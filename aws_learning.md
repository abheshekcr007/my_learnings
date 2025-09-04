**AWS Kinesis**  

in short it can be said as stream analytics  
suppose assume there is an e-commerce website..and customers visit this site and perform variety of operations..  
browse through the catalog,buy something ,add to cart and leave and so on ..  
Adding to cart and leaving can be a potential loss for the business..because it had somehow convienced the customer that it is of good quality and at a good price  
and customer had also added it to his cart .but for some reason ..network issue or some notification from some other app he leaves..  
so there is a high probability of sales if we show such products as ads to the customer..  
and hence we analyse ..who are the customers who added products to their cart and left and where are they from..  

use Lambda function to enrich the data ...by adding geo location and timestamp ..and also the products that they were interested in.  

enriched data lands in S3 bucket  

Glue transforms it into curated tables..  

Athena queries ..how many users abondoned the cart after 5 minutes..  

and this info of user_id,geo location and the kind of products that they were interested in can be sent to the marketing team  
when can help them to plan and conduct efficient marketing campaigns ..which can boost the sales for the company.  



