### How many holiday packages are in each coutry:
```
SELECT c.country_name, COUNT(hp.h_package_id) as no_h_packages
FROM holiday_package hp 
JOIN hotel h
ON hp.hotel_id=h.hotel_id
JOIN country c 
ON h.country_id=c.country_id
GROUP BY c.country_id
ORDER BY c.country_name
```

### Average price of holiday package for adult:
```
SELECT AVG(price_adult) AS average_price_adult
FROM holiday_package
```

### Occupancy of individual holiday packages
```
SELECT hp.h_package_id, (COUNT(b.no_adults)+COUNT(b.no_children)) AS occupacy
FROM holiday_package hp
JOIN booking b
ON hp.h_package_id=b.h_package_id
GROUP BY hp.h_package_id
ORDER BY occupacy DESC
```
### Subquery - Customers who booked holiday package in Italy
```
SELECT customer_id
FROM booking
WHERE h_package_id = 
	(
	SELECT h_package_id
	FROM holiday_package
	WHERE hotel_id IN
		(
		SELECT hotel_id
		FROM hotel
		WHERE country_id = (
			SELECT country_id
			FROM country
			WHERE country_name LIKE 'Italy'
			)
		)
	)
```
### CASE statement - If a customer buys at least 2 holiday packages, he will have discount 10% for next trips. If he buys 5 or more trips, he will obtain discount 20%.

```
SELECT 
	customer_id,
	CASE
	WHEN (COUNT(h_package_id)) > 1
		AND COUNT(h_package_id) < 5 THEN 10
	WHEN (COUNT(h_package_id)) > 5 THEN 20
	ELSE 0
	END discount
	
FROM booking
GROUP BY customer_id
ORDER BY discount DESC
```


