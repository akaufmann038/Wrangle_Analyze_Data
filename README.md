# Wrangle_Analyze_Data
Project on wrangling, cleaning, and analyzing Twitter archive data

0.1 Gathering from Twitter Archive
Firstly, I gathered twitter archive data from the csv file, ‘twitter-archive-enhanced.csv’. This was completed by using the pandas read_csv operation and loading it into a dataframe called df_twitter_archive.

0.2 Gathering from URL
I gathered the image predictions data programatically from a provided URL. I used the requests library to get the data from the URL and I stored this data in the response variable. Then, I opened the file, ‘image_predictions’ in the current directory and wrote all the content from the response data into the opened file. Finally, I read the data from ‘image_predictions’ into a dataframe, df_image_predictions, using pandas read_csv. The data in the tsv file was separated with an arrow-like character, so I specified this using the sep argument in pd.read_csv.

0.3 Gathering from Twitter API
I gathered data related to retweet count and favorite count using twitter’s API. Firstly, I set up my twitter developer account and received a key, consumer secret, access token, and access secret. Then, I used tweetpy to create an api object. Next, I iterated over the tweet id column in df_twitter_archive since I wanted the retweet count and favorite count for every tweet in the archive dataset. In every iteration, I accessed the tweet data and set it equal to the tweet variable. Then I accessed the json data from the tweet variable and added this to a list called tweet_data.
I then opened a new file in the current directory called tweet_json.txt. I iterated over each data object in tweet_data and dumped each data object into tweet_json.txt, making sure each data object was separated by a new line.
Finally, I was to create a dataframe from the data in tweet_json.txt. I opened tweet_json.txt and iterated over each line of the file. In every iteration, I accessed the tweet id, retweet count, and favorite count from the text data using regular expressions. I then added these three variables to a df_list (a list I created to keep track of data accessed from text document) in the form of a dictionary. After the iteration, I converted the list of dictionaries into a dataframe called df_twitter_api.
