# Dataset Description

This dataset contains information about used automobiles and their attributes. It is used for analyzing and exploring car listings. The dataset includes the following columns:

- **dateCrawled**: The date and time when the car listing was crawled.
- **name**: The name of the car model.
- **seller**: Whether the seller is private or a dealer.
- **offerType**: The type of offer, such as "Angebot" (offer) or others.
- **price**: The price of the car listing.
- **abtest**: A test category.
- **vehicleType**: The type of vehicle, such as "bus," "limousine," etc.
- **yearOfRegistration**: The year when the car was first registered.
- **gearbox**: The type of gearbox, such as "manuell" (manual) or "automatik" (automatic).
- **powerPS**: The power of the car's engine in horsepower.
- **model**: The model of the car.
- **odometer**: The mileage of the car in kilometers.
- **monthOfRegistration**: The month when the car was first registered.
- **fuelType**: The type of fuel used by the car, such as "benzin" (gasoline) or others.
- **brand**: The brand or manufacturer of the car.
- **notRepairedDamage**: Indicates if the car has unrepaired damage (e.g., "nein" for no).
- **dateCreated**: The date when the car listing was created.
- **nrOfPictures**: The number of pictures in the car listing.
- **postalCode**: The postal code of the location where the car is listed.
- **lastSeen**: The date and time when the car listing was last seen.

## Data Cleaning and Preprocessing

Before performing any analysis, data cleaning and preprocessing are essential to handle missing values, convert data types, and address any inconsistencies in the dataset.

## Data Analysis and Exploration

This dataset allows for various analyses and explorations, such as:

- Calculating statistics, such as the mean and median of car prices and mileage.
- Understanding the distribution of car types, brands, and fuel types.
- Identifying patterns between car attributes and their impact on price.
- Exploring relationships between car features and seller types.

## Data Visualization

Data visualization techniques, including bar plots, scatter plots, and histograms, can be used to visually represent the distribution and relationships between different car attributes.

**Note**

The provided dataset snippet contains sample rows of the original dataset, and its actual size and specific attributes may vary based on the source. To conduct a comprehensive analysis, refer to the complete dataset and its documentation. Additionally, consider performing further data cleaning and validation to ensure accurate results in the analysis process.

# Code Description

The provided code is a Python script using the Pandas library to analyze a dataset of used automobile listings. Below is a step-by-step explanation of each part of the code:

1. **Data Loading and Inspection:**
   - The script starts by importing the Pandas and NumPy libraries.
   - It loads the dataset from a CSV file named "autos.csv" using the `pd.read_csv()` function, with the "Latin-1" encoding.
   - The script then uses `autos.info()` to display information about the dataset, including the data types and non-null counts.
   - It shows the first few rows of the dataset using `autos.head()`.
   - The column names of the dataset are printed using `autos.columns`.

2. **Data Cleaning - Renaming Columns:**
   - The script renames some of the columns using the `autos.rename()` function to ensure consistent and more readable column names.

3. **Data Cleaning - Dropping Columns:**
   - The script drops three columns ("seller", "offer_type", and "num_pictures") using `autos.drop()` to remove unnecessary information.

4. **Data Cleaning - Cleaning "Price" Column:**
   - The "price" column contains "$" symbols and is in string format. The script removes the "$" symbol using `autos["price"].str.replace()` to convert the prices into numeric values.
   - It converts the "price" column to numeric data type using `pd.to_numeric()` with the "coerce" option to handle any non-numeric values.

5. **Data Cleaning - Filtering "Price" Column:**
   - The script filters the "price" column using `autos[autos["price"].between(1, 350000)]` to keep only the car listings with prices between $1 and $350,000.

6. **Data Cleaning - Cleaning "Odometer" Column:**
   - The "odometer_km" column contains "km" symbols and is in string format. The script removes the "km" symbol using `autos["odometer_km"].str.replace()` to convert the values into numeric format.
   - The script also removes commas from the "odometer_km" values to ensure they are numeric.

7. **Data Cleaning - Filtering "Registration Year" Column:**
   - The script filters the "registration_year" column using `autos[autos["registration_year"].between(1910, 2016)]` to keep only the car listings with registration years between 1910 and 2016.

8. **Data Analysis - Brand Information:**
   - The script calculates the mean price and mean mileage for popular car brands. It identifies popular brands based on their percentage of occurrence in the dataset.
   - The brand information is stored in the `brand_info` DataFrame, which includes columns for mean mileage, popularity, and mean prices.

9. **Data Visualization and Summary:**
   - The script does not include specific data visualization or summary statistics output. However, it performs various data cleaning and preparation steps to facilitate further analysis and visualization.

**Note**

The provided code snippet is part of a larger data analysis process and may require additional steps or context to conduct a comprehensive analysis. For a complete understanding of the analysis, refer to the full script and the original dataset documentation.
