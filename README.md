# Putting Vietnamese cuisine on the map
New York restaurants catch the eye of the Michelin Guide

## Data
Data analysis can be found in analysis.ipynb

| Filename | Description |
| :----------- | :----------- |
| restaurant.csv | Vietnamese restaurants in the Michelin Guide |
| restaurant_info.csv | Info pages of each Vietnamese restaurant |
| cuisines.csv | Restaurants by cuisine type |
| ingredients.csv | Ingredients list for horizontal bar chart |
| clean-falansai.csv | Menu of Falansai |
| clean-thai-so'n.csv | Menu of Thai-so'n  |
| clean-di-an-di.csv | Menu of Di An Di |
| clean-van-da.csv | Menu of Van da |
| clean-bolero.csv | Menu of Bolero |

## Relevant figures

### Number of restaurants in the guide
- Search for an empty string: https://guide.michelin.com/en/search?type=restaurant&q=
- As of June 24, there were 15,928 restaurants listed in the guide

### Number of Vietnamese restaurants in the guide
- Search the keyword "Vietnamese": https://guide.michelin.com/us/en/search?type=restaurant&q=vietnamese

### Number of U.S. restaurants in the guide
- Using BeautifulSoup, scrape all the Vietnamese restaurants
- Get the version of the guide the restaurant appeared, i.e. Michelin Guide USA

### Number of New York restaurants in the guide
- Get the city using BeautifulSoup, i.e. New York

### Restaurants by type
- There is a dropdown menu containing cuisine types and the number of each type: https://guide.michelin.com/us/en/restaurants
- The sum of restaurants by cuisine is greater than the total number of restaurants, likely due to some restaurants being in multiple categories

### Percent of Vietnamese restaurants in the guide
- (Vietnamese restaurants / Total restaurants in the Michelin Guide) * 100
- (37 / 19528) * 100

### Number of times a dish appears on the menu
- Standardize / simplify the names of the dishes
- Count how many times a dish appears
- Some dishes can be the same thing with an English name and the Vietnamese name

### Number of times an ingredient appears on the menu
- Combine the name of the dish and the description(s) of the dish into a string
- Comma delimit every ingredient in the string
- Remove all descriptors such as "spicy"
- Keep all descriptors that would make it a different ingredient such as "Vietnamese mortadella"
- Count how many times an ingredient appears

## Charts

### Key ingredients
https://datawrapper.dwcdn.net/4c75z/6/

## What I learned / Challenges
- A menu is not a table, it's actually just a list of text
- Menus come in all shapes and sizes and are not at all consistent between restaurants
- When scraping some of the tools struggled with diacritics that commonly appear in Vietnamese
- Each restaurant often have 3-4 smaller menus that need to be scraped and merged, i.e. Lunch, Dinner, Drinks, Wine
- Some restaurants did not a link to their website, a menu that could be downloaded or a header image in the guide
- Some restaurants did appear in the guide, but did not have a Bib Gourmand or at least one Michelin star
- Getting the ingredients from the dishes was a very manual process of splitting a string into its individual parts
- There was an issue when using scrollama and overlapping text that immediately follows the scrolling section
- Data on when a restaurant opened was hard to find
- The number of restaurants in the guide changes
- It can be hard to tell if a restaurant that was previously on the list is still on the list, i.e. La Maison 1888
- Some restaurants are a copy of the original ones awarded a Michelin star, i.e. Jardin Des Sens Saigon
- An item can be served in various sized portions, which needed to be consolidated into one single row
- An item can have a vegetarian option, which needed to be treated as its own separate item
- An item description highlights notable ingredients, but does not list every ingredient used in the dish

## Other notes
- Sanity checks revealed issues with the scraping of the menus and how much more cleaning needed to be done
- I moved from Jupyter Notebook to Google Sheets to create clean .csv file for each restaurant
- I would have liked to expand this analysis for all 37 Vietnamese restaurants in the Michelin Guide
- Did not include wines, but kept other drinks such as beer, cocktails or mocktails
- With a smaller sample size of five New York restaurants vs all 37 restaurants, it can skew the popularity of dishes / ingredients
