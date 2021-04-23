# Balance-defaulter-classifier

I am interested in predicting whether an individual will default on his or her credit card payment, on the basis of annual income and monthly credit card balance. 


# Note:
The way I am writing these notebooks is somewhat different. I have few cells dedicated to the experiments that I perform to
play around my understanding of the python concepts. I have not deleted them because I thought other beginners might find
them useful. I have also added references about the "under the hood" stuff which I used while coding.



# Data Source: 

The data set is displayed below. I have plotted annual income and monthly credit card balance for a subset of 10,000 individuals. 

The Default data set.Left:The annual incomes and monthly credit card balances of a number of individuals. The individuals who defaulted on their credit card payments are shown in orange, and those who did not are shown in blue. Center:Boxplots of balanceas a function of default status. Right: Boxplots of incomeas a function of default status.

![index](https://user-images.githubusercontent.com/26453844/115777731-1b821600-a3cf-11eb-9643-a068463c1e6f.png)


Applying Logistic Regression (using sklearn library) on the dataset gives the following plot:

![LR](https://user-images.githubusercontent.com/26453844/115935598-fbc11f80-a4ac-11eb-8bb4-7fbe11e9e72b.png)



Another library which is more comprehensive for fitting logistic regression than sklearn is statsmodel. My favorite 
feature of statsmodel is the comprehensive summary reports that it provides which contains more inforfation than summary 
provided by sklearn. I will perform the same computation using statsmodel. 

![Screenshot_2021-04-24 Logistic Regression - Jupyter Notebook](https://user-images.githubusercontent.com/26453844/115935716-375be980-a4ad-11eb-8e22-5c7748620cbb.png)

As it can be seen that the value of the coefficient of student2 is positive which indicates that if you are a student then 
you are more likely to default.

# Multiple Linear Regression (Where we consider more than 1 feature)

![Screenshot_2021-04-24 Logistic Regression - Jupyter Notebook(1)](https://user-images.githubusercontent.com/26453844/115936010-bd783000-a4ad-11eb-8fb3-293cf66acba5.png)

The Coefficient of student2 -0.6468 shows that if a person is a student then he won't default, but we saw earlier that
this is not the case. This contradiction is because of a phenomenon called confounding. Balance and student are 
correlated, they were hiding behind income and balance. Consider it like this, suppose the student has some good 
income (maybe he is a post grad working somewhere) that could be th reason of him not defaulting. When we took multiple 
features into account then we see the actual correlation.

![Screenshot_2021-04-24 Logistic Regression - Jupyter Notebook(2)](https://user-images.githubusercontent.com/26453844/115936153-f57f7300-a4ad-11eb-9fc3-c12b023b9fd5.png)

![MLR2](https://user-images.githubusercontent.com/26453844/115936238-29f32f00-a4ae-11eb-9558-9584ed0e8405.png)


