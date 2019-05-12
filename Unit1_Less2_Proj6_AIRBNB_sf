--Questions

1.) What's the most expensive listing? What else can you tell me about the listing?
A1:The most expensive listing is a Full House Victorian (7,500 sqft) with 4 floors 
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
A2:The three most popular neighbourhoods are Mission with 694 listings, 
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
