what am i learning to build today ?  

what problem for customer or business am i trying to solve  
i am solving the problem of big data for businesses..  
Businessess generate a lot of data ..this data can be used in useful ways to improve the services  
it offers to its customers..  generate new insights and increase their revenue..  
and other whole host of things can be done if they can leverage the data they generate   

so for this we need big data engineers..  
so i can help businesses to bring data into one place from many different sources  
transform this data according to business logic and serve it to the end users  

for this we need orchestration skills to bring data from various sources  
sql,python skills ..scripts to bring in data can be achieved only through this  
data warehousing skill..this big data need to be stored in ordered tables somewhere ..
distributed compute through spark ..batch and stream processing  

so what are the skills we need to be good at  
1.sql,python,pyspark  
2.cloud(orchestation,warehousing,transformation,devops)  
3.distributed compute concepts  


<b>1.why spark is faster than mapreduce??  </b>  
In-memory computation  
Less disk I/O  
DAG-based optimization  
Faster iterative and interactive workloads  
Lazy evaluation and caching  

```
val text = spark.read.textFile("hdfs://file")
val result = text
  .flatMap(line => line.split(" "))
  .map(word => (word, 1))
  .reduceByKey(_ + _)
  .filter(_._2 > 10)
  .sortBy(_._2, ascending = false)

result.collect()
```

What happens:
Data is loaded once  
Intermediate results stay in memory  
Spark builds a DAG and optimizes execution  
Only final output is written to disk (if needed)  
No repeated disk reads/writes  






