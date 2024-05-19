# Alphabet Soup Funding Challenge 


## Background 
The nonprofit foundation <i>Alphabet Soup</i> wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With machine learning and neural networks, I'm using the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, I have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

- EIN and NAME—Identification columns
- APPLICATION_TYPE — Alphabet Soup application type
- AFFILIATION — Affiliated sector of industry
- CLASSIFICATION — Government organization classification
- USE_CASE — Use case for funding
- ORGANIZATION — Organization type
- STATUS — Active status
- INCOME_AMT — Income classification
- SPECIAL_CONSIDERATIONS — Special considerations for application
- ASK_AMT — Funding amount requested
- IS_SUCCESSFUL — Was the money used effectively

## Process

Data Preprocessing

- I dropped the EIN and NAME—Identification columns as they have no relevance to what we're evaluating
- I reduced the number of values in APPLICATION_TYPE and CLASSIFICATION by categorizing smaller segments into an "other" label.
- I expended categorial variables with pd.get_dummies()
- I'm using the IS_SUCCESSFUL column as our target for X
- I kept all of the other datapoints to be evaluated for Y
- I split the data into training ad testing datasets.
- I scaled the training and testing features using StandardScaler before fitting it to the model.

Compiling, Training & Evaluating

I created the first model based on the starter code's outputs. (Loss: 0.55914705991745, Accuracy: 0.7302623987197876)
I'd like to achieve a higher accuracy of 75%, so I created 3 variations in hopes of increasing the accuracy and reducing the loss.
Optimization Attempt 1 (Loss: 0.5743629932403564, Accuracy: 0.728396475315094)
Increase number of epochs from 100 to 200
Optimization Attempt 2 (Loss: 0.566865861415863, Accuracy: 0.728863000869751)
Increased nodes in layer one to 3 times the number of columns in dataset.
Increased nodes in layer two to 1/2 the number of nodes as layer one
Optimization Attempt 3 (Loss: 0.580244243144989, Accuracy: 0.7292128205299377)
Changed the number of nodes in layer one to 120
Changed the number of nodes in layer two to 90.
Added a third layer with 30 nodes.
