
Agrinet’s purpose is to improve the food security of Trinidad and Tobago through the use of ICT. To this end, one of the things we are trying to do is help farmers and policy makers make sound, data-driven decisions. One way we are trying to achieve this is by trying to forecast crop prices withing a six month window using previous price data as provided by NAMDEVCO. Sadly,  none of my methods produced accurate results. I tried as many models as I could think of – linear regressions, support vector regressions with several different kernels, multilayer feed-foward neural networks trained with back-propogation, Ridge Regression, LASSO Regression, practically every feature of the scikit-learn’s regression toolkit – on a bunch of different feature sets –  feature sets carved from the mean prices from t-12 to t-6 and the time series model’s forecasts and “estimated” residuals- to no avail. I suppose that’s how research oriented work rolls some of the time. Nonetheless, I present some of them here as even failures can be edifying.

Since there are over 50 crops under Agrinet’s consideration, it would be impractical to go over all of them and all of the models I applied .  So for the sake of brevity, I’ll present the most interesting results – the application of ARIMA time series modelling in conjunction with linear regression, Support Vector Regression with a polynomial kernel, and a multilayer neural network trained with back-propagation using sigmoid layers on the data set for small limes.

**Exploration Phase**

As with any machine learning project, we need to dissect the data and understand something of its dynamics to inform our machine learning and statistical models.

We extracted the monthly data from the xls files on NAMDEVCO’s site and stored them as csv’s beforehand using python. Loading the data into R and running auto-correlation function – acf – on the mean price data we generate the following graph

 

 

There is substantial auto-correlation there!

I am far from an expert on time series analysis (or anything for that matter), but it seemed as though we could have used ARIMA modelling here. Loading the convenient forecast package into  R and running auto.arima on the time series data we get the following results on a subset of the time series

 

However, now we need to assess the quality of forecast on the known unused data. For this we use the Mean Absolute Error and the Mean Square Error function and yield the following results:

 

Not so good.

 

 

 

 

 

 


