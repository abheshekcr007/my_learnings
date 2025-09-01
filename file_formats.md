**what is the expectation from a file format-**

-gets read fast  
-gets written fast  
-be splittable  
-support advanced compression (Gzip,snappy etc)  
-support schema evolution

there will always be tradeoff..no one file format provides all features  

**Csv/Tsv files -**  

-each line is a record/data and lines are terminated bt /n character  
-good write performance but slower reads  
-do not support block compression  
-text files are inherently splittable by /n character
-limited schema evolution  

**sequence files-**  
-Storing thousands of small log files from a server. The timestamp of each log entry could be the key, and the entire log content for that entry would be the value.  
-each record is stored as a key value pair in binary format  
-good write performance than text files  
-supports block compression  
-they are splittable  
-limited schema evolution  

**Avro format-**  
**example-**  
```json
{
  "type": "record",
  "name": "UserInfo",
  "namespace": "com.example.data",
  "fields": [
    {
      "name": "username",
      "type": "string",
      "doc": "Name of the user"
    },
    {
      "name": "age",
      "type": "int",
      "default": 0,
      "doc": "Age of the user"
    }]
```

**example record-**  
// Logical representation of a single Avro record conforming to the UserInfo schema
```json
{
  "username": "Alice",
  "age": 30,
  "email": "alice@example.com",
  "isActive": true
}
```

-it is a file format plus serialization and deserialization framework.Avro uses Json for defining data types and serializes data in compact binary format  
-average read and write performance  
-supports block compression  
-they are splittable  
-was mainly designed for schema evolution. (it stores metadata with data ).fields can be added,renamed or deleted while the old files can still be read with the new schema  


**Columnar file formats-**  
-in columnar file formats ,instead of storing rows adjacent to one another ,we also store column values adjacent to one another.  
-so datasets are partitioned horizontally as well as vertically  

**Rc file format (record columnar)-**  
-these are flat files consisting of binary key value pairs.and it shares much similarity with sequence files.  
-was developed for faster reads,but with a compramise for write performance.  
-provides significant block compression.  
-Rc files are splittable  
was mainly designed for faster reads so no schema evolution.  

**ORC file format-**  
-a better version than RC file format
-was developed for faster reads,but with a compramise for write performances.  
-provides significant block compression  
-orc files are splittable  
-still doesnt support schema evolution

**Parquet file format-**  
-it is a columnar file format similar to rc and orc.  
-faster reads with solw writes  
-supports compression mostly with snappy algorithm  
-parquet files are conditionally splittable  
-limited schema evolution (new fields can only be added to existing fields and old fields can never be deleted.














