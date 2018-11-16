* Atomicity
    *  A write operation is atomic on the level of a single document, even if the operation modifies multiple embedded documents within a single document.
    * Doing upsert - 
      * ensure to create unique index to avoid duplicate data 


* Concurrency in MongodB - https://docs.mongodb.com/manual/faq/concurrency/ ?

Concurrency control
Concurrency control ensures that database operations can be executed concurrently without compromising correctness. Pessimistic concurrency control, such as used in systems with locks, will block any potentially conflicting operations even if they may not turn out to actually conflict. Optimistic concurrency control, the approach used by WiredTiger, will delay checking until after a conflict may have occurred, aborting and retrying one of the operations involved in any write conflict that arises. https://docs.mongodb.com/manual/reference/glossary/#term-concurrency-control


WriteConflicts https://muralidba.blogspot.com/2018/03/what-are-writeconflicts-in-mongodb.html


Need to implement application level optimistic concurrency as it not supported. https://github.com/mikeckennedy/optimistic_concurrency_mongodb_dotnet/blob/master/src/MongoDB.Kennedy/ConcurrentDataContext.cs

