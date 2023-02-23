# GetGo-App-Reviews

```Some Data Science on GetGo App Reviews```

1. Fetch reviews of the GetGo App from the Apple App Store. This is done using the app_store_scraper. Take note that the country code is 'sg' and app_id is 
'1545316216'.

<img width="1090" alt="Screenshot 2023-02-23 at 10 10 42 PM" src="https://user-images.githubusercontent.com/95064358/221019089-1a3c7943-dd88-40cc-a2c1-a21c293b88ac.png">

2. Construct some word clouds of the reviews. Here are a few:

```word cloud of the reviews```

![wordcloudreview](https://user-images.githubusercontent.com/95064358/221010235-a98befac-ccbc-44e7-a18a-f0e1ed36466c.png)

```word cloud of the titles```

![wordcloudtitle](https://user-images.githubusercontent.com/95064358/221010289-f4ab6592-9a98-4c3f-8687-1733dd358793.png)

```word cloud of reviews with rating 1```

![wordcloudrating1](https://user-images.githubusercontent.com/95064358/221010346-786d7102-139d-423a-9feb-e92d0ba0962c.png)

As we can see, the reviews are generally positive, which is good news! Words like "easy", "good" and "convenient" appear multiple times. Nonetheless, we do get a peek at the common problems faced by users in the third word cloud. These include "booking", "customer service" and "late", just to name a few. 

3. Create some visualisations to understand the data better!

<img width="414" alt="Screenshot 2023-02-23 at 9 46 09 PM" src="https://user-images.githubusercontent.com/95064358/221013917-592acd86-eef3-40c0-874e-ecb3a3523c8e.png">

As we can see, the reviews are generally positive with a high number of 5/5 reviews. Nonetheless, there are also a fair number of negative reviews (1/5), which is understandable for any application with a sizable number of downloads.


<img width="794" alt="Screenshot 2023-02-23 at 9 46 33 PM" src="https://user-images.githubusercontent.com/95064358/221013984-d80c38f1-830b-4703-bfeb-8b18d5f371c6.png">

Here we get to see the fluctuation of ratings per month. We also observe an upwards trend in recent months, which is encouraging as well.

4. Use the ARIMA model to forecast the rating next month

ARIMA is a model used rather frequently in time series forecasting. Here, we try to forecast the average rating of the GetGo application on the App Store next month.




