## Booking.com Implicit Feedback Prediction(Travel Destination Forecast)

### About Implicit Feedback Prediction 
Implicit feedback prediction is a technique for making inferences from user behavior (implicit ratings). For example, a user books a ticket on Booking.com, watches a movie on YouTube, or buys a product on Amazon. 

`Advantage` -- This information is more available and easier to get.

`Disadvantage` -- There is no user negative feedback or level of preference (i.e. how much time a user watched a YouTube video).

### About Project Introduction
Booking.com currently focuses on **a multi destinations trip planning problem**, which is a popular scenario in the travel domain. The goal of this project is to make the best recommendation of an additional in-trip destination by predicting the probability of each user that might travel to a specific city by using collaborative filtering of implicit rating. 

By using an implicit feedback recommendation system on the Booking.com dataset, we can deduce user next in-trip destination preferences even without their explicit input, allowing for better personalized recommendations.

### Dataset 
We used the [modified training data]() from [Kaggle.com](https://www.kaggle.com/datasets/teresasereno/booking-challenge-data) that contains 970K rows with four columns. We test data predicted implicit ratings for 381K user & city cases.

| Feature | DataType | Detail |
|--------|--------|--------|
| `user_id` | Numeric | real anonymized user id|
| `city_id` | Numeric | city id of the hotel's city (anonymized) |
| `user_country` | Numeric encoded from Text | country from which the reservation was made (anonymized) |
| `ratings`| Binary | a user liking a specific city, with a corresponding city and context feature; **each row of this column is 1 for the initial data** |

### What I achieved in this project:

- Encoded columns with continuous ids
- Implemented negative sampling technique to randomly put negative weights on items(cities) that a user has not visited.
- Used embedding methods to represent users, items, and features as a dense vector.
- Trained different models such as matrix factorization and neural networks.
- Grid searched for the best hyperparameters and tried hyperparameters tuning to achieve the most optimized models. Hyperparameters such as batch size, embedding size, learning rate, weight decay, number of epochs, and dropout rate.
- Used ensembling (similar to random forest) and took average of the result of our best matrix factorization and neural network models in order to achieve our best loss (0.4095).

Thanks to my teammate Michael Reigelman(https://www.kaggle.com/mtreigelman) for working with me on this project.
