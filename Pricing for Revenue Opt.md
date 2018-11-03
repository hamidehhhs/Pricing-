# Revenue Management with Price Optimization 
* Revenue is the income that a business has from its normal business activities, usually from the sale of goods and services to customers.
* Revenue management is aimed to find a way of selling the right product to the right customer at the right time for the right price.Revenue management problem can be decomposed into four distinct but related subproblems that are usually treated separately: demand forecasting, overbooking, capacity allocation and pricing. Experts agree that pricing is vital in RM.
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

### [Revenue managment based on dynamic pricing in the presense of transport competition](https://github.com/hamidehhhs/Pricing-/blob/master/paper/Dynamic%20pricing%20of%20HSR%20with%20compettition%20.pd)

The demand for a seat depends in high speed railway not only on its price, but also on the price of a similar schedule 
for a different mode like airplane. Their analysis is based on the assumption that each mode keeps track of the real-time 
number of seats available in all other modes.<br/>
In their paper  take into account a passenger who cancels their reservation or no-shows, and are overbooked by the company.
* Breif review 
We assume that there are n types of transportation modes (for example, railway, airplane, expressway bus and so on) 
between a single origin and destination pair, and each transit agency provides an alternative schedule in a day.
Their objective is to find a pricing strategy that maximize the revenue for each mode and prove that there is Nash 
equilibrium in the mixed strategies under some resonable assumptions.
Consider <img src="https://latex.codecogs.com/svg.latex?\inline&space;f_{ij}(x,t)" title="f_{ij}(x,t)" /> be the price of jth schedules 
of mode i, for a different time t and different number of booking x. They formulate a revenue for each mode  depend on 
the price after taking into account the cancalation refund. and find the optimum pricing strategy for each mode.
{Their model for revenue is very intersting , the whole paper is very worth to read!}

### [Bilevel model to maximize revenue by pricing and seat inventory control Case study North American Airline](https://github.com/hamidehhhs/Pricing-/blob/master/paper/bilevel%20model%20for%20fare%20price.pdf)
They used the idea of [bilevel optimization problems](https://arxiv.org/pdf/1705.06270.pdf) to model revenue management. 
They define an optimization problem with the following format: <br/>
<img src="https://latex.codecogs.com/svg.latex?\inline&space;\begin{array}{cc}&space;\max_{x,\gamma}&space;F(x,\gamma)&space;&&space;\\&space;&&space;(x,\gamma)\in&space;X\\&space;&&space;\gamma\in&space;argmin_{\gamma\in&space;Y(x)}&space;f(x,\gamma)&space;\end{array}" title="\begin{array}{cc} \max_{x,\gamma} F(x,\gamma) & \\ & (x,\gamma)\in X\\ & \gamma\in argmin_{\gamma\in Y(x)} f(x,\gamma) \end{array}" />
* Breif reveiw: Their decision variables of their optimization problem are: 1- product fares (a product is an O-D itinerary ) 2- number of passengers buy a given product. The whole model is decsribed on page 8 of the paper. The upper level optimization is maximizing airline revenue that is price  multiply nummber of passenger sum over all airline flight, product and customer group. In the lower level {to get the better estimation of demand} find optimum number of passenger by minimizeing their travel disutility.
Their intution behind using the bilevel model is that, user try to minimze their own disutility of travel from origin to destination, which is dependent on fare structure, seat availability, flight duration, etc.<br/>
Advantage of their model is that, it makes  possible to take into account customer segmentation and behaviour, with respect ot the airline fare and competitors. While 
disadvantage is that the model set an static optimum price {Need to run several times a perday to make it dynamic!}
