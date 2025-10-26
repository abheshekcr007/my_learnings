course ppt is really good ..use that for reference  

dynamodb is a nosql database  
it can store document type data ..key value pairs  
it is serverlss..provisioning and maintenance is managed by aws  

nosql databases are distributed ..it can have horizontal scaling ..(adding more machines ..)  

dynamodb is made of tables  
each table should have a primary key  
each table can have infinite number of items  
each item has attributes  

how should the primary key be??  
it can be a partition key or partition key + sort key  
for hot data like ecommerce store carts dynamodb can be a good choice ..for cold data s3 can be a better choice  

26/10/25-  
rcu and wcu -read capacity unit and write capacity unit  
1wcu for an item upto 1kb in size per second
1rcu for a item upto 4kb in size per second ..(eventually consistent is 2x of strongly consistent)  
we can either provision it or have it on demand ..(on demand is 2.5X costly than provisioned)  

