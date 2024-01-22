city Analysis
import pandas as pd
import pandas as pd
dataset=pd.read_csv(r"C:\Users\User\Downloads\Dataset.csv")
dataset=pd.read_csv(r"C:\Users\User\Downloads\Dataset.csv")
dataset
dataset
Restaurant ID	Restaurant Name	Country Code	City	Address	Locality	Locality Verbose	Longitude	Latitude	Cuisines	...	Currency	Has Table booking	Has Online delivery	Is delivering now	Switch to order menu	Price range	Aggregate rating	Rating color	Rating text	Votes
0	6317637	Le Petit Souffle	162	Makati City	Third Floor, Century City Mall, Kalayaan Avenu...	Century City Mall, Poblacion, Makati City	Century City Mall, Poblacion, Makati City, Mak...	121.027535	14.565443	French, Japanese, Desserts	...	Botswana Pula(P)	Yes	No	No	No	3	4.8	Dark Green	Excellent	314
1	6304287	Izakaya Kikufuji	162	Makati City	Little Tokyo, 2277 Chino Roces Avenue, Legaspi...	Little Tokyo, Legaspi Village, Makati City	Little Tokyo, Legaspi Village, Makati City, Ma...	121.014101	14.553708	Japanese	...	Botswana Pula(P)	Yes	No	No	No	3	4.5	Dark Green	Excellent	591
2	6300002	Heat - Edsa Shangri-La	162	Mandaluyong City	Edsa Shangri-La, 1 Garden Way, Ortigas, Mandal...	Edsa Shangri-La, Ortigas, Mandaluyong City	Edsa Shangri-La, Ortigas, Mandaluyong City, Ma...	121.056831	14.581404	Seafood, Asian, Filipino, Indian	...	Botswana Pula(P)	Yes	No	No	No	4	4.4	Green	Very Good	270
3	6318506	Ooma	162	Mandaluyong City	Third Floor, Mega Fashion Hall, SM Megamall, O...	SM Megamall, Ortigas, Mandaluyong City	SM Megamall, Ortigas, Mandaluyong City, Mandal...	121.056475	14.585318	Japanese, Sushi	...	Botswana Pula(P)	No	No	No	No	4	4.9	Dark Green	Excellent	365
4	6314302	Sambo Kojin	162	Mandaluyong City	Third Floor, Mega Atrium, SM Megamall, Ortigas...	SM Megamall, Ortigas, Mandaluyong City	SM Megamall, Ortigas, Mandaluyong City, Mandal...	121.057508	14.584450	Japanese, Korean	...	Botswana Pula(P)	Yes	No	No	No	4	4.8	Dark Green	Excellent	229
...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...
9546	5915730	Naml۱ Gurme	208	��stanbul	Kemanke�� Karamustafa Pa��a Mahallesi, R۱ht۱m ...	Karak�_y	Karak�_y, ��stanbul	28.977392	41.022793	Turkish	...	Turkish Lira(TL)	No	No	No	No	3	4.1	Green	Very Good	788
9547	5908749	Ceviz A��ac۱	208	��stanbul	Ko��uyolu Mahallesi, Muhittin ��st�_nda�� Cadd...	Ko��uyolu	Ko��uyolu, ��stanbul	29.041297	41.009847	World Cuisine, Patisserie, Cafe	...	Turkish Lira(TL)	No	No	No	No	3	4.2	Green	Very Good	1034
9548	5915807	Huqqa	208	��stanbul	Kuru�_e��me Mahallesi, Muallim Naci Caddesi, N...	Kuru�_e��me	Kuru�_e��me, ��stanbul	29.034640	41.055817	Italian, World Cuisine	...	Turkish Lira(TL)	No	No	No	No	4	3.7	Yellow	Good	661
9549	5916112	A���k Kahve	208	��stanbul	Kuru�_e��me Mahallesi, Muallim Naci Caddesi, N...	Kuru�_e��me	Kuru�_e��me, ��stanbul	29.036019	41.057979	Restaurant Cafe	...	Turkish Lira(TL)	No	No	No	No	4	4.0	Green	Very Good	901
9550	5927402	Walter's Coffee Roastery	208	��stanbul	Cafea��a Mahallesi, Bademalt۱ Sokak, No 21/B, ...	Moda	Moda, ��stanbul	29.026016	40.984776	Cafe	...	Turkish Lira(TL)	No	No	No	No	2	4.0	Green	Very Good	591
9551 rows × 21 columns

city_restaurant_count=dataset.groupby('City')['Restaurant Name'].count()
city_restaurant_count
City
Abu Dhabi          20
Agra               20
Ahmedabad          21
Albany             20
Allahabad          20
                   ..
Weirton             1
Wellington City    20
Winchester Bay      1
Yorkton             1
��stanbul          14
Name: Restaurant Name, Length: 141, dtype: int64
city_with_highest_restaurants=city_restaurant_count.idxmax()
highest_restaurant_count=city_restaurant_count.max()
​
(f"The city with the highest number of restaurants is'{city_with_highest_restaurants}'with {highest_restaurant_count} restaurants.")
"The city with the highest number of restaurants is'New Delhi'with 5473 restaurants."
average_ratings_by_city=dataset.groupby('City')['Aggregate rating'].mean()
print("Average rating for restaurants in each city:")
print(average_ratings_by_city)
Average rating for restaurants in each city:
City
Abu Dhabi          4.300000
Agra               3.965000
Ahmedabad          4.161905
Albany             3.555000
Allahabad          3.395000
                     ...   
Weirton            3.900000
Wellington City    4.250000
Winchester Bay     3.200000
Yorkton            3.300000
��stanbul          4.292857
Name: Aggregate rating, Length: 141, dtype: float64
city_with_highest_rating=average_ratings_by_city.idxmax()
highest_average_rating=average_ratings_by_city.max()
(f"the city with the highest average rating is'{city_with_highest_rating}'with an average rating of {highest_average_rating:.2f}.")
​
"the city with the highest average rating is'Inner City'with an average rating of 4.90."
​


​
