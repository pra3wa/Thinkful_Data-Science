# Thinkful_Data-Science
1.) What's the most expensive listing? What else can you tell me about the listing?
A1:The most expensive listing is a Full House Victorian (7,500 sqft) with 4 floors 
and a hot tub. The host name is Sarah and the price is $10,000. The house is in the 
neighborhood of Western Addtion and has a minimum of 2 nights rental with 3 reviews.
It is available 18 days out of the year. 

'''SELECT
	*
FROM
	sfo_listings
ORDER BY price DESC
'''
