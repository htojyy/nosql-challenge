# nosql-challenge

## 1. Import JSON file using pymongo and update the database

* Import the data `Resources/establishments.json` in terminal, creating database `uk_food` and collection `establishments`  
 Type in terminal:  

    ```bash
    mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json
    ```

* Add a new halal restaurant's details in a dictionary to the database  
  <img src="Images/Add_dict_to_database.png" alt="Add dictionary to database" width="550">

* Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields  
    `{'BusinessType': 'Restaurant/Cafe/Canteen', 'BusinessTypeID': 1}`

* Update the new restaurant with the correct BusinessTypeID  
    `{'_id': ObjectId('6603febb9efd75a38842163d'), 'BusinessName': 'Penang Flavours', 'BusinessType': 'Restaurant/Cafe/Canteen', 'BusinessTypeID': 1 ...`
* Find how many documents have LocalAuthorityName as "Dover", then delete those documents  
    `Number of documents that have LocalAuthorityName = Dover:  994`
    `Remaining documents that include Dover:  0`
* Convert latitude and longitude to decimal datatype, RatingValue to integer datatype  

    ```python
    {'RatingValue': 4,
    'geocode': {'latitude': Decimal128('51.086058'),
                'longitude': Decimal128('1.196408')}}
    {'RatingValue': 5,
    'geocode': {'latitude': Decimal128('51.085797'),
                'longitude': Decimal128('1.194762')}}
    {'RatingValue': 5,
    'geocode': {'latitude': Decimal128('51.083812'),
                'longitude': Decimal128('1.195625')}}
    {'RatingValue': 5,
    'geocode': {'latitude': Decimal128('51.0783519967076'),
                'longitude': Decimal128('1.18590330311705')}}
    {'RatingValue': 5,
    'geocode': {'latitude': Decimal128('51.0783519967076'),
                'longitude': Decimal128('1.18590330311705')}}
    ```

## 2. Exploratory Analysis

## References

* [UK Food Standards Agency](https://www.food.gov.uk/) (2022). UK food hygiene rating data API. <https://ratings.food.gov.uk/open-data/en-GBLinks> to an external site.. Contains public sector information licensed under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/) Accessed Sept 9, 2022 and Sept 12, 2022 with the establishment settings as follows: longitude=51.5072, latitude=-0.1276, maxdistancelimit=4567, pagesize=10000, sortoptionkey=distance, pagenumber=(1,2,3,4,5,6,7,8).
