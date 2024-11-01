Module 1 :-

Different Isolation Levels and Read Phenomenons (MySQL)
4  Isolation Levels 
Technique - Locking Mechanism
Default - Locking Mechanism
1. Dirty Read -> Reads Un Committed Values as well
2. Read Committed -> Reads only committed value
3. Read Repeatable -> Differents results for a tuple/ All results remain consistent , but it on update , it updates and take into consideration value committed by other transactions 
4. Phantom read -> Different results for a single query ,
5. Serializable Anomaly -> Cant do Update in t1 , if Select is in t2 , because it does Select for Share, when timeout happens in t1 while waiting , in t2 , deadlock occurs .So in t2 commit must happen with each query 

Different Isolation Levels (postgreSQL, Isolation level happens on specific transaction only)
3 Isolation Levels 
Technique - Dependencies Detection
Default - Read Committed 

1. Dirty Read -> Reads Un Committed Values as well
2. Read Committed -> Reads only committed value, 
3. Read Repeatable -> Differents results for a tuple/ All results remain consistent , but it on update , it throws an error 
4. Phantom read -> Different results for a single query ,
5. Serializable Anomaly -> if Insert in t1 , and Insert in t2 , Then it shows inserted row of t1 also in result of t2 when select query has run . When using serializable mode , it throws an error , in MySQL , such situation is avoided by locking mechanism until commit happens in t1 , t2 cant process.If query in t2 has not been committed , and in t1 we also run a query , then we get deadlock situation in mysql
6. Read Uncommitted -> No dirty Read.
--------

