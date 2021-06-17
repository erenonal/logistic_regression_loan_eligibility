# About Loan Eligibility Prediction

Dream Housing Finance company deals in all home loans. They have a presence across all urban, semi-urban, and rural areas. Customer-first applies for a home loan after that company validates the customer eligibility for a loan.

# About Implementation

Using the `Logistic Regression` algorithm, I made a loan eligibility prediction by customers status which are showing below.

The explanations of the codes are also written as a comment line in detail, but I will write the operations I have done.

After defining the libraries we use, we read our file. We have two splitted datasets as `loan_test` and `loan_train`. I defined the reading patterns for the colab environment and for the local environment.

To familiarize myself with the dataset, I took a look at the variable names and types.

In the exploratory data analysis part, I observed the distribution of the Gender and Married attributes with Loan_Status

I made a pairplot with the Seaborn library to see its distribution with other features.

There seems to be a correlation between the variables ApplicantIncome and LoanAmount with Loan_Status. When I visualized it with the scatter plot, I saw that it wasn't.

Then I visualized the relations of `Education` , `Property_Area` variables with `Loan_Status`

I defined a function named `explore_object_type` . With this function, I selected only the categorical variables among all the variables, and with the for loop, I observed which classes these categorical variables are divided into and their number.  I found that 5 of our categorical variables had 2 classes, 1 had 3 and 1 had 4 classes. 

I observed the missing values in all the variables and then filled the missing values with mode() for the `Credit_History`  and the mean() for the `LoanAmount` features.

Our target variable (Loan_Status) classes were categorical as Y/N. Likewise, the variables 'Gender', `Married` and `Employed` were categorical variables with 2 classes. I changed them all to 1-0 and filled missing values with thier mode and mean values.

I applied the Label Encoding method because the `Property_Area`, `Education`,`'Dependents` columns have more than 2 classes.

At the end of these operations, all our variables became numeric variables. Now we can look for correlation map.

Before fitting the model, We need to decide how many feature are available for testing and training, then after complete this step. I fitted the model.

Currently, we are using Credit_History', 'Education', 'Gender features for training so let's create train and test variables 

I checked the coefficeints of the trained model with `logistic_model.coef_` and checked the intercept of the model with `logistic_model.intercept_`.

In the end, we found our accuracy score of 80%.

# About Dataset
The company wants to automate the loan eligibility process (real-time) based on customer detail provided while filling the online application form. These details are Gender, Marital Status, Education, Number of Dependents, Income, Loan Amount, Credit History, and others. To automate this process, they have given a problem to identify the customer's segments, those are eligible for loan amount so that they can specifically target these customers. Here they have provided a partial data set.

Loan_ID : Unique Loan ID.

Gender : Male/ Female

Married : Applicant married (Y/N)

Dependents : Number of dependents

Education : Applicant Education (Graduate/ Under Graduate)

Self_Employed : Self-employed (Y/N)

ApplicantIncome : Applicant income

CoapplicantIncome : Coapplicant income

LoanAmount -: Loan amount in thousands

Loan_Amount_Term : Term of a loan in months

Credit_History : Credit history meets guidelines

Property_Area : Urban/ Semi-Urban/ Rural

Loan_Status : Loan approved (Y/N)

CoapplicantIncome : Coapplicant income

LoanAmount -: Loan amount in thousands

Loan_Amount_Term : Term of a loan in months

Credit_History : Credit history meets guidelines

Property_Area : Urban/ Semi-Urban/ Rural

Loan_Status : Loan approved (Y/N)

