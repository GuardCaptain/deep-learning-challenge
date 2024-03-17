# deep-learning-challenge
For this challenge we are tasked with helping the nonprofit foundation Alphabet Soup develop a tool that can help select applicants for funding with the best chance of success in their ventures.
From Alphabet Soup's business team, we have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years.
We will be using our knowledge of machine learning and neural networks to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.



Overview of the analysis:
For our first model we created,  we started off by dropping the EIN and NAME columns and then binned together the value counts of the 'APPLICATION_TYPE' and 'CLASSIFICATION'. This would create a new bin called 'Others' which would help simplify the model. We then used our pd.dummies to encode categorical variables and then created our features and target array. Using the features and target array, we created our model and tested it using our hidden layers and activation functions. After all of this was done, we were able to get an accuracy of approximately 72%



OPTIMAZATION PROCESS
 In an attempt to optimize the function and achieve an accuracy of 75% or higher, the first thing I tried to do is create less bins in the application types and classification types. I did this because I thought maybe if we have more categories, it would increase our accuracy since we would have more information on the types. Therefore, I lowered the cutoff for the binning phase of those two categories to about half of the original value. This turned out to not improve the accuracy, and it stayed more or less the same.
 I then tried to remove a few columns. I thought maybe the columns 'USE_CASE' and 'SPECIAL_CONSIDERATIONS' were good candidates, as they didn't seem too important to the accuracy. After rerunning the model without those two columns, the accuracy again was more or less the same.
 Next, I tried changing the first and second hidden layers and their units. I decided to flip the their orders (i.e. first layer was 80 and second layer was 50, but now first layer is 50 and second layer is 80). I left the activation functions the same because I believe 'relu'  is the optimal activation for the hidden layers while would be optimal sigmoid for the output layer (because sigmoid is for outputs 1 and 0). This too turned out to not affect the accuracy as much.
 Lastly, I tried including the 'NAME' column into the model. I thought maybe the name of organizations might be important when taking charity into account because organizations may continue to donate multiple times to the charity (similar to loyalty of customers). I ran the NAME column through the same binning process as the APPLICATION_TYPE and CLASSIFICATION, taking the value counts of NAME with < 20 and putting them into 'Others'. After running the model, the accuracy finally broke the ceiling of 75%! It obtained an accuracy of 77%! 