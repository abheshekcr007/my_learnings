spark context and spark session 

spark context is used for dealing with rdds.  
it was introduced and used in spark 1.X 

```
from pyspark import SparkContext

sc = SparkContext(appName="MyApp")
rdd = sc.parallelize([1, 2, 3, 4])
print(rdd.sum())
```

spark session is used for dealing with higher level apis like dataframes,datasets etc  
it was introduced and used from spark 2.X  
spark session has sqlcontext,hivecontext,and sparkcontext  


```
from pyspark.sql import SparkSession

spark = SparkSession.builder \
    .appName("MyApp") \
    .getOrCreate()

df = spark.createDataFrame([(1, "A"), (2, "B")], ["id", "value"])
df.show()
```

