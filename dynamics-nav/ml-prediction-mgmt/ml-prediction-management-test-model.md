# How to: Building Your Own Predictive Model
You can use Azure Machine Learning Studio to build your own predictive model and use it in [!INCLUDE[d365fin](includes/d365fin_md.md)]. To use your own model, you must subscribe to Azure Machine Learning. <!--Can we recommend a particular subscription?--> For more information, see [Azure Machine Learning Studio Documentation](https://go.microsoft.com/fwlink/?linkid=861765).  
  
We do, however, offer an easier way for you to create and use your own predictive model. You can share the data from your invoices with our predictive experiment in Azure Machine Learning, and let our experiment create and train a predictive model based on your data. The data you share is listed earlier in this topic. To share your data, on the **Late Payment Prediction** page, choose the **Create Custom Model** action. Afterward, predictions will be based on your model, not ours.  
  
> [!Note]
> The quality of the model is important. When our predictive experiment uses your data to train a model it determines a quality value for the model as a percentage. The model quality indicates how accurate the model's predictions are likely to be. Several factors can impact the quality of a model. For example, these factors might be that there simply was not enough data, or the data did not contain enough variation. You can view the quality of the model you are currently using on the **Late Payment Prediction Setup** page. You can also specify a minimum threshold for the model quality. Models with a quality value below the threshold will not produce predictions.  
  
If you create your own model in Azure Machine Learning Studio, without using the tools in [!INCLUDE[d365fin](includes/d365fin_md.md)], you must provide your credentials so that [!INCLUDE[d365fin](includes/d365fin_md.md)] can access the model. There are a couple of steps to do that:

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Late Payment Prediction Setup**, and then choose the related link.  
2. Choose the **Use My Model** check box.  
3. In the **Selected Model** field, choose **My Model**.  
4. On the **My Model Credentials** FastTab, enter the API URL and API Key for your model.  

##See Also  
[Azure Machine Learning Studio Documentation](https://docs.microsoft.com/en-us/azure/machine-learning/studio/)  
[Customizing Dynamics 365, Business edition Using Extensions](ui-extensions.md)  
[Welcome to [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  