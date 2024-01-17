# SuperKart_Linear_Regression
## For this project, I build a regression model for sales predictions.


#Objective:
SuperKart is an organization that owns a chain of supermarkets and food marts providing a wide range of products. It wants to predict the future sales revenue of its different outlets to strategize its sales operation across different tier cities and plan its inventory accordingly. To achieve this purpose, SuperKart has hired a data science firm, shared the sales records of its various outlets for the previous quarter, and asked the firm to develop a suitable model to predict the total sales of the stores for the upcoming quarter.

# Data Description:
The data contains the different attributes of the various products and stores. The detailed data dictionary is given below.

- Product_Id - unique identifier of each product, each identifier having two letters at the beginning followed by a number.
- Product_Weight - the weight of each product
- Product_Sugar_Content - sugar content of each product like low sugar, regular, and no sugar
- Product_Allocated_Area - the ratio of the allocated display area of each product to the total display area of all the products in a store
- Product_Type - broad category for each product like meat, snack foods, hard drinks, dairy, canned, soft drinks, health and hygiene, baking goods, bread, breakfast, frozen foods, fruits and vegetables, household, seafood, starchy foods, others
- Product_MRP - maximum retail price of each product
- Store_Id - unique identifier of each store
Store_Establishment_Year - the year in which the store was established
- Store_Size - the size of the store depending on sq. feet like high, medium, and low
- Store_Location_City_Type - the type of city in which the store is located, such as Tier 1, Tier 2, and Tier 3. Tier 1 consists of cities where the standard of living is comparatively higher than its Tier 2 and Tier 3 counterparts.
- Store_Type - the type of store depending on the products that are being sold there like Departmental Store, Supermarket Type 1, Supermarket Type 2, and Food Mart
- Product_Store_Sales_Total - total revenue generated by the sale of that particular product in that particular store.

## Inspect the distribution of the continuous variables


![carbon (16)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/bbd11c75-c4dd-4fb3-8a52-5500d9caa6a5)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/5be0bf1d-20af-41fc-b0a7-0ef791ac16f1)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/f317bb08-5457-4383-91ab-5e4ddd7de11b)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/b8866ea2-1bf0-4fed-be64-391631384dfe)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/7c33ceab-bdc0-4634-9be7-83466356379e)

### All but one of the continuous variables are normally distributed. The product allocated area is right skewed. This could be due to the fact that some large products require a larger display area.

## Inspect the categorical variables

![carbon (17)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/f288a18d-7d61-420e-a038-c32ea3feb4a5)


![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/359c3860-e369-4f4b-8ead-0a23397f8aeb)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/80d34677-ef09-40af-b896-0974f740898a)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/8932e244-52e8-429e-829b-36d0c1074e03)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/d196a34d-62df-40cd-a604-4adfa51f024f)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/4cddb374-711e-4180-82f4-e3c52257ded3)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/5d299d0e-f3a8-46f6-8dfb-2105b4104394)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/4aef1dcc-bb34-4075-a10b-8c921934027b)

- ### Low-sugar products are the most popular. This makes sense because later, you will see that fruits and vegetables are what people buy most.
- ### Fruits and vegetables, snack foods, frozen foods, dairy, and household goods are the top 5 products.
- ### Store_Id - unique identifier of each store Store_Establishment_Year - the year in which the store was established. OUT004 should be the stores established in 2009. More stores were established this year. You see this in the year-established graph.
- ### Medium-sized stores have the most stores.
- ### Tier 2 has the most stores.
- ### Supermarket type 2 has the most stores.
- ### Supermarket type 2 and OUT004 are probably the same. This would indicate that supermarket type 2 was established in 2009. The store type and the year established have a 1:1 mapping.

  ## Inspect the correlation of the continuous variables

  ![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/1f96a61e-2977-4691-afeb-4533712209d6)

- ### Product weight and Product MRP are highly correlated with product store sales totals, which is the target variable.
- ### Product weight and product MRP have a strong correlation as well.
- ### Everything else does not correlate.


## Bivariate analysis. Inspect categorical variables vs. target variable product store sales totals.

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/416cdef5-f2f7-4f6f-8e39-5decd1e922ed)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/63bea240-6672-406d-9aa6-de6ed6cd5dec)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/686db28e-5818-404f-9c87-0f5653d930bf)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/8e0ab937-6592-4eda-a5ff-d98fc13dac50)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/0e0ff374-9763-409d-8e3d-8c43b77674c9)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/9a2f6183-8a5b-4e02-993c-d10db27f790c)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/b48f9c49-5b5c-43de-947e-949073383344)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/81a236d4-7890-4f31-aa35-57ccd6e56ff8)

### Here are the things that generate the most revenue:
- ### Food items
- ### Low-sugar items
- ### Fruits and Vegetables and Snack foods
- ### Store id OUT004
- ### The year 2009 (This is the year they had the most expansion)
- ### Medium sized stores
- ### Tier 2 stores
- ### Supermarket type 2


## Inspect the distribution of the continuous variables vs. sales totals

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/1282dfc8-8be4-4b1a-bdfa-237d5b549712)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/10550b2a-8db7-444b-8210-37e5e20b3968)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/243a3141-2846-4a66-964f-184b1179d377)

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/6a5b881b-793b-4a88-882b-ab17bc3f30bf)

- ### Prices from sugar content are roughly the same.
- ### High-size store prices look to be higher. Although medium size generated more revenue.
- ### OUT003 prices are higher. OUT004 generates more revenue.
- ### Looks like department stores have higher median prices
Supermarket type 2 generates the most revenue.
Department stores may have higher ticket items
- ### Median prices look the same for all product types, which is interesting.

## Inspect product types with respect to store size and tier vs. sales totals

### Small Store

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/434f35de-68e9-4fd9-b7d3-c7e484fe4386)

### Tier 1

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/6c95ab91-3348-4410-ab28-b1d64065e35c)

### Heat Map view of store size

![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/acaddac2-ad4a-43b8-accb-f1861b76f130)


- ### Regardless of the store size, tier, or type, fruits and vegetables, and snack foods are the top 2.

## Split the data into train and test data


![carbon (18)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/e8206996-b1ad-4958-8e6d-e7b6be2c9092)


## Test for Multicollinearity


![carbon (19)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/07132d0c-1f59-440d-8a95-c4d0a9b7997c)

- ### The VIF of Product_Weight, Product_Allocation_Area, Product_MRP, Product_Id_char_FD are less.
- ### The VIF for dummy variables can be ignored, which is expected that they would have a high VIF.
- ### But the continuous variables should not have high VIF.


## Check Model Performance


![carbon (22)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/763da344-7c77-450f-a99d-460fa50d05b9)

- ### The Train and the Test scores are very close to each other so we can say the model is not overfitting.
- ### However, the Test score is slightly better than the Train score. So, we might be able to get better performance if we increase the complexity of the model.


  ![carbon (23)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/dadf9260-4e38-4be0-973f-6d386261f3c3)

- ### The train and the test scores are very close to each other. So, we can say the model is not overfitting.
- ### However, the test score is slightly better than the training score. So, we might be able to get better performance if we increase the complexity of the model.
- ### So, model2 is performing the best when compared with model1 because in model2 we are dropping insignificant variables.


## Checking the below linear regression assumptions
1. Mean of residuals should be 0
2. No Heteroscedasticity
3. Linearity of variables
4. Normality of error terms


## Mean Residual


![carbon (24)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/751bffd5-6878-4af7-8084-ec634b090eb6)

- ### The mean of residuals is very close to 0. Hence, the corresponding assumption is satisfied.



## Check for homoscedasticity
- Homoscedasticity - If the residuals are symmetrically distributed across the regression line, then the data is said to be homoscedastic.

- Heteroscedasticity- - If the residuals are not symmetrically distributed across the regression line, then the data is said to be heteroscedastic. In this case, the residuals can form a funnel shape or any other non-symmetrical shape.

- We'll use Goldfeldquandt Test to test the following hypothesis with alpha = 0.05:

    - Null hypothesis: Residuals are homoscedastic
    - Alternate hypothesis: Residuals have heteroscedastic


![carbon (25)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/7ade0c82-7d61-4ea3-985b-24bfc06987d7)

- ## Since p-value > 0.05, we cannot reject the Null Hypothesis that the residuals are homoscedastic and the corresponding assumption is satisfied.


## Check linearity of Variables


![carbon (26)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/421b458a-874a-49ff-927a-db2ea38b466f)


![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/853da722-e6ca-4e8f-a6b4-be98553197dc)

- ### There is no pattern in the residual vs fitted values plot. Hence, the corresponding assumption is satisfied.


## Normality of error terms

### The residuals should be normally distributed.


![carbon (27)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/e4b80e3c-7d52-425f-bef6-daa91210a497)


![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/d2dcfed4-ccb0-436a-9274-65f4b5c5bed0)


![carbon (28)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/5b6ac19d-16b8-440d-a61e-2db0fac2f9e7)


![image](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/edc1492e-1814-4ed7-8db6-33b6756a10df)

- ### From the above plots, the residuals seem to follow a normal distribution. Hence, the corresponding assumption is satisfied. Now, we will check the model performance on the train and test datasets.


## Apply cross-validation to improve the model and evaluate it using different evaluation metrics

### Let's check the performance of the model using the cross-validation technique from the scikit-learn library and see if the performance on the train and the test data is comparable to what we are getting after cross-validating the data.


![carbon (29)](https://github.com/j-will7378/SuperKart_Linear_Regression/assets/133849655/91aae60b-6933-4979-84ca-5d65f8aeb2a6)

- ### After applying cross-validation the model score has improved. We can compare it by the evaluation metric scores.


## Actionable Insights and Business Recommendations
- ### We can use this prediction model to predict the total sales that will be done by SuperKart in the next quarter.

T- ### he model explains around 79% of the variation in the data.

- ### OUT004 - OUT004, which is of Supermarket Type2, located in a Tier 2 city and having store size as medium, is performing well. They can also look to set up stores in this type of city having comparable socio-economic conditions in order to expand their business and reach.

- ### OUT002 - OUT002, being a food mart in a Tier 3 city and having small store size, is also performing well. Target similar cities for business expansion.

- ### OUT001 - OUT001 which is a store of Supermarket Type 1, located in a Tier 2 city and having store size as high is not performing upto the mark. SuperKart can look to look build new marketing strategies (maybe give attractive discounts and offers) in this store in order to attract more customers.

- ### OUT003 - Similar approach can be taken to increase the business of OUT003 which is a Departmental store in a Tier 1 city and having store size as medium. It is the premium store of the company where most of the costly goods are sold, so the correct set of audience should be targetted.

- ### Daily needs like fruits and vegetables and snack foods are the biggest contributors to the revenue across all the stores. So SuperKart should look to maintain the inventory of these products properly and ensure that these products never face a shortage.

## Additional information that can be collected to gain better insights -

- ### Customers' details like age and gender can be incorporated in this model so that the company gets to know their target audience well and can build their sales strategies according to that.

- ### The company should also keep a watch for the number of festive occasions present in a quarter so that they can strategize their inventory accordingly.

## Continued Research Recommendations and Considerations

- ### What are OUT004 and OUT002 doing to drive revenue?
- ### Who are their customers and what are thier behaviors?
- ### What aren't the pther two perfoming as well?
- ### Who are their customers and what are thier behaviors?
- ### How large does socio economics play into the role of how these stores perform?
- ### Do these stores carry different brands of products and does that play a part into revenue generation?
















