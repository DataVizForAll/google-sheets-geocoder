# Google Sheets Geocoder
Geocode addresses into latitude/longitude coordinates inside Google Sheets,
with US Census or Google Apps service.

## UPDATE
To geocode multiple addresses inside your spreadsheet, we now recommend that beginniners install a free Google Sheets Add-on called [Geocoding by SmartMonkey](https://gsuite.google.com/marketplace/app/geocoding_by_smartmonkey/1033231575312), instead of the Google Apps Geocoder script below.

See geocoding instructions in *Hands-On Data Visualization* chapter 2: https://handsondataviz.org/geocode.html




## Demo Geocoder US Census or Google
- Geocode locations into latitude, longitude, with source and match quality, inside a Google Sheet
- Go to Google Sheet template, sign in to your account, and File > Make a Copy to your Google Drive https://docs.google.com/spreadsheets/d/1XvtkzuVyQ_7Ud47ypDJ4KOmz_5lOpC9sqeEDBbJ5Pbg/edit#gid=0
- Insert locations, select 6 columns, and select Geocoder menu: US Census or Google (limit 1000 daily per user)
- Google Sheets script will ask for permission to run the first time

![Screencast](google-sheets-geocoder-census-google.gif)

## Demo Geocoder US Census Geographies
- Geocode US addresses into latitude, longitude, GeoID census tract, inside a Google Sheet
- Go to Google Sheet template, sign in to your account, and File > Make a Copy to your Google Drive
https://docs.google.com/spreadsheets/d/1x_E9KwZ88c_kZvhZ13IF7BNwYKTJFxbfDu77sU1vn5w/edit#gid=0
- Insert locations, select 8 columns, and select Geocoder menu: US Census 2010 Geographies
- Google Sheets script will ask for permission to run the first time

![Screencast](google-sheets-geocoder-census-geographies.gif)

#### About 15-character GeoID
- Make sure that column G is formatted as text (to preserve leading zeros), not number
- Break down a sample GeoID: 090035245022001
  - state = 09
  - county = 003
  - tract = 524502 = 5245.02
  - block group = 2
  - block = 001

## How to insert script into any Google Sheet
  - Download or fork the Google Sheets scripts (.gs) from this GitHub repo
  - Go to your Google Sheets > Tools > Script Editor
  - File > Create New Script File
  - Copy and paste contents of your preferred script (such as geocoder-census-google.gs)
  - Save as Code.gs (or save, then rename to geocoder-census-google.gs)
  - Refresh your Google Sheet and look for new Geocoder menu

## See also: Batch upload to US Census
- Available at US Census Geocoder https://geocoding.geo.census.gov/geocoder/
- Upload up to 1000 rows
  - Find Locations using > Address Batch (returns latitude, longitude coordinates)
  - Find Geographies using > Address Batch (returns lat, lng, census geographies)
- Upload CSV table with up to 1000 rows for faster processing, in this format:

| AnyID  | Street | City | State | Zip |
|:----- |:----- |:--- |:---- |:--- |
| 1     | 300 Summit St  | Hartford | CT | 06106 |

## Learn more
- **Hands-On Data Visualization** book, see *Transform Your Data* chapter, https://HandsOnDataViz.org/

## Credits
- Developed by [Ilya Ilyankou](https://github.com/ilyankou) and [Jack Dougherty](https://github.com/jackdougherty) with support from Trinity College CT, for [Hands-On Data Visualization](https://HandsOnDataViz.org/)
- Inspired by Google Sheets Geocoding Macro (2016) https://github.com/nuket/google-sheets-geocoding-macro (no license)
- Geocoding services:
  - US Census Geocoder https://geocoding.geo.census.gov/geocoder/
  - Geocode with Google Apps: The Maps Service of Google Apps allows users to geocode street addresses without using the Google Maps API, limit 1,000 searches daily per user, https://developers.google.com/apps-script/reference/maps/geocoder



### Testing
- Geocoder-with-Mapzen.gs -- need to focus search within a country or prioritize area https://mapzen.com/documentation/search/search/#search-within-a-particular-country
