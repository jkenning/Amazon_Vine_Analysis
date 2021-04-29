# Amazon Vine Reviews - Big Data

Analysis of thousands of Amazon US review data for electronics products

## Overview

The project involves analyzing a dataset thousands of Amazon product reviews. Using PySpark, the ETL process is used to extract and transform the data, connect to an AWS RDS instance, and load the transformed data into PgAdmin. 

### Purpose

A client is about to release a large catalog of products of a leading retail website. Analyses aim to answer the following:

* How to the reviews of the company's products compare to similar products sold by their competitors
* Is it worth the cost of enrolling in a program that gives out rewards to select reviewers?

The Amazon Vine program provides products to customers in exchange for writing a review. PySpark was used to determine if there is any bias towards favorable reviews from Amazon Vine members for "Electronics" product reviews and recommend whether it is worth the client company participating in the program. 

## Resources

Tools and software: Spark 3.1.1, PySpark in Google Colab, Amazon Web Services RDS, PgAdmin 4.29, Visual Studio Code 1.54.3

Amazon source data: https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt

## Analysis of Vine Reviews Vs. Non-vine Reviews

A dataframe was created of the Amazon US Electronics product reviews. The data was then filtered to products where there are 20 or more votes and the percentage of helpful votes is equal or greater than 50%. 

Figure. 1 - Resultant dataframe filtered to vine reviews

Figure. 2 - Resultant dataframe filtered to non-vine Reviews

**How many vine reviews and non-vine reviews were there?**

* Total vine (paid) reviews: 1080

* Total non-vine (unpaid) reviews: 49673

**How many vine reviews were 5 stars? How many non-vine reviews were 5 stars?**

* Total vine (paid) 5-star reviews: 454

* Total non-vine (unpaid) 5-star reviews: 23043

**What percentage of vine reviews were 5 stars? What percentage of non-vine reviews were 5 stars?**

* Percentage of vine (paid) 5-star reviews: 42.0%

* Percentage of non-vine (unpaid) 5-star reviews: 46.4%

## Summary

The analysis shows there is no positivity bias for reviews given by vine members compared to non-vine members. In fact, while the percentage of vine 5-star reviews vs. non-vine 5-star reviews is fairly similar (within 5 percentage points), the percentage of non-vine 5-star reviews is actually higher. 

While this suggests that non-vine members are more likely to give 5-star reviews than vine members, it does not necessarily mean that they provide more favorable reviews for a product overall. It would be worth seeing a comparison for each star rating, it could be that vine reviewers are significantly more likely to give 4-star reviews than non-vine members for instance which are still pretty good reviews. It might also be the case that even though vine reviewers do not provide any different proportion of highly rated reviews, they are far less likely to give the product negative reviews than non-vine members which could still be worthwhile investment for the company. So it is worth analyzing the difference between percentages of average and negative reviews.