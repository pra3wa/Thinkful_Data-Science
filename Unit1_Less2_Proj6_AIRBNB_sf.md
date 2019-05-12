--Questions

1.) What's the most expensive listing? What else can you tell me about the listing?

Answer: The most expensive listing is a Full House Victorian (7,500 sqft) with 4 floors 
and a hot tub. The host name is Sarah and the price is $10,000. The house is in the 
neighborhood of Western Addtion and has a minimum of 2 nights rental with 3 reviews.
It is available 18 days out of the year. 

```SQL
SELECT
	*
FROM
	sfo_listings
	
ORDER BY price DESC
```

2.) What neighborhoods seem to be the most popular?

Answer: Popular in this case is assumed to be the neighborhoods with the most number of listings. With this assumption in mind, the three most popular neighbourhoods are Mission with 694 listings, 
Western Addition with 506 listings, and South of Market with 504 listings.


```SQL
SELECT
	neighbourhood,
	COUNT(*)
FROM
	sfo_listings
	
GROUP BY 1

ORDER BY COUNT DESC
```

3.) What time of year is the cheapest time to go to San Francisco? What about the busiest?

Answer #1: The cheapest time to go to San Francisco is assumed to be the month with the lowest average listing. With this in mind, the cheapest time to go to San Francisco is January, with an average AirBnB listing price of $212.51.

```SQL
WITH 
	final_table
AS(
WITH 
	clean_table
AS (
SELECT
	EXTRACT (month from calender_date) "listing_month",
	REPLACE (REPLACE(REPLACE(price,'$',''),'.00', ''),',','') "clean_price"
FROM 
	sfo_calendar)
SELECT
	listing_month,
CAST (clean_price AS int)
FROM
	clean_table)
SELECT
	listing_month,
	AVG(clean_price)
FROM
	final_table
GROUP BY listing_month
ORDER BY avg ASC
```
Answer #2: 

```SQL
SELECT 
	EXTRACT (month from calender_date) "listing_month",
	COUNT(*) AS available
FROM
	sfo_calendar
WHERE
	available = 't'
GROUP BY listing_month
ORDER BY available ASC
```
