# Time Series Analysis of Amazon Data

## Description

Amazon product prices and other parameters vary with time. This project deals with the analysis of Amazon products data.

## Scope

 - A customer can know the best time to buy a product - before, during or after a sale
 - A company can understand how their productss and their competitors' products' prices, ratings, offers etc. are varying.

## Motivation

E-commerce product prices vary considerably over time. Knowing when to buy a product can help a consumer save money. It can be difficult to decide if a product should be bought at that point of time, or if the price will decrease or increase further.
There is a lack of analysis of Amazon product data, especially Amazon India products. We want to show how the product prices and other details vary over time - before, during and after a sale.

## Dataset

 - The data is collected by performing web scraping on Amazon India.
 - Details of 10 products are scraped periodically over the course of a few months.
 - The Web scraper is made using Scrapy python library. A PostgreSQL database is used to store and add to the database. The scraper and database are deployed to Heroku. The database is exported to a `.csv` file. The scraper program is at [this repository](https://github.com/Samyak2/amazon-scraper) (private repository)
 - The dataset consists of 29 columns.
 - As the data is being scraped everyday, it does not have a fixed number of rows. As of 10-10-2019 it has `1217 rows`.
 - Some of the columns of the dataset are:
     - `Name`: Name of the product.
     - `Price`: Price of the product including all discounts except lightning deals.
     - `url`: URL of the product.
     - `Seller Name`: Name of the main/default seller.
     - `Seller Rating`: Star rating of the main/default seller.
     - `Number of seller ratings`: Number of people who have rated the main/default seller.
     - `Answered Questions`: Number of questions answered. The value is `1000+` if there are more than 1000 questions.
     - `Availibility`: Availibility of the product as described by a string. It can take any of these values:
         - `Currently unavailable.`
         - `In stock.`
         - `Only n left in stock.` where n is an integer.
         - `Only n left in stock (more on the way).` where n is an integer.
     - `Time`: Time at which the data was scraped (With the timezone as GMT and NOT IST).
     - `Deal Price`: Price during a lightning deal. No value is there is no lightning deal.
     - `ASIN`: A unique ID given by Amazon to a product. Not available for all products in this dataset.
     - `Brand`: Brand name of the product.
     - `Return Policy`: Defines the return policy of the product in a string.
     - `Warranty`: Shows the warranty available on the product. Could be of the form `x Year Warranty` or `x Day Warranty`.
     - `Pay on Delivery`: Value can be Null/NaN or `Pay on Delivery`.
     - `Amazon Delivered`: Value can be Null/NaN or `Amazon Delivered`.
     - `Features`: A list of features in the form of a string with each value in the list separated by `||`.
     - `Weight`: weight of the product. Can be different units hence it's a string.
     - `Model`: Model number
     - `Category`: List of categories the product falls in, in the form of a string with commas `,` as separator