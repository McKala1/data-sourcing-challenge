# data-sourcing-challenge

# Project README

Hey there! 👋 I just finished working on a cool project where I retrieved movie reviews from The New York Times API and gathered additional details from The Movie Database API. Here's a rundown of how I went about it:

## Part 1: Retrieve Movie Reviews from New York Times API

### Step 1: Setting Up
I kicked things off by creating an empty list called `reviews_list` to store the reviews from the API.

### Step 2: Getting Reviews
Since the Article Search API limits results to 10 per page, but I wanted 200, I set up a loop to go through 20 pages. Inside the loop, I extended the `query_url`, made GET requests, and stored JSON data in a variable called `reviews`. I also added a 12-second interval between queries to stay within API limits.

### Step 3: Processing Reviews
I added a try-except clause to handle potential issues. In the try block, I looped through the reviews and appended each one to the list. If there were no results on a page, I printed the page number and broke out of the loop.

### Step 4: Data Wrangling
After retrieving the reviews, I previewed the first five in JSON format and converted the `reviews_list` to a Pandas DataFrame using `json_normalize()`. I also extracted movie titles and keywords, preparing the data for the next steps.

## Part 2: Access The Movie Database API

### Step 1: Building Query URLs
I consulted The Movie Database API documentation to build query URLs. Prepared the query URL with the movie title and API key.

### Step 2: Retrieving Movie Details
I created an empty list called `tmdb_movies_list` to store API results. Set up a request counter to keep track and added a sleep interval after every 50 requests. In a loop, I queried The Movie Database, collected movie details, and stored them in `tmdb_movies_list`.

### Step 3: Data Cleanup
I previewed the first five results in JSON format and converted them into a Pandas DataFrame called `tmdb_df`. 

## Part 3: Merge and Clean the Data for Export

### Step 1: Merging DataFrames
I merged the New York Times reviews and TMDB DataFrames based on the movie titles.

### Step 2: Cleaning Up
I cleaned up the data by converting list columns to strings and removing unwanted characters. Finally, I deleted any duplicate rows and reset the index.

### Step 3: Wrapping Up
I exported the cleaned data to a CSV file without the DataFrame's index, ready for future use.

And that's a wrap! 🚀 The project was a fun journey from fetching reviews to gathering movie details. Cheers to data exploration! 🎉