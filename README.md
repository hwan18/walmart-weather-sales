# walmart-weather-sales
Walmart Recruiting II: Sales in Stormy Weather

# **Walmart Recruiting II: Sales in Stormy Weather**

## Predict how sales of weather-sensitive products are affected by snow and rain

## Problem:

1. **111 products** whose sales may be **affected by the weather** (such as milk, bread, umbrellas, etc.).
2. 111 products are sold in stores at **45 different Walmart** locations.
3. Some of the **products may be a similar item** (such as milk) but have a **different id** in different stores/regions/suppliers.
4. **45 locations** are covered by **20 weather stations** (i.e. some of the stores are nearby and share a weather station).

### Goal:

1. **predict the amount of each product sold** around the **time of major weather** events.
2. predict the units sold for a window of ±3 days surrounding each storm.

### Data Info:

1. full observed weather covering the entire data set.
2. sales number 0 doesn't necessarily mean there was no demand for this product; it may mean it was in stock but none were sold, or it could mean that the product was out of stock, or discontinued and not available.
3. The following graphic shows the layout of the test windows. The **green dots are the training set days**, the **red dots are the test set days**, and the **event=True are the days with storms.** Note that this plot is for the **20 weather stations**.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/25589de8-a826-4c6d-8eeb-1151dcef4191/Untitled.png)

## **Field descriptions**

- date - the day of sales or weather
- store_nbr - an id representing one of the 45 stores
- station_nbr - an id representing one of 20 weather stations
- item_nbr - an id representing one of the 111 products
- units - the quantity sold of an item on a given day
- id - a triplet representing a store_nbr, item_nbr, and date. Form the id by concatenating these (in that order) with an underscore. E.g. "2_1_2013-04-01" represents store 2, item 1, sold on 2013-04-01.

## **File descriptions**

- key.csv - the relational mapping between stores and the weather stations that cover them
- sampleSubmission.csv - file that gives the prediction format
- train.csv - sales data for all stores & dates in the training set
- test.csv - stores & dates for forecasting (missing 'units', which you must predict) **NOTE: This file has been encrypted. To get the password, please fill out [Walmart's Recruiting Survey](http://form.jotformpro.com/form/50757464385970)**
- weather.csv - a file containing the NOAA weather information for each station and day
- noaa_weather_qclcd_documentation.pdf - a guide to understand the data provided in the weather.csv file
