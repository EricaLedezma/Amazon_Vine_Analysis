# Amazon_Vine_Analysis

## Overview

In this project, we were tasked with analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. This analysis is specifically focused on watches.

## Results
Analysis process: PySpark was used to perform the ETL process to extract the watches dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Then used PySpark to determine if there is any bias toward favorable reviews from Vine members in the dataset. Here are the results:

- Dataset is filtered to show total votes count >= 20
![image](https://user-images.githubusercontent.com/111028230/213822996-03227ac0-1ac8-4126-88f7-7f928307d571.png)

- Create new dataframe from step 1 where number of helpful_votes divided by total_votes is >= 50%.
![image](https://user-images.githubusercontent.com/111028230/213824095-b45dfb89-8825-46b6-bce7-13b4ef198729.png)

- Filter dataframe from step 2 and create new one that shows where a review was written as part of the Vine program (paid), vine == 'Y'.

  ![image](https://user-images.githubusercontent.com/111028230/213824246-e6561fb0-1179-4a76-9628-b7d6de107151.png)
 
- Same process, however, we want the rows where the review was ***not*** part of the Vine program (unpaid), vine == 'N'.

  ![image](https://user-images.githubusercontent.com/111028230/213824631-a96b7bd3-4448-4061-bd6c-f11d01bcc709.png)

- Finally, get the total number of reviews, the number of 5-star reviews, and the percentage of 5-star reviews for the two types.the total number of reviews, the number of 5-star reviews, and the percentage of 5-star reviews for the two types of reviews.

  ![image](https://user-images.githubusercontent.com/111028230/213827417-3ecd863d-8791-4199-ad8a-8d1af638f68e.png)
  ![image](https://user-images.githubusercontent.com/111028230/213827532-79e32249-ec0f-440b-a3ab-3cfb88238ca2.png)


## Summary
Based on the analysis, we do not show any positive bias for reviews with the Vine program. The percentage of 5 star votes in the Vine program was much lower (37%) than the the percentage of non-Vine reviews (54.1%).

We could analyze the whole dataset, to see if the results match or are signifcantly different.
