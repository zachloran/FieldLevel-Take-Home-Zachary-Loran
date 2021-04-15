# Entry Level Data Analyst Take Home Project

## Purpose
The goal of this project help us understand your data analyst abilities.
We are providing you real datasets to explore which are drawn from FieldLevel applications.
We do not expect you to spend more than four hours completing the exercise.

To complete the goal you should setup your system as described below and then edit the file Exercise.ipynb in a web browser using jupyter notebooks.

## Setup
#### Get the data and project code
1. Import the exercise repository to your personal Github account. Using github's import tool (https://github.com/new/import) import this url: https://github.com/FieldLevel/fieldlevel-entrylevel-da-take-home
1. Invite our github user "fl-codereview" to be a collaborator on your new repository
1. Get your new repository on your local machine

#### Run the programming environment
Before you start the exercise you'll need to get python 3 running and a jupyter server notebook.
The fastest way to do that on my mac was:

1. Install anaconda (https://docs.anaconda.com/anaconda/install/)
1. Navigate to repository in a console
1. Run `jupyter notebook`
1. Open webrowser (if it didn't open automatically) and navigate to http://localhost:[8888]/notebooks/Exercise.ipynb where [8888] is the port jupeter is running on.
1. Import the pandas library into the the first cell of the jupyter notebook and then load the datasets email_data.csv and activity_data.csv via the read csv function. The datasets are pipe '|' delimited. Display the head of the dataframes. If you see something that looks like this you are setup and ready to start the exercise:

![Complete Setup](docs/SetupCompleteScreenShot.png)

## Exercise
In this exercise we imagine you are working as the data analyst on a product team along side a product manager, developers, and designers. The team is looking to improve features related to the emails we send to our users. To that end, the team is thinking it would be good for you review data related to emails we have been sending lately. They hope you will be able to answer some basic questions the group brainstormed at the project kickoof.

### About the datasets
Before you start your analysis, first review the descriptions of the datasets below to make sure you understand the data. If you have any questions about the meaning of a column contact us.
#### Dataset: email_data.csv
This is dataset contains samples of the emails we have sent over the last year or so. Each row represents an email that was sent to a user. This dataset represents a small fraction of the emails we have sent over the time period covered by the data.

Column Name | Description
--- | ---
LogId | A unique number used to represent each individual email that was sent
EmailSentDateTimeUtc | The date and time the email was sent in coordinated universal time
EmailCampaignId | A unique number used to represent each email campaign. Multiple users can recieve emails multiple times from the same email campaign.
EmailOpenedDateTimeUtc | The date and time the email was opened. Null if the user did not open the email
EmailClickedDateTimeUtc | The date and time the a link in the email was clicked by the user. Null if the user did not click any links in the email.
UserId | A unique number used to represent each user
AddressData | A string in JSON format. May be null as not all users have provided an address. The field contains the 5 digit zip code of an address the user provided. Note the format of the JSON object varies. A zipcode will always be identified by the key 'ZipCode'. Some 'ZipCode' keys are duplicated. Some have null values. Some are preceeded by extranious letters.

#### Dataset: activity_data.csv
This is dataset contains a daily log of user activity. If any user represented in the email_data was active on a day during the period covered by the email there will be a row in activity_data. If no row is present for a given UserId and date, you can assume that UserId was not active on that date. 

Column Name | Description
--- | ---
UserId | A unique number used to represent each user
DateOfActivityPST | A date a user made an authenticated request to our servers in pacific standard time.


### Questions
For each question below create a new code cell in the Exercise.ipynb notebook. Start the code cell with a comment indicating the question it is answering. Then write and execute the code you feel is required to answer the question. Finally, if the question requires it print a _brief_ response (1 or 2 sentences) summarizing your answer.
1. How many rows are in the two datasets? (use python to print the number and display it nicely with commas)
1. What are the earliest and most recents dates of emails sent in this dataset in California time? (use python to print the date in format mm/dd/yyy hour:minute in 24 hour time)
1. How many users got at least 1 email each month? Based on this monthly series of data, what
1. If the log of emails represents 1% o
1. PM is thinking we may be sending too much email. Is there a campaing that we should consider no longer sending? (e.g. its performance has never been good)