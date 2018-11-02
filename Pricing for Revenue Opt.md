# Revenue Management with Price Optimization 
* Revenue is the income that a business has from its normal business activities, usually from the sale of goods and services to customers.
* Revenue management is aimed to find a way of selling the right product to the right customer at the right time for the right price.
Here we will review some papers concerning this subject. 

 ### [Revenue management with seat inventory control method Case study China high speed railway](https://github.com/hamidehhhs/Pricing-/blob/master/paper/seat%20assignment%20model%20.pdf)
They assume that different fare classes for homogenous seats is available and they predict customer behavior   according to customer preference orders. Then they try to improve revenue by controlling determinestic booking limits for each fare class. 
One of the key feature in their method  is that if  there is multiple train avaiable for each O-D itinerary, design a seat allocation for the whole train instead of one by one. (See the example of page 4 of the paper) 

* Here is a brief description of their model and idea: 
They try to take a customer type in to account in their model. <br/>
Assume there is k=1 to K customer type each has unique preference order among the available fare class. For example if we have just three fare class A,B and C one customer type is those who would prefer A then B and final choice is C. <br/>
They design an mathematical programming which aim to find decision variables <img src="https://latex.codecogs.com/svg.latex?\inline&space;b_{gjr}^k" title="b_{gjr}^k" />   denotes the booking limit for train g , O-D itinerary j , customer type k , and  fare class r.  The total expected revenue of all the customers for all O-D itineraries is 
<img src="https://latex.codecogs.com/svg.latex?\inline&space;\sum_{j=1}^n\sum_{k=1}^K\sum_r&space;(h_{jr}^kS_{jr}^k(b_{gjr}^k))" title="\sum_{j=1}^n\sum_{k=1}^K\sum_r (h_{jr}^kS_{jr}^k(b_{gjr}^k))" /> with some constraitns
where <img src="https://latex.codecogs.com/svg.latex?\inline&space;h_{jr}^k" title="h_{jr}^k" /> is the ticket price of class r for customer type k and O-D itinerary j {Note that they don't consider price as variable but need to be known!}. and the function S is  for customer type k and O-D itinerary j , the number of customers who obtain class r. This is directly to a random variable <img src="https://latex.codecogs.com/svg.latex?\inline&space;\lambda_j^k" title="\lambda_j^k" /> that is predicted number of customer of type k on O-D itinerary, They predict its density function by data 
Table 1 of page 7 include good review 
Name of paper :<br/>

### [Revenue managment with fare optimization base on passenger demand case study China HSR](https://github.com/hamidehhhs/Pricing-/blob/master/paper/Fare%20Opt%20and%20passenger%20choice%20behavior.pdf)
They devide customer behaivour in to two category 1) myopic {buy a product as soon as its price is less than their reservation price} and 2) strategic {optimize their purchase behavior according to the company pricing strategy}
we assume myopic behavior in this paper. Since there is not too much information and time for customers to make strategic decisions when purchasing railway tickets.
* Brief review of this paper: 
They assume there is j=1 to n different O-D itineraries each has a ticket selling period with  <img src="https://latex.codecogs.com/svg.latex?\inline&space;T_j" title="T_j" /> subperiod. Let <img src="https://latex.codecogs.com/svg.latex?\inline&space;d_j^t" title="d_j^t" /> be the duration of subperiof t for itinerary j. They intend to maximize revenue through the following optimization problem: <img src="https://latex.codecogs.com/svg.latex?\inline&space;\max&space;R(\lambda)=\sum_{j=1}^n&space;\sum_{t=1}^{T_j}&space;\lambda_j^tP_j^t(\lambda)d_j^t" title="\max R(\lambda)=\sum_{j=1}^n \sum_{t=1}^{T_j} \lambda_j^tP_j^t(\lambda)d_j^t" /> with some proper constraints. In this programming <img src="https://latex.codecogs.com/svg.latex?\inline&space;\lambda_j^t" title="\lambda_j^t" /> are decision variables and are demand density (amount of demand in unit time) of product 𝑗 in subperiod 𝑡, and P is a price function with respect to the demand. {Its numerical exprement is worth to check}




### Revenue optimization in the present of competitor 

 The demand for a seat depends not only on its price, but also on the price of a similar schedule for a different mode. 
<br/>
We use the multinomial logit (MNL) model to describe the customers’ choice behavior.

<img src="https://latex.codecogs.com/svg.latex?\inline&space;x^2" title="x^2" />
