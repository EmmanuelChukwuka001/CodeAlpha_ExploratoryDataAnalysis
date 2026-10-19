
# Nigerian Equipment Marketplace Listing and Price Analysis

## 1. Project Objective
Collect publicly available equipment listings from the Nigerian
Equipment Marketplace and explore their categories, locations,
conditions, and advertised sale and rental prices.

## 2. Data Source
Website: https://equipmentmarket.ng/
Data was retrieved from the website's listings API.

## 3. Data Collection
- Used Python and the requests library to retrieve listing data.
- Retrieved approved listings through paginated API requests.
- Added a 1-second delay between page requests.
- Collected 245 listings across equipment and service types.

## 4. Data Preparation
- Converted the API response into a pandas DataFrame.
- Selected equipment listings, excluding service listings.
- Retained 158 equipment listings for analysis.
- Selected relevant listing, category, location, condition,
  availability, date, and price fields.
- Converted price fields to numeric values where possible.
- Preserved missing prices as missing values rather than zero.
- Added price-availability flags and sale-price status labels.
- Standardized location text and assigned broad regions.
- Checked listing IDs and investigated repeated titles without
  automatically deleting records.

## 5. Privacy and Data Quality
- Seller contact and owner fields were removed at collection, before
  the raw data was saved.
- Excluded contact details from the analysis-ready export.
- Excluded the views field from the export and conclusions because
  the website's view-count behavior may artificially boost values.
- Retained potential sale-price outliers for analysis.
- Recorded missing prices, repeated titles, and rental-price
  patterns as observations rather than confirmed errors.

## 6. Output
Saved a cleaned CSV containing 158 equipment listings and
21 analysis-ready columns.

## 7. Limitations
- The dataset represents listings available at the time of collection.
- Advertised prices are not necessarily completed transaction prices.
- Seller-stated condition and listing details were not independently
  verified.
- Rental prices are available for only a small subset of listings.
- Similar titles do not prove that listings are duplicates.
- Regional groupings are based on text in the supplied locations.


## 8. Key Findings

### Listing Categories
Transport & Logistic was the largest category, with 32 listings (20.25%).
Construction & Infrastruture followed with 26 (16.46%), and
Agriculture & Mining had 21 (13.29%). Together, these three categories
accounted for 50% of the 158 equipment listings.

### Geographic Distribution
Lagos accounted for 84 listings (53.16%), while Abuja / FCT accounted
for 65 (41.14%). Together, these regions represented 94.30% of the
sample. This describes the collected listings and does not establish
market demand or total equipment availability in Nigeria.

### Equipment Condition
There were 78 listings marked Used - Excellent (49.37%), 73 marked
Brand New (46.20%), and 7 marked Used - Good (4.43%). These conditions
were reported in the listings and were not independently verified.

### Sale Prices
Of 158 listings, 119 had an advertised sale price and 39 did not.
Among listings with prices, the median was NGN 6,000,000 and the mean
was approximately NGN 30,242,195. The mean being substantially higher
than the median suggests that high-priced listings influence the
average. The observed price range was NGN 10,000 to NGN 392,450,000.

Six sale prices were flagged as potential outliers (above
NGN 105,410,000) using the interquartile-range method. They were
retained because unusual prices are not automatically errors.

### Rental Prices
Daily rates were available for 15 listings, while monthly and annual
rates were each available for 14 listings. This limited coverage
restricts the conclusions that can be drawn about rental pricing.

### Data Quality
The verification status field was blank for all 158 listings, and the
minimum lease field was blank for 88.0%, so neither can support
analysis. Only 4 listings (2.5%) lacked a subcategory. A total of 29
listings (18.4%) showed no price in any of the four price fields.

### Rental Rate Pattern
Of the 14 listings showing both a daily and a monthly rate, 12 had a
monthly rate almost exactly 162 times the daily rate (median ratio
162.0, maximum 182.5), not the 30 times a simple 30-day month would
give. This suggests the monthly rates may follow a fixed formula,
which this data cannot confirm. Rental rates should be compared within
the same rate type, not converted between daily and monthly.

### Interpretation
The analysis summarizes advertised equipment listings collected at
the time of scraping. It does not measure completed transactions,
market demand, or the full Nigerian equipment market.
