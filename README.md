# deep-learning-challenge
Module 21 Challenge


## Overview
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With machine learning and neural networks, we have created a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

The dataset in CSV format contains data from more than 34,000 organizations that have received funding from Alphabet Soup over the years.


## Results
### Data Preprocessing

1. **What variable(s) are the target(s) for your model?<br>**
The target variable in my model is the `IS_SUCCESSFUL` column from the dataset, which indicates whether the organization used the funding effectively (1) or not (0).

   Another potential target variable that I haven't focused on is `STATUS`:
      - The `STATUS` column reflects whether the organization is active or not.
      - If I were to redo this analysis, I would consider using both `IS_SUCCESSFUL` and `STATUS` as target variables.
      - This approach could lead to a more comprehensive model, helping the nonprofit foundation not only predict if the funding will be used effectively but also whether the organization will remain active.

2. **What variable(s) are the feature(s) for your model?**<br>
   The dataset includes the following columns:
      - `EIN` and `NAME—Identification` columns
      - `APPLICATION_TYPE`—Alphabet Soup application type (due to the number of unique values within this column, the values have been categorized into a category named "Other" if the value is < 528)
      - `AFFILIATION`—Affiliated sector of industry
      - `CLASSIFICATION`—Government organization classification
      - `USE_CASE`—Use case for funding
      - `ORGANIZATION`—Organization type
      - `STATUS`—Active status
      - `INCOME_AMT`—Income classification
      - `SPECIAL_CONSIDERATIONS`—Special considerations for application
      - `ASK_AMT`—Funding amount requested
      - `IS_SUCCESSFUL`—Was the money used effectively

3. **What variable(s) should be removed from the input data because they are neither targets nor features?**<br>
   There are two variables that were removed from the dataset due to being neither targets nor features. 
         - `EIN` (a reference number given to each organization)
         - `NAME` (the name of the organizations)

### Compiling, Training, and Evaluating the Model
4. **How many neurons, layers, and activation functions did you select for your neural network model, and why?**<br>
    - `AlphabetSoupCharity.H5` and `AlphabetSoupCharity_Optimazation.H5`
        - For the initial model I chose to run three layers:
            - Input Layer - `80` Nodes - `Relu` Activation
                - I chose to run 80 nodes for this layer due to the number of dimensions within the dataset (42)
            - Hidden Layer - `30` Nodes - `Relu` Activation
                - 30 Nodes was selected for this layer, again due to the number of dimensions within the dataset
            - Output Layer - `1` Node - `Sigmoid` Activation
        - The initial model resulted in:
            - Accuracy: `72.61%`
            - Loss: `0.5741`

5. **Were you able to achieve the target model performance?**<br>
    - No, the accuracy scored at `72.62%` and a loss value of `0.5741`.

6. **What steps did you take in your attempts to increase model performance?**<br>
    - I used the `Keras_tuner` library to test the performance.


## Summary
The deep learning model achieved an accuracy of approximately 73% on a dataset with multiple dimensions and some complexity. While this fell short of the target accuracy of 75%, the optimization led to a reduction in the number of neurons required, with only one additional layer needed compared to the initial model.

