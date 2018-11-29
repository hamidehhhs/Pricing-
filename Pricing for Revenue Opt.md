# Pricing for Revenue Management
* Revenue is the income that a business has from its normal business activities, usually from the sale of goods and services to customers.
* Revenue management is aimed to find a way of selling the right product to the right customer at the right time for the right price 
to improve profits by controlling the prices and availabilities of various products. 
 Revenue management problem can be decomposed into four distinct but related subproblems that are usually treated separately: 
 demand forecasting, overbooking, capacity allocation and pricing. Experts agree that pricing is vital in RM.
Here we will review some papers concerning this subject. 

### [Revenue management with seat inventory control method Case study China high speed railway](https://github.com/hamidehhhs/Pricing-/blob/master/paper/seat%20assignment%20model%20.pdf)
In this work they don't want to set a price for a particular product, but their goal is to find the optimum distribution of their products
with a predefined price to improve the revenue. <br/>
Means, they try to desing an optimum seat allocation, by varying booking limits, for a certain period of time and multiple train with different 
stop available for a same O-D itinerary. 
In their seat inventory method, for a  homogeneous seat multiple fare class will be designed based on [customer preference](https://213.233.161.137:2443/hhsereshky/Pricing-/blob/master/Data%20Analysis/Customer%20preference.md) 


* Main idea: Assume there is k=1 to K customer type each characterized by unique preference order among the available fare class.
For example if we have just three fare class A,B and C one customer type is those who would prefer A then B and final choice is C. <br/>
They design a mathematical programming with decision variables <img src="https://latex.codecogs.com/svg.latex?\inline&space;b_{gjr}^k" title="b_{gjr}^k" /> , denotes the booking limit for train g , O-D itinerary j , customer type k , and  fare class r.  Their objective function 
is the total expected revenue of all the customers for all O-D itineraries formulate by 
<img src="https://latex.codecogs.com/svg.latex?\inline&space;\sum_{j=1}^n\sum_{k=1}^K\sum_r&space;(h_{jr}^kS_{jr}^k(b_{gjr}^k))" title="\sum_{j=1}^n\sum_{k=1}^K\sum_r (h_{jr}^kS_{jr}^k(b_{gjr}^k))" /> under  some constraitns (equation (11-15) of page 10)
where <img src="https://latex.codecogs.com/svg.latex?\inline&space;h_{jr}^k" title="h_{jr}^k" /> is the ticket price of class r for customer type k and O-D itinerary j {Note that they don't consider price as variable but need to be known!}. Function S is defined  for customer type k and O-D itinerary j and is the number of those customers who obtain ticket in class r. 
Two main values need to be predicted (for example by data analysis) to calculate this function.
1-Passenger demand density function and  <img src="https://latex.codecogs.com/svg.latex?\inline&space;\lambda_j^k" title="\lambda_j^k" /> that is predicted number of customer of type k on O-D itinerary j.  

A similar work is done for [airline revenue management](https://213.233.161.137:2443/hhsereshky/Pricing-/blob/master/paper/revenue%20management%20under%20customer%20choice.pdf)
Preference ordering and some other concepts is described better there. 
### [Revenue managment with fare optimization base on passenger choice case study China HSR](https://github.com/hamidehhhs/Pricing-/blob/master/paper/Fare%20Opt%20and%20passenger%20choice%20behavior.pdf)
They divide customer behaivour in to two categories 1) myopic {buy a product as soon as its price is less than their reservation price} 
and 2) strategic {optimize their purchase behavior according to the company pricing strategy}
They assume myopic behavior in this paper, since too much information and time is needed for a customer to be a strategic. 
 Therefor it is can be a false assumption that many customers choose to be myopic. 
* Main idea: 
They assume there is j=1 to n different O-D itineraries each has a ticket selling period, with
<img src="https://latex.codecogs.com/svg.latex?\inline&space;T_j" title="T_j" /> subperiod. 
Let <img src="https://latex.codecogs.com/svg.latex?\inline&space;d_j^t" title="d_j^t" /> be the duration of subperiod t
for itinerary j. They intend to maximize revenue by adjusting ticket price over time based on passenger behaviour through the following optimization problem:
<img src="https://latex.codecogs.com/svg.latex?\inline&space;\max&space;R(\lambda)=\sum_{j=1}^n&space;\sum_{t=1}^{T_j}&space;\lambda_j^tP_j^t(\lambda)d_j^t" title="\max R(\lambda)=\sum_{j=1}^n \sum_{t=1}^{T_j} \lambda_j^tP_j^t(\lambda)d_j^t" /> 
with some proper constraints {equatins (2) and (3) in page 3}. Their decision variables  <img src="https://latex.codecogs.com/svg.latex?\inline&space;\lambda_j^t" title="\lambda_j^t" /> 
 are demand density  of product 𝑗 in subperiod t, and P is a price function its value
s is based on demand {In this paper it defined as a equation (6) of page 3}.<br/>
It is worth to note that, Passenger demand is usually characterized as a Poisson process, for which demand within a certain time 
period is a stochastic variable. This stochastic element vastly increases the complexity and difficulty of the problem. 
In this paper they use a frequently employed method which is using  a deterministic model as an approximation of the 
stochastic problem. Means instead of estimating density function, they would find it through optimization program. 
By solving the optimization they can figure out how many seat can be allocatated to a product in each subpreiod with a certain price.  

### [Revenue managment based on dynamic pricing in the presense of transport competition](https://github.com/hamidehhhs/Pricing-/blob/master/paper/Dynamic%20pricing%20of%20HSR%20with%20compettition%20.pdf)

The demand for a seat depends in high speed railway not only on its price, but also on the price of a similar schedule 
for a different mode like airplane. Their analysis is based on the assumption that each mode keeps track of the real-time 
number of seats available in all other modes.<br/>
In their paper  take into account a passenger who cancels their reservation or no-shows, and are overbooked by the company.
* Main idea:  We assume that there are n types of transportation modes (for example, railway, airplane, expressway bus and so on) 
between a single origin and destination pair, and each transit agency provides an alternative schedule in a day.
Their objective is to find a pricing strategy that maximize the revenue for each mode and prove that there is Nash 
equilibrium in the mixed strategies under some resonable assumptions.
Consider <img src="https://latex.codecogs.com/svg.latex?\inline&space;f_{ij}(x,t)" title="f_{ij}(x,t)" /> be the price of jth schedules 
of mode i, for a different time t and different number of booking x {vary with t}. They formulate a revenue for each mode  depend on 
the price after taking into account the cancalation refund. and find the optimum pricing strategy for each mode.
Given time t and booking number x(t) they defin an optimization problem in equation (6) to find a pricing for the given state {t,x(t)}.
The objective function is a bit complicated but it revenue pluse other factors! 
{Their model for revenue is very intersting , the whole paper is very worth to read!}

### [Bilevel model to maximize revenue by pricing and seat inventory control Case study North American airline](https://github.com/hamidehhhs/Pricing-/blob/master/paper/bilevel%20model%20for%20fare%20price.pdf)
They used the idea of [bilevel optimization problems](https://arxiv.org/pdf/1705.06270.pdf) to model revenue management. 
They define an optimization problem with the following format: <br/>
<img src="https://latex.codecogs.com/svg.latex?\inline&space;\begin{array}{cc}&space;\max_{x,\gamma}&space;F(x,\gamma)&space;&&space;\\&space;&&space;(x,\gamma)\in&space;X\\&space;&&space;\gamma\in&space;argmin_{\gamma\in&space;Y(x)}&space;f(x,\gamma)&space;\end{array}" title="\begin{array}{cc} \max_{x,\gamma} F(x,\gamma) & \\ & (x,\gamma)\in X\\ & \gamma\in argmin_{\gamma\in Y(x)} f(x,\gamma) \end{array}" />
* Main idea: Decision variables of their bilevel optimization problem are: 1-product fares (a product is an O-D itinerary ) 
2-number of passengers buy a given product. The whole model is decsribed on page 8 of the paper. In uper level they optimize revenue 
based on product fare and number of passenger in each group purchasing the product. But the buyer in each fare class  depend on different
factors like fare structure, seat availiblity, flight duration , .... So to   get the better estimation of demand, in the lower 
level they try to find optimum number of passengers by minimizing passengers disutility.( To formulate objective functions we need some information from data) <br/>
Advantage of their model is that, it makes  possible to take into account customer segmentation and behaviour, with respect ot 
the airline fare and competitors. While 
disadvantage is that the model set an static optimum price {Need to run several times a perday to make it dynamic!}

### [Revenue managment with limited demand information, using online pricing](https://github.com/hamidehhhs/Pricing-/blob/master/paper/online%20pricing.pdf)


