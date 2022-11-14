# Data_Wrangling_Project
Twitter_WeRate_Dogs_Wrangling
This wrangling effort followed the data wrangling mehodology best practice in carrying out this project which is:

Gather
Assess
Clean
Gather
Data was gathered from three major sources (csv - archive, tsv - Image and a json file - API) containing different variables. The data was gathered and each line was read from the json file, appended three relevant fields (tweet_id, retweet_count and favorite_count) which were relevant to the completion of the project and then read in a dataframe. I could not get my developer elevated request approved by twitter. I had to rely on the json text provided in the classroom environment by udacity.

Assess
The Gathering phase resulted in creating three dataframes which were then assessed visually and programmatically. I used the sample or head function to have a quick look into the data in each dataframe.

A better deep dive into the dataframes was done programmatically using the info, describe and removing duplicates where necessary.The objective of this assessment is to identify structural (Tidiness) and Quality issues with the data for appropriate remediation.

Generally, about 11 data quality issues were identified across the 3 dataframes ranging from completeness, consistency, accuracy and validity. Furthermore, 3 tidiness issues were identified majorly around storing single observation in multiple tables.

Quality issues
The in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id & retweeted_status_id_timestamp needs to be dropped, filter to only tweets and keep only the NaN values.

Extract the real dog names from text and get rid of (a, an, just, ....etc) values.

Some Values in rating_denominator don't equal 10

The values of the source column and the dog stage can be presented in a more useful form

There are less tweets in the image_predictions than the ones in twitter_enhanced

We should have only 2097 rows

Values of rating_denominator must be 10 and it's multiples, other values should be dropped

Extract Tweet's link from text

Use regex to extract the source (Twitter for iPhone, Twitter Web Client, or TweetDeck) from source column

Change the datatype of timestamp to datetime

Change the datatype of tweet_id to string in the 3 dataframes

Tidiness issues
The nine(9) columns under image_predictions can be presented in more clear form

There are less tweets in twitter_api than the ones in twitter_enhanced and much more than the ones in image_predictions

Single Observation is stored in multiple tables. The three dataframes should be merged on tweet_id

Clean
The identified issues were cleaned using the DCT methodology which is:

Define
Code
Test
Summarily the following cleaning activities were carried out:

Quality Issues:
I droped the non NaN values in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id & retweeted_status_timestamp after filtering them to only tweets in twitter_archive_enhanced
Changed the datatype of tweet_id to string in the 3 dataframes (twitter_archive_enhanced, image_predictions, twitter_api).
Changed the datatype of timestamp to datetime in twitter_enhanced.
Found a way to represent the dog stage in more useful form in twitter_enhanced.
Renamed 'p1', 'p1_conf', 'p1_dog', 'p2', 'p2_conf', 'p2_dog', 'p3', 'p3_conf', 'p3_dog' to more descriptive headers in image_predictions.
Used regex to extract the source (Twitter for iPhone, Twitter Web Client, or TweetDeck) from source column in twitter_enhanced
Extracted the Tweet's link from text in twitter_enhanced
Extracted the real dog names from text and get rid of (a, an, just, ... etc) values in twitter_enhanced
Noted some values in rating_denominator don't equal 10, and created a column to represent the dog rating regardless to the denominator in twitter_enhanced
Made sure we had only tweets before Aug. 2017
Included only tweets with images and drop NaN values of expanded_url in twitter_enhanced
Tidiness Issues:
The 9 columns of predictions were presented in a clearer form.
The dataframes twitter_enhanced, image_predictions and twitter_api were merged on tweet_id.
