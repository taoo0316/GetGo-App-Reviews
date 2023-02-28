# GetGo-App-Reviews

## Some Data Science on GetGo App Reviews

## 1. Fetch reviews of the GetGo App from the Apple App Store. 

This is done using the app_store_scraper. Take note that the country code is 'sg' and app_id is '1545316216'.

https://apps.apple.com/us/app/getgo-carsharing/id1545316216

<img width="1090" alt="Screenshot 2023-02-23 at 10 10 42 PM" src="https://user-images.githubusercontent.com/95064358/221019089-1a3c7943-dd88-40cc-a2c1-a21c293b88ac.png">

## 2. Construct some word clouds of the reviews. Here are a few:

![wordcloudreview](https://user-images.githubusercontent.com/95064358/221010235-a98befac-ccbc-44e7-a18a-f0e1ed36466c.png)

```word cloud of the reviews```

![wordcloudtitle](https://user-images.githubusercontent.com/95064358/221010289-f4ab6592-9a98-4c3f-8687-1733dd358793.png)

```word cloud of the titles```

![wordcloudrating1](https://user-images.githubusercontent.com/95064358/221010346-786d7102-139d-423a-9feb-e92d0ba0962c.png)

```word cloud of reviews with rating 1```

As we can see, the reviews are generally positive, which is good news! Words like "easy", "good" and "convenient" appear multiple times. Nonetheless, we do get a peek at the common problems faced by users in the third word cloud. These include "booking", "customer service" and "late", just to name a few. 

## 3. Create some visualisations to understand the data better!

<img width="414" alt="Screenshot 2023-02-23 at 9 46 09 PM" src="https://user-images.githubusercontent.com/95064358/221013917-592acd86-eef3-40c0-874e-ecb3a3523c8e.png">

As we can see, the reviews are generally positive with a high number of 5/5 reviews. Nonetheless, there are also a fair number of negative reviews (1/5), which is understandable for any application with a sizable number of downloads.


<img width="794" alt="Screenshot 2023-02-23 at 9 46 33 PM" src="https://user-images.githubusercontent.com/95064358/221013984-d80c38f1-830b-4703-bfeb-8b18d5f371c6.png">

Here we get to see the fluctuation of ratings per month. We also observe an upwards trend in recent months, which is encouraging as well.

## 4. Use the ARIMA model to forecast the average rating next month

ARIMA is a model used rather frequently in time series forecasting. Here, we try to forecast the average rating of the GetGo application on the App Store next month.

<img width="581" alt="Screenshot 2023-02-23 at 10 36 55 PM" src="https://user-images.githubusercontent.com/95064358/221024413-1a31b72f-ed0f-47d1-8b2b-b1347783ba63.png">

From the forecast, the monthly average rating in March will be around 2.71, which is indeed an increase from the previous two months this year. It will be interesting to see if this forecast holds true. 

## 5. Top modelling using LDA for reviews with rating 1

To get a better sense of the areas of improvement, we can do a topic modelling for reviews with rating 1 using the Latent Dirichlet Allocation (LDA) algorithm from the gensim library.

The result is as follows:

<img width="994" alt="Screenshot 2023-02-24 at 2 02 52 AM" src="https://user-images.githubusercontent.com/95064358/221059078-de0d8acb-7f4e-414b-83b1-333fbac73e27.png">

## 6. Developer response rate

Now we have a better sense of the problems surfaced by customers, how often do our developers respond to their questions? We can use data science to find out too.

<img width="602" alt="Screenshot 2023-02-24 at 11 58 16 AM" src="https://user-images.githubusercontent.com/95064358/221149406-31c76636-f8a2-470a-8a63-df988d0c945d.png">

<img width="630" alt="Screenshot 2023-02-24 at 11 58 34 AM" src="https://user-images.githubusercontent.com/95064358/221149480-c4e0cfb5-c0ab-4ec4-a791-6c4b01985eda.png">

As we can see, the overall response rate is close to 50%, which is a respectable rate. The response rate for reviews of rating '1' is over 60%, which makes sense as we want to tend to those who encounter issues with our application. Nonetheless, maybe it is better to raise this number so that the customers can have an even better overall customer experience. 

Since we have the time series data, it would be a pity to not take advantage of that. Therefore, I have also created a plot to show how the rate of response by developers changes over time. The result is rather interesting as well.

<img width="439" alt="Screenshot 2023-02-24 at 2 37 03 PM" src="https://user-images.githubusercontent.com/95064358/221180663-ab016dda-35c8-4ed2-ac77-33cab5062ec2.png">

As we can see, there is a very high rate of response until Jan 2022. After that, the response rate seems to fluctuate a lot more, with a sharp dip from July to October of 2022. Following that, the response rate has been steadily climbing up back again. 

It will be interesting to look into the periods of July-October of 2022 to understand better why the response rate is so low.

We first look at the number of reviews and developer responses during that 4-month period.

<img width="687" alt="Screenshot 2023-02-24 at 4 02 30 PM" src="https://user-images.githubusercontent.com/95064358/221197571-13420bae-ae63-4aaa-9473-710da76458e9.png">

As seen above, the number of reviews left is 61, but the number of responses is only 2.

We then look at the average number of reviews left in a 4-month period.

<img width="918" alt="Screenshot 2023-02-24 at 4 03 48 PM" src="https://user-images.githubusercontent.com/95064358/221197885-e2f4631e-af37-4acb-bce0-609044ec109f.png">

The number is 88, which is in line with the number of reviews left from July to October of 2022. This suggests there might indeed be a lack of responses in that period, which means we need to look into the operating procedures during that period of time to address the problem. Were developers busier? Is it because there was a critical bug in the application they had to attend to?

## 7. Delving into specific reviews

Beyond using data science to understand a problem, sometimes it is actually helpful to look at specific customer feedback to get a better sense of the issue. 

To do this, I looked at reviews during the 4-month period when the response rate is low. Interestingly, some common problems do surface.

A notable one is the functionality of the 'book' icon. Many customers provided feedback that they faced difficulties when pressing the icon.

<img width="1004" alt="Screenshot 2023-02-24 at 9 04 59 PM" src="https://user-images.githubusercontent.com/95064358/221269127-5613506c-c603-4fd8-b481-1cdb95ecc44f.png">

<img width="1003" alt="Screenshot 2023-02-24 at 9 05 23 PM" src="https://user-images.githubusercontent.com/95064358/221269211-9a3dbed3-a928-4bc6-94e9-276c7fd3c734.png">

While I am not sure if the icon is fixed now, the issue is certainly worth looking into by the engineering team :D. It is also worth noting that a developer response was not provided for the three reviews above.

![IMAGE 2023-02-24 21:16:18](https://user-images.githubusercontent.com/95064358/221271157-3f18b191-4499-4b0e-a5f6-3b62b53a2ae3.jpg)

```The UI of GetGo at the time of this project```

## 8. Generate replies trained on existing ones

As we know that developers may not be able to tend to every review, we can utilise natural language processing to generate replies, trained on the replies already present in the data set. There are many such language models available, such as seq2seq, transformers, etc. However, this requires extensive computational resources. Moreover, this often means we need a relatively large amount of training data. Nonetheless, to see a similar project I did previously, see this link: https://github.com/taoo0316/seq2seq-chatbot.

Another option is to utilise ChatGPT, an AI language model that has gained much traction lately. It is worth pointing out here that since ChatGPT was not trained on data specifically related to the company, the replies it generates may not be completely applicable as well. Nonetheless, I have tried out one of the unreplied reviews, and the response is not too bad:

<img width="812" alt="Screenshot 2023-02-25 at 1 44 29 AM" src="https://user-images.githubusercontent.com/95064358/221321822-fe16f9c7-3887-4d45-9215-497bf4ee85cf.png">

<img width="801" alt="Screenshot 2023-02-25 at 1 45 06 AM" src="https://user-images.githubusercontent.com/95064358/221321870-ece60484-ccd6-4fb6-a4bf-ca9705ecd880.png">

While it may not be a good idea to simply copy the reply generated by ChatGPT, the developer team can consider using a similar language model to automate the process. The team can then edit the reply as they see fit. In this way, we will be able to increase the response rate to the reviews left by customers. 

## 9. Conclusion

Overall, it is encouraging to see that the application has recently been on an upwards trajectory, with the response rate and average monthly rating both improving over time. Moreover, many customers are happy with their user experience, despite having some issues occasionally. To improve further, the team can consider looking into specific issues surfaced by customers during periods when the average rating is unsatisfactory/developer response rate is low. It might also be worth looking into periods when the number of reviews left is high to get a better sense of the high volume of customer feedback. Beyond that, the team can also consider looking into other avenues of customer feedback, such as via word of mouth, email or direct interactions with customer service specialists.
