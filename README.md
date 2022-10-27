# Neural_Network_Charity_Analysis
A binary classifier that is capable of predicting whether applicants will be successful
## Overview
The purpose of this analysis is to help Alphabet Soup find applicants who would be the most successful if they were given funds by using a binary classifier.  With the CSV file given to us, of the 34,000 organizations that have previously received funding, we cleaned the data, created and trained a neural network model and finally optimized the model to find the best results.

## Results
Below are the results to the two-part analysis of this repository. First, 'Data Processing' and second, 'Compiling, Training, and Evaluating the Model'.

### Data Processing
- What variable(s) are considered the target(s) for your model?
  - The variable that is considered the target for this model is “IS_SUCESSFUL”. This variable tells us if the applicant was successful after they received funding from Alphabet Soup. 
- What variable(s) are considered to be the features for your model?
  - The variables that are considered features for this model are “APPLICATION_TYPE”, “AFFILIATION”, “CLASSIFICATION”, “USE_CASE”, “ORGANIZATION”, “STATUS”, “INCOME_AMOUNT”, “SPECIAL_CONSIDERATION” and “ASK_AMT”.
- What variable(s) are neither targets nor features, and should be removed from the input data?
  - The variable that were neither targets nor features, and have been removed from the input data are EIN and NAME – which are identification columns.

![drop_name](https://user-images.githubusercontent.com/107289345/198415322-09051dba-60fd-447e-86ba-f3a31aaa46ad.png)

![merged_dataframe](https://user-images.githubusercontent.com/107289345/198415361-8c07320b-fdb4-4a02-a7a7-b34c44434ee4.png)

### Compiling, Training, and Evaluating the Model

- How many neurons, layers, and activation functions were slected for the neural network model, and why?
  - We selected 80 neurons for the first hidden layer and used the ReLu activation function. In the second hidden layer, we used 30 neurons and again used the ReLu activation function. Lastly, the output layer used the activation function Sigmoid. These amounts of neurons, layers and activation functions were chosen just as a starting point for the model
- Were we able to achive the target model performance?
  - We did not achieve the target model performance accuracy higher than 75% The accuracy that we were able to achieve was 70%. 

![moduel_2](https://user-images.githubusercontent.com/107289345/198415766-f4b6ac96-431e-4d20-82b2-b1fbcc5f9c02.png)

- What steps were takend to try and increase model performance?
  - We did three different attempts to increase the model accuracy percentage to reach above 75%. 
    - In the first attempt, we took the ASK_AMT column and created a cutoff point (of 5000) and bined the other categorical variables together in a new column, 'Other'. I kept the same neurons, layers and activation functions. However, the accuracy percentage was lowered to 60%.
    
    ![attempt_one](https://user-images.githubusercontent.com/107289345/198416028-127b8737-f3c5-47ed-a99c-23192207ea8a.png)

    - The second attempt, I decided to drop two more columns, 'AFFILIATION' and 'ORGANIZATION'. Lowered the neurons, to 60 for the first layer and 20 for the second layer. Kept the same amout of layers and same activation functions. The accuracy percentage was lowered to 50%. 
    
    ![attempt_two](https://user-images.githubusercontent.com/107289345/198416000-1d83e24c-bc48-4e3a-8896-ef73c2f8521f.png)

    - The 3rd attempt, I changed the number of neurons, layers and activation functions. 80 neurons in the first layer, 30 in the second layer and 20 in the third layer. I change the first activation function to 'tanh', the second and third layers to 'relu' and the output layer stayed the same with 'sigmoid'. However, the accuracy percentage did not achieve 75%, it was 54%. 
    
    ![attempt_three](https://user-images.githubusercontent.com/107289345/198415851-4b044c23-c389-4644-89fb-1695dca97cd1.png)

## Summary
  
  In summary, the overall results were okay when using the deep learning model. However because this dataset is not overly complex we could use the Random Forest classifier. I would recommend Random Forest because it could be useful when it comes to outliers, especially in the ASK_AMT column. It could also be helpful when it comes to asking whether or not any other classifiers are of any importance to the overall outcome. 
