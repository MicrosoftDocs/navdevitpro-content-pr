

# How to: Use the Image Analysis API
This topic uses the Image Analyzer extension as an example of how to connect [!INCLUDE[d365fin_long](../includes/d365fin_long_md.md)] with Custom Vision API from Azure Cognitive Services.

<!--Not sure if this section is necessary. 

##To create your own model
1. In a browser, go to [ https://www.customvision.ai/]( https://www.customvision.ai/).
2. Create a new project. Use the **General** type.
3. Upload and tag images. 
  
    > [!Note]
    > For each tag you will need around 38 images. However, it's a good idea to have more than that number of images, so that you have some to test the model's accuracy.
  
4. Train the model.
5. Test the model by choosing the **Quick Test** action.
6. On the **Performance** tab, copy the API URI.
7. Choose the **Setting** action to get the API key.

-->

## To get an API URL and API key
1. In a browser, go to [https://azure.microsoft.com/en-us/services/cognitive-services/computer-vision/](https://azure.microsoft.com/en-us/services/cognitive-services/computer-vision/).  
2. Choose **Start Trial**.  
3. Get an API URI, and add **/analyze** at the end. 
  
    > [!Example]
    > https://westus.api.cognitive.microsoft.com/vision/v1.0**/analyze**
  
4. Get an API key. There are two displayed, use the first one.  
    
    > [!Example]
    > a4ef7524412d4e49ac123456789101112
  
## To use your model in [!INCLUDE[d365fin_long](../includes/d365fin_long_md.md)]
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Image Analysis Setup**, and then choose the related link.  
2. Fill in the **API URI** and **API key** fields.  
3. In the **Limit Type** field, enter a period of time.  
4. In the **Limit Value** field,   .

## To prepare the codeunit
1. In the Development Environment, choose **Object Designer**.  
2. Choose the **Codeunit** button.  
3. Choose the **New** button.  
4. On the **View** FastTab, choose **Properties**.  
5. On the **Properties** page, enter an ID and a name.  
6. Define the global variable **ImageAnalysisManagement: Codeunit Image Analysis Management**.  
7. Add the following statement to the onRun trigger: **ImageAnalysisManagement.Initialize**.  

## To choose a picture to analyze
### From MediaSet
* Add the **Item: recordItem** variable. Use the **SetMedia** function to pass a picture from the **MediaSet** data type.

**Example**
```
Item.GET('1964-S');
ImageAnalysisManagement.SetMedia(Item.Picture.ITEM(Item.Picture.COUNT));

```
  
> [!Note]
> The MediaSet data type may contain several images. In the example above, the latest image is used.
  
### From Blob
1. Add the variable **CompanyInformation: record Company Information**.  
2. Add the temporary variable **TempBlob: record TempBlob**.  
3. Use the function **SetBlob** to pass the picture from the **Blob** data type.  

**Example**
```
CompanyInformation.GET;  
CompanyInformation.CALCFIELDS(Picture);  
TempBlob.Blob := CompanyInformation.Picture;  
ImageAnalysisManagement.SetBlob(TempBlob);  

```
### From File System (Optional)
Use the function ImageAnalysisManagement.SetImagePath to set the path to the image on a local drive.

> [!Note]
> Make sure that the server can access the path.

**Example**
```
ImageAnalysisManagement.SetImagePath('C:\Demo\1964-S.jpg');
ImageAnalysisManagement.SetImagePath('C:\Demo\Annette Hill.jpg');

```

## To choose a type of analysis
Define the global variable **ImageAnalysisResult: Codeunit Image Analysis Result**.

The following types of analyses are available:
  
* Tags  
* Faces (the pictures you analyze must contain human faces)  
* Color  
  
Use the following statements to perform an analysis. Note that the result will be returned to the **ImageAnalysisResult** codeunit.

### Tags
```
ImageAnalysisManagement.AnalyzeTags(ImageAnalysisResult);
```

Check the result with the following statement:

```
MESSAGE('Number of tags %1',ImageAnalysisResult.TagCount);
```

### Faces
```
ImageAnalysisManagement.AnalyzeFaces(ImageAnalysisResult);
```

Check the result with the following statement:

```
MESSAGE('Number of faces %1',ImageAnalysisResult. FaceCount);
```

### Colors
```
ImageAnalysisManagement.AnalyzeColors(ImageAnalysisResult);
```

Check the result with the following statement:

```
MESSAGE('Number of colors %1',ImageAnalysisResult.DominantColorCount);
```

## Working with the Results
The result of the analysis is returned to the ImageAnalysisResult codeunit. This codeunit provides several methods to handle results. The first helps to understand the type of analysis that was done.

1. Define variable: **AnalysisType: option Tags,Faces,Color**.
2. Use the following statement to get the type of the latest analysis:

    ```
    ImageAnalysisResult.GetLatestAnalysisType(AnalysisType);
    ```

3. Now you can use the **AnalysisType** to decide which data you want to read from the ImageAnalysisResult codeunit.

**Example**
```
CASE AnalysisType OF
  AnalysisType::Color: BEGIN
//put code to analyze color here
  END;
  AnalysisType::Faces: BEGIN
//put code to analyze faces here
  END;
  AnalysisType::Tags: BEGIN
//put code to analyze tags here
  END;
END;

```
4. Depending on the type of analysis, the API returns different results.
### Tags
Use the following statement to get the number of returned tags:

```
ImageAnalysisResult.TagCount ;
```

Use the following statement to get the tag name (value):

```
ImageAnalysisResult.TagName(Number);
```

**Example**
```
FOR iii := 1 TO ImageAnalysisResult.TagCount DO
   MESSAGE('Tag %1 with confidence %2',
      ImageAnalysisResult.TagName(iii),
      ImageAnalysisResult.TagConfidence(iii));

```

### Faces
Use the following statement to get the number of analyzed faces (an image can contain several faces).

```
ImageAnalysisResult.FaceCount ;
```
You can get age and gender information for each face.

```
ImageAnalysisResult.FaceAge(Number);
ImageAnalysisResult.FaceGender(Number);

```
> [!Note]
> There will be no output for faces that appear younger than 16 years old.

**Example**

```
FOR iii := 1 TO ImageAnalysisResult.FaceCount DO 
   MESSAGE('Gender %1, age %2',
      ImageAnalysisResult.FaceGender(iii),
      ImageAnalysisResult.FaceAge(iii));
```
### Colors
Use the following statement to get the number of dominant colors (images typically contain several colors).

```
ImageAnalysisResult.DominantColorCount
```

Use the following statement to get the value of each dominant color:  

```
ImageAnalysisResult.DominantColor(iii);
```

Additionally, you can use the following statements to distinguish between foreground and background colors:  

```
ImageAnalysisResult.DominantColorForeground;
ImageAnalysisResult.DominantColorBackground;
```

**Example**
```
MESSAGE('Foreground color: %1, background color: %2',
   ImageAnalysisResult.DominantColorForeground,
   ImageAnalysisResult.DominantColorBackground);
FOR iii := 1 TO ImageAnalysisResult.DominantColorCount DO 
   MESSAGE('Color %1',ImageAnalysisResult.DominantColor (iii));

```
