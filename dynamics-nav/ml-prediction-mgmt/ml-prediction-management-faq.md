
# Frequently Asked Questions

##Can I use the web service with the Excel add-in?
Yes, but there is a known issue to be aware of. There is a mismatch between what the experiment expects as Global Parameters (a CSV-like two lines of text) and what the Excel add-in can provide (one line of text).

The cause of the error is that the experiment expects the **Horizon** parameter in Global Parameters. To change that, change the default forecasting horizon to **3** by replacing these lines in the R code in the experiment:
  
```
#Number of forecast predictions
horizon <- as.numeric(dataset2$HORIZON)

-with-

#Number of forecast predictions
if(is.null(dataset2$HORIZON)) { 
horizon <- 3;
} else {
horizon <- as.numeric(dataset2$HORIZON)
} 
```
## How do I know if I have enough data?
The more data you have about payments that were on-time and late, the better. As a general rule of thumb, you should have two or three hundred records of each type, that is, both late payments and payments that were on-time. However, depending on other factors, such as variance in your data, you might be able to get accurate predictions even if you have less than that. For example, you might try actually removing some of your data and then retraining your model, or just train the model several times. Our API will check the quality of your model, which you can use to decide whether the predictions are reliable enough to use. 

## Where does the "quality" value come from.
The quality of the model is important. When our predictive experiment uses your data to train a model it determines a quality value for the model as a percentage. The model quality indicates how accurate the model's predictions are likely to be. Several factors can impact the quality of a model. For example, these factors might be that there simply was not enough data, or the data did not contain enough variation. You can view the quality of the model you are currently using on the **Late Payment Prediction Setup** page. You can also specify a minimum threshold for the model quality. Models with a quality value below the threshold will not produce predictions.

