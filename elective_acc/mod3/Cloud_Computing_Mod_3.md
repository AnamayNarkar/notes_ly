# Cloud Computing - Module 3: Managing Data (10 hrs, CO3)

Course: Cloud Computing / Cloud Computing Emerging Technologies (K. J. Somaiya, Mumbai University / SVU)

How to read this file:

- Unmarked content comes from your uploaded notes (the 4 decks).
- `[PYQ yyyy]` marks something that has actually appeared in a previous year paper.
- `[ADDED]` marks content I wrote myself because it is in the syllabus or helps the answer, but it is NOT in your notes or any official PYQ.
- `[LIKELY]` marks question types I expect (my prediction, not official).

---

## 0. CARRY-FORWARD SUMMARY (UTMOST IMPORTANT - keep this in context for the whole chat)

**Task:** Help the student prepare Module 3 (Managing Data). One single markdown file `Cloud_Computing_Mod_3.md` with four deliverables: (1) topic map, (2) topic-wise question-type table with PYQ indicators, (3) topic-by-topic breakdown with exam-writing guidance and numericals, (4) PYQ solutions grouped by topic. No emojis, no separate artifacts. Anything not from notes/PYQ must be marked `[ADDED]`.

**Syllabus (verbatim):**
- 3 Managing Data, 10 hrs, CO3
- 3.1 Relational databases: Data Storage Techniques; Default data storage and retrieval mechanism since the 80s
- 3.2 Cloud File Systems: Google File System (GFS Architecture), BigTable Storage, Dynamo Architecture, Datastore
- 3.3 Parallel Database Architectures, MapReduce Model: Fault Tolerance, Efficiency, Applications

**Source material read (all of it):**

| File | Covers |
|---|---|
| Module_3_1.pptx (74 slides) | Intro to data/DBMS/RDBMS, 12 storage techniques, comparison table, default mechanism since the 1980s (evolution, client-server, SQL, ACID, transactions, concurrency, limitations in cloud) |
| Module_3_2.pptx (113 slides) | GFS, NoSQL intro, BigTable, Dynamo (consistent hashing, vnodes, quorum, hinted handoff, vector clocks), Datastore (entity/kind/property/key), comparison tables |
| Cloud_File_Systems_GFS_BigTable_Dynamo_Datastore.pptx (18 slides) | Condensed version + 4-system comparison + "choose the right system" + exam key points |
| Parallel_Database_Architectures_MapReduce.pptx (23 slides) | Shared memory/disk/nothing, partitioning, MapReduce (map, shuffle, reduce, word count), fault tolerance, efficiency metrics, applications, MapReduce vs MPP DB, limitations, review questions |
| cloud_computing.PDF | Scanned SVU ESE paper Jan-Apr 2025 (course 116m75E702, 100 marks, 3 hrs) |
| 7 screenshots | Dec 2022 ESE (2UCE713, 100 marks), Nov-Dec 2021 ESE (2UCE713, 50 marks), May-June 2021 ESE (UCEC801 Distributed and Cloud Computing, 50 marks) |

**PYQ screening result (only Module 3 questions kept):**

| Paper | Question | Marks | Module 3 topic |
|---|---|---|---|
| Jan-Apr 2025 | Q2A(ii) Explain Map Reduce model with example | 5 | 3.3 MapReduce |
| Jan-Apr 2025 | Q5(iii) Amazon Simple Storage Service (S3) | 5 | 3.2 adjacent (cloud storage) |
| Nov-Dec 2021 | Q1(B)(v) Difference between Amazon Simple DB and Amazon RDS | part of 10 (any 5 of 7) | 3.1/3.2 relational vs NoSQL cloud DB |

Rejected as NOT Module 3 (belong to other modules): SaaS, scalability/elasticity, private vs public cloud, Jenkins, Web 2.0, utility computing, PaaS, execution/Hyper-V virtualization, Aneka (container, services, scheduling), AppEngine, DVFS/power management, cloud federation, Docker, MBaaS, Xen, VMware, Spot cloud, MaaS, SOA, VM migration, microservices, EC2, AWS architecture, MOCC, SAN vs NAS (storage virtualization - Dec 2022 Q1 iv and May-June 2021 Q1 IV; this is virtualization, not Module 3), cluster job management, MCQs on hypervisors/web services/load balancing.

**Key insight:** PYQ coverage of this module is thin (3 items in 4 papers, one is borderline). GFS, BigTable, Dynamo, Datastore, parallel DB architectures, ACID and storage techniques have NEVER appeared, so they are the highest "fresh question" risk. The 2025 paper (current SVU pattern) asks: Q1 any 4 of 6 at 5 marks, Q2A 5+5 (or 10), Q2B 10, Q3 any 2 of 3 at 10, Q4 any 2 of 3 at 10, Q5 any 4 of 6 short notes at 5. Prepare every topic at two depths: a 5-mark note (5-6 points + small diagram) and a 10-mark answer (definition, architecture diagram, working, advantages, limitations, example).

**Facts to remember exactly (from notes):**
- GFS: Client + Master + Chunk Servers; chunk = 64 MB with unique chunk handle; 3 replicas; heartbeat; master stores metadata only; data flows client <-> chunk server directly.
- BigTable: row key, column family, column, timestamp; built on GFS + Chubby + SSTable; Master + Tablet Servers; write = commit log -> MemTable -> flush to SSTable -> compaction.
- Dynamo: key-value, decentralized, consistent hashing ring, vnodes, replication factor N, quorum R + W > N (example 3/2/2), eventual consistency, hinted handoff, vector clocks.
- Datastore: entity, kind, properties, key, ancestor hierarchy, indexes, transactions, strong vs eventual consistency; now Firestore in Datastore mode.
- Parallel DB: shared memory, shared disk, shared nothing; MapReduce = Map -> Shuffle/Sort -> Reduce; fault tolerance = replication + task re-execution + speculative execution; efficiency = speedup S(p)=T(1)/T(p), efficiency E(p)=S(p)/p, locality, skew, Amdahl.

---

## 1. TOPIC MAP

```
MODULE 3: MANAGING DATA (10 hrs, CO3)
|
+-- 3.1 RELATIONAL DATABASES
|    |
|    +-- A. Foundations
|    |    +-- Data -> Database -> DBMS -> RDBMS
|    |    +-- Why databases are needed (redundancy, inconsistency, search, security)
|    |    +-- Components of an RDBMS
|    |         +-- Table (relation), Row (tuple), Column (attribute)
|    |         +-- Primary key, Foreign key
|    |
|    +-- B. DATA STORAGE TECHNIQUES
|    |    +-- 1. Table-based storage
|    |    +-- 2. Row-oriented storage (OLTP)
|    |    +-- 3. Column-oriented storage (OLAP)
|    |    +-- 4. Heap file organization
|    |    +-- 5. Sequential file organization
|    |    +-- 6. Indexed storage
|    |    |    +-- Primary index
|    |    |    +-- Secondary index
|    |    |    +-- Clustered index
|    |    |    +-- Non-clustered index
|    |    +-- 7. Hash-based storage
|    |    +-- 8. B-Tree / B+ Tree storage
|    |    +-- 9. Partitioning (horizontal, vertical, range, hash, list)
|    |    +-- 10. Compression (row, column, dictionary, RLE)
|    |    +-- 11. Normalization
|    |    +-- 12. Data pages and blocks
|    |    +-- Comparison table + applications
|    |
|    +-- C. DEFAULT STORAGE AND RETRIEVAL MECHANISM SINCE THE 1980s
|         +-- Evolution: file-based -> hierarchical -> relational (Codd, 1970)
|         +-- Why RDBMS became the default (tables, SQL, normalization, security)
|         +-- Client-server database architecture (client, DB server, storage)
|         +-- SQL-based retrieval (SELECT, INSERT, UPDATE, DELETE)
|         +-- ACID properties (A, C, I, D)
|         +-- Transaction management (BEGIN/COMMIT/ROLLBACK, transaction states)
|         +-- Concurrency control (locks, timestamp ordering, MVCC)
|         +-- Advantages
|         +-- Limitations in cloud computing  ---> motivates 3.2
|
+-- 3.2 CLOUD FILE SYSTEMS
|    |
|    +-- Why cloud file systems (scale, fault tolerance, throughput)
|    |
|    +-- A. GOOGLE FILE SYSTEM (GFS)
|    |    +-- Why GFS was built, features
|    |    +-- Architecture: Client, Master (metadata), Chunk Servers
|    |    +-- File storage: 64 MB chunks, chunk handle
|    |    +-- Read operation, Write operation
|    |    +-- Replication and fault tolerance (heartbeat, re-replication)
|    |    +-- Advantages, limitations, applications
|    |    +-- Traditional FS vs GFS
|    |
|    +-- B. BIGTABLE STORAGE
|    |    +-- NoSQL introduction (traditional DB vs NoSQL)
|    |    +-- Features, applications
|    |    +-- Data model: Row key, Column family, Column, Timestamp
|    |    +-- Architecture: Client, Master, Tablet Servers, GFS, Chubby
|    |    +-- Tablet and SSTable
|    |    +-- Read / Write (commit log, MemTable, compaction)
|    |    +-- Advantages, limitations
|    |    +-- BigTable vs RDBMS, BigTable vs GFS
|    |
|    +-- C. DYNAMO ARCHITECTURE
|    |    +-- Need for Dynamo, characteristics (decentralized, HA, eventual)
|    |    +-- Key-value data model
|    |    +-- Consistent hashing, virtual nodes
|    |    +-- Data partitioning, Replication (N)
|    |    +-- Consistency: eventual, quorum (N, R, W)
|    |    +-- Failure handling: detection, hinted handoff
|    |    +-- Versioning: vector clocks
|    |
|    +-- D. DATASTORE
|    |    +-- Why cloud datastores, characteristics
|    |    |    (scalability, availability, durability, fault tolerance, persistence)
|    |    +-- Types of cloud datastores
|    |    +-- Data model: Entity, Kind, Properties, Key, Ancestor paths
|    |    +-- Indexing, Queries, Transactions
|    |    +-- Strong vs eventual consistency
|    |    +-- Architecture
|    |    +-- RDBMS vs Datastore, Dynamo vs Datastore
|    |
|    +-- E. Comparison of GFS / BigTable / Dynamo / Datastore + choosing a system
|
+-- 3.3 PARALLEL DATABASE ARCHITECTURES AND MAPREDUCE
     |
     +-- A. Parallel database architectures
     |    +-- Why parallel databases (data growth, performance, scalability)
     |    +-- Shared memory
     |    +-- Shared disk
     |    +-- Shared nothing (partitioning, parallel query processing, data skew)
     |
     +-- B. MapReduce model
     |    +-- Big picture: Map -> Shuffle/Sort -> Reduce
     |    +-- Map function, Shuffle/Sort/Reduce
     |    +-- Worked example: Word Count
     |    +-- How parallelism is achieved (data, task, pipelined)
     |
     +-- C. Fault tolerance
     |    +-- Replication of input, task re-execution
     |    +-- Straggler mitigation (speculative execution), checkpointing
     |
     +-- D. Efficiency
     |    +-- Parallelism, data locality, communication, skew
     |    +-- Metrics: execution time, speedup, efficiency, throughput, utilization
     |    +-- Amdahl's law
     |
     +-- E. Applications (logs, search/indexing, recommendation, ETL, social, IoT)
     +-- F. MapReduce vs parallel/MPP database; limitations; typical stack
```

---

## 2. TOPIC-WISE QUESTION TYPES

Legend: `[PYQ yyyy]` = appeared in a previous year paper. `Likely` = my prediction based on how notes are structured and the SVU paper pattern (not official). `-` = unlikely for that topic.

Question-type columns: **Note** = short note (5M), **Long** = explain in detail (10M), **Diag** = draw and explain a diagram, **Cmp** = compare/differentiate, **Num** = numerical/problem, **Case** = example/scenario/design, **Obj** = MCQ/match/fill/1-2 marks.

### 3.1 Relational databases

| Topic | Note | Long | Diag | Cmp | Num | Case | Obj |
|---|---|---|---|---|---|---|---|
| DBMS vs RDBMS, components (table, key) | Likely | - | Likely (sample tables) | Likely (DBMS vs RDBMS) | - | Likely | Likely |
| Table / row-oriented / column-oriented storage | Likely | Likely | Likely (layout) | Likely (row vs column) | Likely [ADDED style] | Likely (slide 18 activity: which technique for which task) | Likely |
| Heap and sequential file organization | Likely | - | Likely | Likely (heap vs sequential) | Likely (search cost) [ADDED style] | - | Likely |
| Indexed storage (primary, secondary, clustered, non-clustered) | Likely | Likely | Likely | Likely (clustered vs non-clustered) | - | - | Likely |
| Hash-based storage | Likely | - | Likely | Likely (hash vs B+ tree) | Likely (hash mod bucket) [ADDED style] | - | Likely |
| B / B+ tree | Likely | Likely | Likely | Likely | Likely (height) [ADDED style] | - | Likely |
| Partitioning, compression, pages/blocks | Likely | - | - | - | - | - | Likely |
| Normalization | Likely | - | Likely (before/after tables) | - | Likely (normalize a table) | Likely | Likely |
| Default mechanism since 80s (why RDBMS became standard) | Likely | Likely | Likely (client-server) | Likely (file system vs DBMS) | - | Likely | Likely |
| SQL-based retrieval | Likely | - | - | - | Likely (write queries) | Likely | Likely |
| ACID properties | Likely | Likely | - | - | - | Likely (bank transfer case study in notes) | Likely |
| Transaction management and states | Likely | - | Likely (state diagram) | - | - | Likely | Likely |
| Concurrency control (lost update) | Likely | - | - | - | Likely (lost update trace) [ADDED style] | Likely | Likely |
| Limitations of RDBMS in cloud / RDBMS vs NoSQL | Likely | Likely | - | **[PYQ 2021] Amazon SimpleDB vs Amazon RDS** | - | - | Likely |

### 3.2 Cloud file systems

| Topic | Note | Long | Diag | Cmp | Num | Case | Obj |
|---|---|---|---|---|---|---|---|
| GFS architecture | Likely | Likely | Likely (client-master-chunkservers) | Likely (traditional FS vs GFS) | Likely (chunk count, replica count - notes slide 10, 18) | Likely (store a video file) | Likely |
| GFS read / write flow | Likely | Likely | Likely (step diagram) | - | - | - | Likely |
| GFS replication and fault tolerance | Likely | - | Likely | - | Likely (copies after failure) | Likely | Likely |
| NoSQL intro | Likely | - | - | Likely (traditional DB vs NoSQL) | - | - | Likely |
| BigTable data model | Likely | Likely | Likely (row/column family/timestamp table) | Likely (BigTable vs RDBMS) | - | Likely (sparse student table, salary versions) | Likely |
| BigTable architecture (Master, Tablet Server, Chubby, GFS) | Likely | Likely | Likely | Likely (BigTable vs GFS) | - | - | Likely |
| Tablet and SSTable; read/write path | Likely | - | Likely (write path) | - | - | - | Likely |
| Dynamo architecture and characteristics | Likely | Likely | Likely (ring) | Likely (Dynamo vs Datastore, Dynamo vs RDBMS) | - | Likely (shopping cart) | Likely |
| Consistent hashing, virtual nodes | Likely | - | Likely (ring) | Likely (mod hashing vs consistent hashing) | Likely (keys moved) [ADDED style] | - | Likely |
| Replication, quorum N/R/W, eventual consistency | Likely | - | - | - | Likely (check R+W>N; notes slide 70) | Likely (price 50 -> 60) | Likely |
| Hinted handoff, vector clocks | Likely | - | Likely | - | Likely (compare two vector clocks) | Likely | Likely |
| Datastore (entity, kind, property, key) | Likely | Likely | Likely (architecture) | Likely (RDBMS vs Datastore) | - | Likely | Likely |
| Datastore indexing, queries, transactions, consistency | Likely | - | - | - | - | - | Likely |
| Four-system comparison / choosing a system | - | Likely | - | Likely (comparison table, notes slide 15) | - | Likely | Likely |
| Cloud object storage (Amazon S3), adjacent topic | **[PYQ 2025] Amazon S3 (5M)** | - | Likely | - | - | - | - |

### 3.3 Parallel databases and MapReduce

| Topic | Note | Long | Diag | Cmp | Num | Case | Obj |
|---|---|---|---|---|---|---|---|
| Why parallel databases | Likely | - | - | - | - | - | Likely |
| Shared memory / shared disk / shared nothing | Likely | Likely | Likely (3 diagrams) | Likely (review question 1 in notes) | - | - | Likely |
| Partitioning and data skew | Likely | - | Likely | - | - | Likely | Likely |
| MapReduce model (map, shuffle, reduce) | **[PYQ 2025] Explain Map Reduce model with example (5M)** | Likely | Likely (flow diagram) | - | Likely (trace word count) | **[PYQ 2025] with example** | Likely |
| MapReduce fault tolerance | Likely | Likely | Likely (failure scenario) | - | - | Likely (2 workers fail - notes slide 20) | Likely |
| Efficiency (locality, skew, speedup, Amdahl) | Likely | - | - | - | Likely (speedup and efficiency; notes define formulas) | - | Likely |
| Applications of MapReduce | Likely | - | - | - | - | Likely (design failed-login counter, log analyzer) | Likely |
| MapReduce vs parallel/MPP database; limitations | Likely | - | - | Likely | - | - | Likely |

---

## 3. TOPIC-BY-TOPIC BREAKDOWN

General exam strategy for every topic: 5 marks = 5 to 6 crisp points plus one small labelled diagram or example. 10 marks = definition, diagram, working/steps, advantages, limitations, example, (and a comparison table if a similar system exists).

---

# PART 3.1 - RELATIONAL DATABASES

## 3.1.0 Foundations (needed to start any answer)

**Data** = raw facts (student marks, bank transactions, sensor readings). **Database** = organized collection of related data stored electronically for easy access, retrieval, modification, management. Characteristics: organized structure, reduced redundancy, data integrity, easy retrieval, security, multi-user access.

**Why databases?** Without: duplicate data, difficult search, slow updates, inconsistency. With: faster search, better security, efficient storage, concurrent access, backup and recovery.

**DBMS vs RDBMS**

| DBMS | RDBMS |
|---|---|
| Software to create, store, retrieve, update, delete data and manage users/security | A DBMS based on the relational model: data in tables (relations) |
| Need not store data in related tables (document, key-value, graph DBs are non-relational DBMSs) | Tables related using keys |
| Example: MongoDB, Redis | Example: Oracle, MySQL, PostgreSQL, SQL Server, IBM DB2 |

**Components of an RDBMS**

- Table (relation): one entity (Student, Employee).
- Row (tuple/record): one complete record, e.g. `101 | Rahul | Computer | 20`.
- Column (attribute): one property (Name, Department, Age).
- Primary key: uniquely identifies each row (StudentID).
- Foreign key: links tables (Student.DepartmentID refers to Department.DepartmentID).

```
STUDENT                                   DEPARTMENT
+-----------+--------+--------------+     +--------------+----------------+
| StudentID | Name   | DepartmentID |     | DepartmentID | DepartmentName |
|   (PK)    |        |    (FK)      |     |     (PK)     |                |
+-----------+--------+--------------+     +--------------+----------------+
|   101     | Rahul  |     D1       |---->|     D1       | Computer       |
|   102     | Priya  |     D2       |---->|     D2       | IT             |
+-----------+--------+--------------+     +--------------+----------------+
```

Why RDBMS is popular: structured format, SQL, consistency, ACID, strong security, standard model.

---

## 3.1.1 DATA STORAGE TECHNIQUES

**Definition (use as opening line):** A relational database stores data as tables of rows and columns, and the DBMS uses different physical storage techniques to decide how those rows are laid out on disk and how quickly they can be found, inserted and updated.

There are 12 techniques in the notes. Learn them as three groups:

- Layout of data: table-based, row-oriented, column-oriented
- File organization and access paths: heap, sequential, indexed, hash, B/B+ tree
- Optimization: partitioning, compression, normalization, pages/blocks

### 1. Table-based storage
Each table = one entity, each row = one record, each column = one attribute, each table has a unique name. Advantages: simple organization, easy retrieval and maintenance, efficient SQL support.

### 2. Row-oriented storage
All values of one record are stored together (contiguously).

```
Row store on disk:
[101,Rahul,Comp,85] [102,Priya,IT,97] [103,Amit,Mech,70] ...
```
- Good for: OLTP, INSERT/UPDATE/DELETE, fetching a complete record. Banking, e-commerce, ERP.
- Bad for: analytical queries touching few columns (reads unnecessary data).

### 3. Column-oriented storage
Values of the same column are stored together.

```
Column store on disk:
ID:    [101,102,103,...]
Name:  [Rahul,Priya,Amit,...]
Marks: [85,97,70,...]
```
- Good for: OLAP, aggregates (SUM, AVG, COUNT), data warehouses, excellent compression.
- Bad for: slow insert/update, not suited to frequent transactions.

**Row vs column (high-probability 5-mark compare)**

| Point | Row-oriented | Column-oriented |
|---|---|---|
| Stored together | All values of one record | All values of one column |
| Best workload | OLTP | OLAP |
| Full-record fetch | Fast | Slow |
| Aggregate on one column | Slow (reads all columns) | Fast |
| Insert/update | Fast | Slow |
| Compression | Moderate | Excellent |
| Use | Banking, ERP | Data warehouse |

### 4. Heap file organization
Records stored in no particular order, inserted wherever free space exists (usually at the end). Fast insertion, simple, no ordering to maintain. Slow search (full table scan).

### 5. Sequential file organization
Records stored sorted by primary key. Fast sequential access, efficient range queries. Slow insertion/deletion, reorganization needed.

**Heap vs sequential:** heap = fast insert, slow search, unordered; sequential = slow insert, fast range/ordered access, sorted by key.

### 6. Indexed storage
An index is a separate structure storing the location of records, like the index of a textbook.

```
INDEX                     TABLE (data)
StudentID | Pointer       Addr | StudentID | Name
   101    | ---> A1       A1   |   101     | Rahul
   102    | ---> A2       A2   |   102     | Priya
   103    | ---> A3       A3   |   103     | Amit
Search StudentID=102: look up index -> go straight to A2 (no full scan)
```

Types:
- **Primary index:** on the primary key (usually created automatically by many DBMSs, exact behaviour depends on DBMS).
- **Secondary index:** on a non-primary-key attribute (e.g. Name, Department) so queries on that column can use it.
- **Clustered index:** determines (or closely corresponds to) the physical order of table rows; the leaf level holds the actual data (e.g. SQL Server). Only one per table.
- **Non-clustered index:** separate structure with pointers to rows; the table stays separate; a table can have many.

| Clustered | Non-clustered |
|---|---|
| Defines physical order of data | Separate from data |
| Leaf level contains actual rows | Leaf level contains pointers to rows |
| One per table | Many per table |
| Faster range retrieval | Extra lookup step to fetch the row |

Advantages of indexing: very fast search, efficient sorting, faster joins. Disadvantages: extra storage, slightly slower insert/update (index must be updated).

### 7. Hash-based storage
A hash function converts the key into a bucket (storage location): `Hash(Key) -> Bucket`. Average O(1) equality lookup. Poor for range queries; collisions must be handled.

### 8. B-Tree and B+ Tree
Most relational DBs use B+ trees for indexes. Balanced tree; search, insert, delete all O(log n); supports range queries. In a B+ tree all data pointers sit in the leaf level and leaves are linked in sequence, so range scans are fast.

```
                [ 50 | 100 ]                  <- root / internal nodes (keys only)
               /     |      \
      [10|30]    [60|80]    [110|150]         <- internal nodes
       /  |  \    /  |  \     /   |   \
     leaf-->leaf-->leaf-->leaf-->leaf-->leaf  <- leaves hold record pointers,
                                                 linked left to right
```

### 9. Partitioning
Big tables split into smaller partitions. Types: horizontal (split rows), vertical (split columns), range, hash, list. Advantages: faster queries, easier maintenance, scalability.

### 10. Compression
Reduces storage. Types: row, column, dictionary, run-length encoding (RLE). Advantages: saves disk, faster backups, better cache performance.

### 11. Normalization
Organize data into multiple related tables to remove redundancy.

```
BEFORE                                     AFTER
Student  | Department                      Student:  ID  | Name  | DeptID
Rahul    | Computer                                  101 | Rahul | D1
Rahul    | Computer     (duplicate)        Department: DeptID | Department
                                                       D1     | Computer
```
Advantages: reduced redundancy, improved consistency, easier maintenance.

### 12. Data pages and blocks
DB stores data in fixed-size pages/blocks, not individual records. Advantages: efficient disk I/O, better caching, faster access.

### Comparison of techniques (from notes, slide 49 - memorize)

| Technique | Best for | Search speed | Insert speed | Storage efficiency |
|---|---|---|---|---|
| Heap | Frequent inserts | Slow | Very fast | Good |
| Sequential | Ordered data | Medium | Slow | Good |
| Indexed | Fast retrieval | Very fast | Medium | Medium |
| Hash | Exact-match search | Very fast | Fast | Medium |
| B+ tree | General purpose | Very fast | Fast | Good |
| Row | OLTP | Fast | Fast | Good |
| Column | OLAP / warehouse | Very fast (analytics) | Slow | Excellent |
| Partitioning | Very large tables | Fast | Fast | Excellent |

### Applications (from notes)
Banking: row storage + B+ tree indexes. E-commerce: indexed + partitioned. Data warehouses: column storage + compression. Hospital systems: row storage + indexes. Library systems: B+ tree + normalization. Online reservation: indexed + hash-based.

### Scenario question (notes slides 18-19, very likely style)
University Student Information System - which technique?
- Recording fee payments -> row-oriented (many small inserts/updates, whole records)
- Department-wise performance reports -> column-oriented (aggregates over few columns)
- Search student by roll number -> indexed storage
- Bulk admission import -> heap file (fast insertion, no ordering)

### How to write it in the exam
- "Explain data storage techniques in RDBMS" (10M): one-line definition, list the techniques in the three groups, then explain 5-6 with a tiny layout diagram each (row vs column, index, B+ tree), add the comparison table, end with applications.
- "Compare row and column storage" (5M): the table above, 6 rows, plus one line each on OLTP/OLAP.
- "Clustered vs non-clustered index" (5M): table above plus a sketch.

### Numericals / problems for this section [ADDED - practice problems, notes only give concepts]

**N1. Row vs column read cost.** Table: 1,000,000 rows, 10 columns, 8 bytes per value. Query: AVG of one column.
- Row store must read all columns: 1,000,000 x 10 x 8 = 80,000,000 bytes = 80 MB.
- Column store reads only that column: 1,000,000 x 8 = 8,000,000 bytes = 8 MB.
- Column store reads 10x less data (before compression). That is why OLAP prefers column storage.

**N2. Search cost by organization.** File has 1,000 blocks, search for a unique key.
- Heap: linear scan, average 1000/2 = 500 block reads (worst 1000).
- Sequential (sorted by key): binary search, about log2(1000) = about 10 block reads.
- Hash: about 1 block read on average.
- B+ tree with fan-out 100 and 1,000,000 records: height = log100(10^6) = 3, so about 3 index reads + 1 data read = 4.

**N3. Hash bucket assignment and collision.** `h(key) = key mod 7`, keys 101, 103, 105, 110.
- 101 mod 7 = 3 (7 x 14 = 98, remainder 3)
- 103 mod 7 = 5 (98 + 5)
- 105 mod 7 = 0 (7 x 15 = 105)
- 110 mod 7 = 5 (105 + 5)
- Keys 103 and 110 both go to bucket 5: a collision, which must be handled (chaining/overflow bucket).

**N4. Normalize this table.** `Orders(OrderID, CustName, CustCity, Item, Price)` where CustName and CustCity repeat for every order.
- Split into `Customer(CustID, CustName, CustCity)` and `Orders(OrderID, CustID, Item, Price)` with CustID as foreign key. Redundancy removed, update a city in one place only.

---

## 3.1.2 DEFAULT DATA STORAGE AND RETRIEVAL MECHANISM SINCE THE 1980s

**Statement to open with:** From the 1980s onward, relational databases (RDBMS) with SQL have been the default way enterprises store and retrieve structured data, because they are simple (tables), reliable (ACID), standardized (SQL) and secure.

### Evolution
1. **File-based systems (before 1980):** text/CSV/binary files (e.g. Student.txt). Problems: redundancy, inconsistency, difficult search, no relationships between files, poor security, difficult backup.
2. **Hierarchical model:** tree structure. Fast parent-child access but rigid, difficult many-to-many relationships.
3. **Relational model (1970):** Dr. Edgar F. Codd proposed data in tables manipulated with relational algebra. Commercial RDBMS spread and became the standard from the 1980s (Oracle, IBM DB2, SQL Server, MySQL, PostgreSQL).

```
File systems  --->  Hierarchical DB  --->  Relational DB (Codd 1970; default from 1980s)  --->  NoSQL / cloud storage
 (flat files)       (tree, rigid)          (tables + SQL + ACID)                              (GFS, BigTable, Dynamo)
```

### Why RDBMS became the default
Table structure (easy), reduced redundancy (normalization), standard SQL, improved consistency, easier maintenance, strong security, reliable transaction processing.

### Client-server database architecture

```
+-------------+    SQL query     +------------------+   reads/writes   +----------------------+
|   CLIENT    | ---------------> |  DATABASE SERVER | ---------------> |   STORAGE SYSTEM     |
| (app/web/   | <--------------- | (MySQL/Oracle/   | <--------------- |  HDD / SSD / RAID    |
|  ERP/HMS)   |   result set     |  PostgreSQL)     |                  |  (database files)    |
+-------------+                  +------------------+                  +----------------------+
 sends SQL, shows results         stores data, processes SQL,           holds the actual files
                                  executes transactions, users,
                                  security, backup
```

Example: student logs into college portal -> app sends SQL -> DB server processes it -> reads from disk -> returns the result.

### SQL-based retrieval
SQL is the standard language to talk to an RDBMS.
```sql
SELECT * FROM Student;                          -- all records
SELECT Name, Marks FROM Student;                -- specific columns
SELECT * FROM Student WHERE StudentId = 102;    -- particular student
INSERT INTO Student VALUES (103,'Amit',70);
UPDATE Student SET Marks = 90 WHERE StudentId = 101;
DELETE FROM Student WHERE StudentId = 103;
```

### ACID properties (very high probability - write all four with the bank example)

| Letter | Meaning | Example |
|---|---|---|
| Atomicity | Transaction is one unit: all or nothing | Transfer Rs 5,000 A -> B: if debit happens but credit fails, roll back; no partial update |
| Consistency | Database moves from one valid state to another | CGPA cannot exceed maximum; invalid data rejected; total money unchanged |
| Isolation | Concurrent transactions do not interfere | Two users book the last train seat; only one succeeds |
| Durability | Committed data survives crashes | Payment record preserved despite power failure |

**Case study (notes slide 74): online banking** - Atomicity: both debit and credit occur or neither. Consistency: balances remain valid. Isolation: simultaneous transfers do not interfere. Durability: once confirmed, the transfer is permanently recorded.

### Transaction management
A transaction is a sequence of operations performed as one logical unit.
```
BEGIN TRANSACTION
  Debit Account A
  Credit Account B
COMMIT          (on error: ROLLBACK)
```
Transaction states (diagram in notes):
```
Normal path:   Start --> Active --> Partially Committed --> Committed
Error path:    Active --> Failed --> Rollback (aborted)
```

### Concurrency control
Many users access the DB simultaneously. Without control: lost updates, dirty reads, inconsistent data. Example: balance Rs 10,000; A withdraws 2,000 and B withdraws 3,000 at once; without control one overwrites the other. Techniques: lock-based protocols, timestamp ordering, Multiversion Concurrency Control (MVCC).

**Numerical (lost update trace) [ADDED style, uses the notes' numbers]**

| Step | Transaction A | Transaction B | Balance in DB |
|---|---|---|---|
| 1 | Read balance = 10,000 | | 10,000 |
| 2 | | Read balance = 10,000 | 10,000 |
| 3 | Write 10,000 - 2,000 = 8,000 | | 8,000 |
| 4 | | Write 10,000 - 3,000 = 7,000 | 7,000 |

Correct final balance = 10,000 - 2,000 - 3,000 = 5,000, but DB shows 7,000: A's update is lost. With locking, B waits until A commits, then reads 8,000 and writes 5,000.

### Advantages of traditional RDBMS
Structured storage, SQL, ACID, integrity, security, mature technology, reliable backups; suited to banking, ERP, healthcare, university systems.

### Limitations in cloud computing (this is the bridge to 3.2 - frequently asked as "why not RDBMS in cloud")
- Vertical scaling (more CPU/RAM) has limits.
- Hard to distribute across thousands of servers.
- Schema changes can be complex.
- Less suitable for rapidly changing or unstructured data.
- High licensing cost for some enterprise databases.

These limitations motivated GFS, BigTable, Amazon Dynamo and NoSQL.

### How to write it in the exam
- "Why did relational DBs become the default since the 1980s?" (5-10M): evolution (file -> hierarchical -> relational), Codd 1970, 5-6 reasons, client-server diagram, SQL, ACID, limitations in cloud.
- "Explain ACID with example" (5M): table above + bank transfer.


---

# PART 3.2 - CLOUD FILE SYSTEMS

## 3.2.0 Why cloud file systems (linking sentence for every answer)

Cloud applications produce data far beyond one server. Storage must survive machine, disk and network failures, so data is spread over many commodity machines, with replication, partitioning and metadata management as the building blocks. Different workloads need different trade-offs among consistency, availability and performance, which is why we have four systems:

| System | Idea |
|---|---|
| GFS | Distributed file system for very large files, high throughput |
| BigTable | Scalable structured, sparse data on top of GFS |
| Dynamo | Highly available key-value store (Amazon) |
| Datastore | Managed NoSQL for application entities (Google) |

---

## 3.2.1 GOOGLE FILE SYSTEM (GFS)

**Definition:** GFS is a scalable distributed file system developed by Google to store and process massive data across thousands of inexpensive commodity servers, giving high performance, fault tolerance and reliability for data-intensive applications. Used by Search, Gmail, Maps, YouTube.

**Why built:** traditional file systems have limited capacity, single point of failure, hard to scale, poor fault tolerance, high hardware cost. Google needed: huge files, thousands of servers, survive hardware failure, high-speed access, automatic recovery.

**Features:** distributed storage, high scalability, fault tolerance via replication, high throughput, automatic failure recovery, optimized for large files, concurrent access by many clients.

### Architecture (draw this; it is the most likely diagram)

```
                         +---------------------------+
                         |       GFS MASTER          |
                         |  (metadata only)          |
                         |  - file names, directories|
                         |  - file -> chunk mapping  |
                         |  - chunk locations        |
                         |  - access permissions     |
                         +---------------------------+
                           ^  1. request metadata   |
              ------------ |                        | 2. chunk handle + locations
             |             |                        v
        +---------+--------+------------------------+
        |  GFS CLIENT (Search, Gmail, Maps ...)     |
        +---------+---------------------------------+
                  | 3. read/write data DIRECTLY (master not involved)
      +-----------+-------------+---------------+
      v                         v               v
+--------------+        +--------------+  +--------------+
| CHUNKSERVER 1|        | CHUNKSERVER 2|  | CHUNKSERVER 3|   ... each stores many
| chunk replicas|       | chunk replicas|  | chunk replicas|   64 MB chunks (Linux files)
+--------------+        +--------------+  +--------------+
      ^------ heartbeat messages to master, replication between chunkservers ------^
```

**Three components**
1. **GFS Client:** application using GFS. Asks Master for metadata, then talks to chunk servers directly to read/write.
2. **Master Server:** the brain. Stores only metadata: file names, directory structure, chunk IDs and locations, permissions, replication info. Also monitors chunk servers, manages replication, detects failures.
3. **Chunk Servers:** store the actual data in fixed-size chunks; each stores many chunks.

### File storage in GFS
File is split into 64 MB chunks (original design), each with a unique chunk handle (ID); chunks go to different chunk servers.

**Numerical (notes slide 10 and 18, high probability)**
- 180 MB file: Chunk 1 = 64, Chunk 2 = 64, Chunk 3 = 52 MB -> 3 chunks. With 3 replicas: 3 x 3 = 9 chunk copies.
- 200 MB video: 200 / 64 = 3.125 -> 4 chunks (64, 64, 64, 8 MB). With 3 replicas: 12 chunk copies spread across chunk servers. If one chunk server fails: Master detects via heartbeat, redirects clients to another replica, creates a new replica to restore 3 copies.
- General formula: number of chunks = ceiling(file size / 64 MB); total copies = chunks x replication factor.

**Extra numerical [ADDED]:** 1 GB file = 1024 MB / 64 = 16 chunks; 3 replicas = 48 copies; raw storage used = 3 GB. Metadata sizing: the GFS paper says the master keeps under about 64 bytes per chunk, so 1 PB = 2^50 / 2^26 = 16,777,216 chunks x 64 B = about 1 GiB of metadata, small enough to hold in master memory. This is why 64 MB chunks (few chunks) keep metadata tiny.

### Read operation (5 steps)
1. Client asks Master for metadata (file name + chunk index).
2. Master returns chunk server locations (chunk handle + replica list).
3. Client contacts a chunk server directly.
4. Chunk server sends the data.
5. Master is not involved in the data transfer (this prevents it from becoming a bottleneck).

### Write operation (6 steps)
1. Client asks Master for chunk information.
2. Master identifies the Primary chunk server (and replicas).
3. Client sends data to all replicas.
4. Primary coordinates the write (orders it).
5. Secondary replicas perform the write.
6. Confirmation returned to the client.

```
WRITE:  Client --1--> Master          Client --3--data--> Primary  --\
        Client <--2-- Master                          \--> Secondary 1 \--> 4/5: Primary orders,
                                                       \--> Secondary 2    secondaries apply
        Client <--------------- 6. ack ------------------ Primary
```

### Replication and fault tolerance
- Each chunk stored on multiple chunk servers, typically 3 replicas -> data available if one fails, better reliability, load balancing.
- Chunk server fails: Master detects through heartbeat messages -> clients redirected to another replica -> Master creates a new replica to restore the replication level. No manual intervention.

### Advantages / Limitations / Applications
- Advantages: scalable, handles petabytes, high throughput, low-cost hardware, automatic recovery, supports distributed computing, optimized for large sequential reads/writes.
- Limitations: poor for many small files, Master can become a bottleneck, heavy network traffic during replication, tuned for Google workloads, not for low-latency random access.
- Applications: search engines, web indexing, analytics, machine learning, video storage/streaming, email, cloud storage; storage layer under MapReduce.

### Traditional file system vs GFS (notes slide 19 - memorize as a table)

| Feature | Traditional FS | GFS |
|---|---|---|
| Storage | Single server | Distributed servers |
| Scalability | Limited | Very high |
| Fault tolerance | Low | High |
| Replication | Usually no | Yes |
| File size support | Small to medium | Very large |
| Availability | Moderate | High |
| Hardware | High-end servers | Commodity hardware |
| Recovery | Manual | Automatic |
| Throughput | Moderate | High |

**Extra GFS facts [ADDED]:** The original paper also describes an operation log + checkpoints for master recovery (metadata survives master restart), leases granted by the Master to the primary replica, and "record append" for many clients appending concurrently; consistency is relaxed (not as strict as a normal file system). Mention one or two in a 10-marker only if you are sure.

### How to write it in the exam
10M: definition, why built, diagram (above), three components with roles, chunk storage with the 180 MB example, read steps, write steps, replication + heartbeat, advantages and limitations, comparison with traditional FS. 5M: definition + diagram + master/chunkserver roles + chunk/replication + 2 advantages.

---

## 3.2.2 BIGTABLE STORAGE

### NoSQL introduction (opening of any BigTable/Dynamo answer)
NoSQL ("Not Only SQL") = non-relational databases for very large volumes of structured, semi-structured and unstructured data: horizontal scalability, high availability, fault tolerance, flexible schema, faster access to large datasets.

**Traditional (relational) DB vs NoSQL** [ADDED where noted; slide 21 is an image of this table, so this is a faithful summary]

| Feature | Relational DB | NoSQL |
|---|---|---|
| Model | Tables, fixed schema | Key-value / column-family / document / graph, flexible schema |
| Scaling | Vertical (bigger server) | Horizontal (more machines) |
| Joins | Supported | Generally avoided |
| Transactions | Full ACID | Limited / eventual consistency (varies) |
| Best for | Structured data, banking | Massive, fast-changing, distributed data |
| Examples | MySQL, Oracle | BigTable, Dynamo, MongoDB |

### Definition
Google BigTable is a distributed, scalable, column-family NoSQL database that stores petabytes of structured data across thousands of commodity servers, for applications needing high scalability, high performance, low latency and fault tolerance.

**Features:** distributed architecture, column-family storage, automatic partitioning, dynamic scalability, fault tolerance, data replication, high throughput, sparse data storage, billions of rows.
**Applications:** Google Search, Gmail, Maps, Earth, Analytics, YouTube, Finance; IoT, ML datasets, real-time analytics, logging.

### Data model: (Row key, Column family:Column, Timestamp) -> Value

```
Row key   | Column family: Personal      | Column family: Contact          | Timestamps
          |  Name      Age               |  Email         Mobile   Address |
----------+------------------------------+---------------------------------+------------
user001   |  Asha      21                |  asha@x.com    98xxxx   -       | each cell can hold
user002   |  Rahul     22                |  rahul@x.com   -        -       | many timestamped
user003   |  Amit      -                 |  -             97xxxx   -       | versions
```
- **Row key:** unique ID, sorted lexicographically, determines physical storage order, immutable after creation.
- **Column family:** logical group of related columns (Personal, Contact, Education, Salary); a unit of storage/management.
- **Column:** inside a family; different rows may have different columns -> sparse data efficient (empty cells cost nothing).
- **Timestamp:** each cell stores multiple versions (e.g. Salary 2024: 50,000; 2025: 55,000; 2026: 60,000) -> versioning and history.

### Architecture (draw it)

```
                  +------------------+          +-------------------+
                  |     CLIENT       |<-------->|  CHUBBY           |
                  +--------+---------+          |  (distributed lock|
          data reads/writes|    ^ tablet info   |   service: master |
                           |    |               |   election, sync, |
        +------------------+----+-------+       |   failure detect) |
        v                  v            v       +---------+---------+
 +--------------+  +--------------+  +--------------+     |
 | TABLET SERVER|  | TABLET SERVER|  | TABLET SERVER|<----+  BigTable MASTER:
 |  Tablet A, B |  |  Tablet C    |  |  Tablet D    |        assigns tablets, load
 +------+-------+  +------+-------+  +------+-------+        balancing, failure recovery
        |                 |                 |                 (not in the data path)
        +-----------------+-----------------+
                          v
              GOOGLE FILE SYSTEM (GFS)
              stores SSTable files + commit logs, replicated
```

Built on three Google technologies: GFS, Chubby, SSTable.
- **Client:** sends read/write requests to tablet servers.
- **Master:** assigns tablets to tablet servers, load balancing, recovery after failures, monitors tablet servers; does NOT handle data access in normal reads/writes.
- **Tablet server:** stores/reads/writes tablets, splits large tablets, serves client requests.
- **GFS:** stores SSTable files, replication, fault tolerance.
- **Chubby:** distributed lock service: master election, synchronization, metadata management, failure detection.
- **Tablet:** horizontal partition of a BigTable (parallel processing, load balancing, easy scaling).
- **SSTable (Sorted String Table):** immutable file, sorted by row key, fast search, efficient storage, better compression.

### Read and write operations

```
WRITE: Client -> Tablet Server -> (1) commit log (durability, on GFS)
                               -> (2) MemTable (in memory)
                               -> (3) MemTable full? flush to disk as new SSTable
                               -> (4) background compaction merges SSTables
READ:  Client -> Tablet Server -> locate row -> fetch from SSTable(s) (and MemTable) -> return result
```

### Advantages / Limitations
- Advantages: highly scalable, high performance, billions of rows, fault tolerant, automatic load balancing, distributed storage, efficient for sparse data, flexible schema.
- Limitations: no complex SQL joins, limited transaction support vs RDBMS, complex architecture, optimized for Google infrastructure, not for complex relational queries.

### BigTable vs RDBMS (notes slide 44)

| Feature | BigTable | Relational DB |
|---|---|---|
| Type | NoSQL | SQL |
| Schema | Flexible | Fixed |
| Scalability | Horizontal | Vertical |
| Storage | Column family | Tables |
| Joins | Not supported | Supported |
| Transactions | Limited | Full ACID |
| Performance | Excellent for big data | Good for structured data |
| Fault tolerance | High | Moderate |
| Data size | Petabytes | Gigabytes to terabytes |

### BigTable vs GFS (notes slide 45)

| Feature | GFS | BigTable |
|---|---|---|
| Type | Distributed file system | NoSQL database |
| Stores | Files | Structured data |
| Data unit | Chunks | Tablets |
| Storage | File-based | Column-family |
| Uses | Large file storage | Structured data storage |
| Depends on | Standalone | Built on GFS |

### How to write it in the exam
10M: NoSQL one-liner, BigTable definition, features, data model with the sparse student table, architecture diagram with Chubby/GFS/SSTable, read/write path, advantages/limitations, BigTable vs RDBMS table. 5M: definition + data model + one diagram + 4 features.

---

## 3.2.3 DYNAMO ARCHITECTURE

**Definition:** Dynamo is Amazon's highly available, distributed key-value storage system for applications needing very high availability, scalability, low latency and fault tolerance, even when servers fail. Used for shopping carts, product catalogs, customer preferences, sessions. Design philosophy: it is better to remain available and accept temporary inconsistency than to become unavailable during failures.

**Why needed:** RDBMS struggle with millions of users, huge request volume, continuous availability, geographically distributed servers, very low latency. Example: shopping cart service depending on one Server A would be unavailable when A fails; Dynamo spreads and replicates data so no single failure stops the application. Uses partitioning, replication, distributed nodes, failure detection, recovery.

**Characteristics:** distributed, decentralized (no central DB server), highly available, fault tolerant (disk/server/network/software/power failure), scalable (add nodes), eventually consistent.

**Data model:** simple key -> value.
```
User101     -> { Name: "John", Cart: "Product101, Product205" }
Product1001 -> { Name: "Laptop", Price: 65000 }
```
Simple model, schema flexibility, fast key-based access, no complex joins.

### Architecture diagram: the hash ring

```
                      Node A
                  .-----o-----.
               .'               '.
         Node D o                 o Node B        Keys and nodes hash onto the SAME ring.
               '.               .'                A key is stored on the first node found
                  '-----o-----'                   clockwise from its hash position, and
                      Node C                      replicated on the next N-1 nodes clockwise.
```

Major mechanisms (memorize the list): **partitioning, replication, consistency, versioning, failure handling, membership management.**

### Consistent hashing
Decides which node stores which key. Problem with simple hashing `hash(key) % number_of_servers`: when a server is added or removed, many keys have to move. Consistent hashing places nodes and keys on a logical ring so only a small portion moves.
Advantages: scalability (add servers without moving all data), fault tolerance (neighbours/replicas handle a failed node's data), reduced data movement, dynamic membership (join/leave/fail/recover without stopping the system).

**Numerical [ADDED, standard example]**
*Part 1: modulo hashing is wasteful.* Keys 0 to 19, going from 4 servers (`k mod 4`) to 5 servers (`k mod 5`). A key stays only if `k mod 4 = k mod 5`; this holds only for k = 0, 1, 2, 3. So 16 of 20 keys (80%) move.
*Part 2: ring.* Ring positions 0-99, nodes A=10, B=35, C=60, D=85; a key goes to the first node at or after its position clockwise (wrapping around).

| Key | Owner |
|---|---|
| 5 | A (10) |
| 20 | B (35) |
| 40 | C (60) |
| 70 | D (85) |
| 90 | A (wraps past 99 to 10) |

Add node E at 50: only keys in (35, 50] change owner, so key 40 moves from C to E; all other keys unchanged (1 of 5 keys; ideally about 1/n). If D fails, key 70 simply moves to the next node clockwise, A. With N = 3 the preference list for key 20 is B, C, D (owner and next two nodes).

### Virtual nodes (vnodes)
Instead of one position per physical server, each server owns multiple positions on the ring. Benefits: better load balancing, easier add/remove of nodes, better failure recovery, more uniform data distribution.

### Data partitioning and replication
Data space is divided into partitions assigned to nodes (e.g. 1 million keys over 4 nodes = 250,000 keys each). Replication factor N = number of copies (N=3 -> 3 replicas; N=5 -> 5 replicas). Benefits: high availability, fault tolerance, durability, lower data-loss risk. Higher N increases storage, network traffic, synchronization overhead.

### Consistency: eventual consistency
Replicas may briefly differ, but if no new updates occur all replicas converge.
```
Initially:      A=Rs50  B=Rs50  C=Rs50
After update:   A=Rs60  B=Rs60  C=Rs50   (temporary inconsistency)
After sync:     A=Rs60  B=Rs60  C=Rs60   (converged)
```
Advantage: high availability, low latency, scalability. Disadvantage: different users may temporarily see different versions.

### Quorum: N, R, W
N = replicas, R = replicas that must respond to a read, W = replicas that must acknowledge a write. Condition **R + W > N** makes read and write sets overlap, so a read sees at least one replica that took the latest write.

**Numericals (notes example plus extra variations [ADDED])**

| N | R | W | R+W | R+W > N ? | Meaning |
|---|---|---|---|---|---|
| 3 | 2 | 2 | 4 | Yes (4 > 3) | Notes example. Read and write sets overlap; tolerates 1 node down for both reads and writes |
| 3 | 1 | 1 | 2 | No | Fast, but a read may return stale data (eventual consistency) |
| 3 | 1 | 3 | 4 | Yes | Reads are fast and fresh; writes are slow and fail if any one replica is down |
| 3 | 3 | 1 | 4 | Yes | Writes are fast; reads slow, need all replicas |
| 5 | 3 | 3 | 6 | Yes (6 > 5) | Tolerates 2 failed nodes for reads and writes |

Rule of thumb: writes tolerate N - W unavailable replicas, reads tolerate N - R. Why overlap works with 3/2/2: write reached replicas {A,B}; a read of any 2 replicas, e.g. {B,C} or {A,C}, must include A or B, so at least one fresh copy is seen.

### Failure detection and hinted handoff
Failure is normal. Dynamo detects unreachable nodes and redirects operations to other replicas. **Hinted handoff:** if the intended replica (Node C) is down, another node (Node D) temporarily stores the data with a hint saying whom it belongs to; when C recovers, D sends the data to C.
```
Data X belongs on A, B, C.   C is down.
A: X   B: X   C: (down)   D: temporary copy of X (hint: for C)
C recovers  ->  D --sends X--> C   (D deletes its temp copy)
```

### Versioning and conflict resolution: vector clocks
Replicas can accept updates independently, so conflicting versions arise (two users modify the same cart). Dynamo tracks versions with vector clocks to decide whether one version is newer or two are concurrent.
- `[A:1]` then `[A:2]`: version 2 derives from version 1 (newer; old one can be discarded).
- `[A:1]` vs `[B:1]`: concurrent updates, a conflict that needs resolution (e.g. merge the two shopping carts).
- Rule: version X descends from Y if every counter in X is >= the matching counter in Y; if neither descends from the other, they conflict. Example [ADDED]: `[A:2,B:1]` vs `[A:1,B:2]` -> concurrent; `[A:2,B:1]` vs `[A:1]` -> first is newer.

### Real-life walkthrough (notes slides 111-113): customer adds iPhone to cart
1. Key = Customer ID C101. 2. hash(C101) decides which node owns it. 3. Cart replicated to Node A, B, C. 4. Node B fails; A and C still serve. 5. Hinted handoff stores data temporarily elsewhere. 6. Failed node returns, receives data back. 7. Replicas synchronize and become consistent.

### Dynamo vs Datastore (notes slide 110)

| Feature | Dynamo | Google Datastore |
|---|---|---|
| Developed by | Amazon | Google |
| Type | Distributed key-value store | NoSQL document/entity database |
| Data model | Key -> Value | Kind -> Entity -> Properties |
| Major focus | Very high availability | Scalable application database |
| Consistency | Primarily eventual | Supports different guarantees |
| Partitioning | Consistent hashing | Distributed automatically |
| Replication | Yes | Yes |
| Failure handling | Sloppy quorum, hinted handoff | Managed by Google |
| Version handling | Vector clocks | Managed database mechanisms |
| Query model | Primarily key-based | Property-based queries and indexes |
| Typical use | Amazon internal services | Google App Engine applications |

**CAP positioning [ADDED]:** CAP says a distributed system under network partition must choose between consistency and availability. Dynamo chooses availability (AP, eventual consistency). GFS/BigTable lean toward consistency with a single coordinating master/row-level consistency. State this only as a one-line remark.

### How to write it in the exam
10M: definition + design philosophy, why needed (cart example), characteristics, key-value model, ring diagram, consistent hashing + vnodes, replication N, eventual consistency, quorum with 3/2/2 example, hinted handoff, vector clocks. 5M: pick any 4 mechanisms: consistent hashing, replication, quorum, hinted handoff.

---

## 3.2.4 DATASTORE

**Definition:** In cloud computing a datastore is a storage system used to store, organize, manage and retrieve data in the cloud, designed for scalability, availability, reliability, accessibility and fault tolerance. In Google Cloud context, Cloud Datastore is a highly scalable managed NoSQL database, historically Google App Engine Datastore, now delivered as **Firestore in Datastore mode**. It stores customer records, student info, catalogs, transactions, media, logs, IoT data, sessions, documents.

**Why datastores (problems with local disk):** limited storage (1 TB server, need 10 TB), server failure (app unavailable and data inaccessible; solved by replication), growing users (1,000 -> 10,000 -> 1,000,000), global access (India, USA, Europe, Singapore, Australia use one datastore).

**Characteristics**
1. Scalability: more data/users/requests/transactions. Vertical scaling = stronger single server (4 cores/16 GB -> 32 cores/128 GB). Horizontal = add more machines; cloud-native datastores prefer this.
2. Availability: stays accessible when a machine fails (redundancy, replication, multiple availability zones).
3. Durability: stored data is not lost (multiple replicas).
4. Fault tolerance: continues despite server, disk, network, software or availability-zone failure.
5. Data persistence: data survives app shutdown, server/VM/container restart; important as cloud instances are created and destroyed often.

**Types of cloud datastores:** relational, key-value, document, column-family, graph, object storage, file storage, block storage, in-memory.

### Data model: Kind -> Entity -> Properties, identified by Key

```
Kind = Student
  |-- Entity (Key: Student + 101)   { studentId:101, name:"Rahul", course:"CSE", age:20 }
  |-- Entity (Key: Student + 102)   { studentId:102, name:"Priya", course:"IT", age:21, email:"..." }
```
- **Entity:** one object (like a row).
- **Kind:** category grouping similar entities (like a table).
- **Properties:** attributes of an entity (like columns); entities of the same kind can have different properties (flexible schema).
- **Key:** unique identity = Kind + ID (or string name).
- **Ancestor/hierarchy:** entities organized in parent-child paths, e.g. University/ABC -> Department/CSE -> Student/101.

Relational mapping: Table = Kind, Row = Entity, Column = Property, Foreign key = key/ancestor relationship.

### Indexing, queries, transactions, consistency
- **Indexing:** indexes make queries efficient (e.g. index on course = "CSE" lists students 101, 105, 109). Many queries depend on indexes.
- **Queries:** by properties, e.g. `Kind = Student WHERE course = "CSE"`, `age > 20`, `course = "CSE" AND age > 20`.
- **Transactions:** provide atomicity (read marks -> update total -> update result; failure prevents incomplete updates).
- **Consistency:** strong = a read sees the latest committed data; eventual = a read may briefly see an older value, then converges.
- Note: the notes say Datastore "historically" had different consistency by operation type. Modern Firestore in Datastore mode provides strong consistency for most operations [ADDED; answer per your notes unless your teacher says otherwise].

### Architecture diagram

```
              Application
                   |
             Datastore API
          +--------+--------+
          v                 v
     Entity Store        Indexes
          +--------+--------+
                   v
        Distributed storage
      Node A     Node B     Node C
          \         |        /
            Replication
```

### Relational DB vs Datastore (notes slide 109)

| Relational database | Datastore |
|---|---|
| SQL database | NoSQL database |
| Tables / Rows / Columns | Kinds / Entities / Properties |
| Fixed, structured schema | Flexible schema |
| SQL queries | Datastore query mechanisms |
| Joins commonly supported | Avoids traditional joins |
| Vertical scaling traditionally | Horizontal scaling by design |
| Foreign keys | Key / ancestor relationships |
| Schema changes can be significant | Flexible entity structure |

---

## 3.2.5 COMPARISON OF THE FOUR SYSTEMS (from the condensed deck, slide 15)

| Dimension | GFS | BigTable | Dynamo | Datastore |
|---|---|---|---|---|
| Primary abstraction | Files / chunks | Tables / tablets | Key-value | Entities |
| Main priority | Throughput | Scalability | Availability | Managed app data |
| Partitioning | Chunks | Tablets | Hash ring | Managed |
| Replication | Yes | Yes | Yes | Managed |
| Consistency | Strong-ish semantics | Strong consistency model | Eventual | Managed / transactional features |
| Typical workload | Large data files | Structured big data | Always-on services | Cloud applications |

**Choose which?** GFS: very large files, high-throughput batch/streaming. BigTable: massive sparse structured data with row-based access. Dynamo-style: high availability and low latency with eventual consistency acceptable. Datastore: managed NoSQL for application entities without managing a cluster.

**Exam key points (deck slide 17):** GFS master = metadata, chunk servers = data and replication; client gets metadata from master then transfers data directly. BigTable = tablets served by tablet servers; row key + column families + columns + timestamps. Dynamo = decentralized + consistent hashing + replication + eventual consistency; N, R, W with R + W > N. Datastore = managed schema-flexible NoSQL with entities, kinds, properties.

---


# PART 3.3 - PARALLEL DATABASE ARCHITECTURES AND MAPREDUCE

## 3.3.1 PARALLEL DATABASE ARCHITECTURES

**Why parallel databases?**
- Data growth: TB to PB from transactions, sensors, logs, media, cloud services.
- Performance: split a big operation into smaller tasks running simultaneously, to reduce response time and/or increase throughput (scans, joins, sorting, aggregation, indexing, analytics).
- Scalability: add processors, memory or nodes to raise total capacity.
- Key design issue: gain from parallelism must exceed communication, synchronization and coordination overhead.

### The three architectures (draw all three; this is a standard 10-mark diagram question)

```
(a) SHARED MEMORY                 (b) SHARED DISK                    (c) SHARED NOTHING

 P1   P2   P3   P4                 P1    P2    P3    P4               +--------+   +--------+   +--------+
  \    |    |   /                  |     |     |     |                | P1     |   | P2     |   | P3     |
   +---+----+--+                   M1    M2    M3    M4               | M1     |   | M2     |   | M3     |
   |  SHARED   |                   \     |     |     /                | D1     |   | D2     |   | D3     |
   |  MEMORY   |                    +----+-----+----+                +---+----+   +---+----+   +---+----+
   +-----+-----+                    |  INTERCONNECT |                    +------------+------------+
         |                          +-------+-------+                         NETWORK (messages only)
      +--+--+                               |
      |DISKS|                           +---+---+
      +-----+                           | SHARED|
                                        | DISKS |
                                        +-------+
 P = processor, M = private memory, D = local disk
```

| Feature | Shared memory | Shared disk | Shared nothing |
|---|---|---|---|
| What is shared | Memory and storage | Disk/storage only; each node has private memory | Nothing; each node has own CPU, memory, disk |
| Communication | Simple, through memory | Through network to shared disk | Message passing over network |
| Scalability | Limited (memory/bus contention) | Moderate (disk contention, coordination overhead) | Highly scalable |
| Fault handling | Single point of contention | Flexible node-failure handling; data reachable from all nodes | Good fault isolation |
| Main drawback | Bus/memory contention | Storage contention, cache coherence overhead | Data movement can be expensive |
| Typical use | Small multiprocessor servers | Clustered databases | Cloud and distributed model (MPP, MapReduce clusters) |

**Shared nothing in detail:** data is partitioned across nodes (hash or range partitioning); queries run close to the data (less movement); adding nodes adds compute and storage; examples: MPP databases and distributed data-processing platforms.

### Partitioning and parallel query processing
```
Input table --> PARTITION --> Node A scan \
                              Node B scan  >--> partial results --> EXCHANGE/SHUFFLE --> parallel join/aggregate --> FINAL RESULT
                              Node C scan /
```
Partitioning decides how much work each node gets. **Data skew:** poor partitioning gives one node most of the work, becoming a bottleneck while others wait.

Partitioning strategies [ADDED]: round-robin (even spread, no locality), hash (good for equality lookups and joins on key), range (good for range queries but can skew). Parallelism types [ADDED]: inter-query (different queries in parallel), intra-query (one query split into parts), intra-operation (one operator, e.g. a scan or sort, run in parallel on partitions).

---

## 3.3.2 MAPREDUCE MODEL

**Definition:** MapReduce is a distributed programming model for processing large datasets across many machines. The programmer writes only two functions, Map and Reduce; the framework handles task scheduling, data distribution, synchronization, failure recovery and most of the parallel execution. Classic flow: Map -> Shuffle/Sort -> Reduce.

### Flow diagram (draw this)

```
 INPUT DATA          MAP TASKS             SHUFFLE & SORT              REDUCE TASKS        OUTPUT
 (split into  --->   Map 1  ---\                                      
  partitions         Map 2  ----+--> group by key, sort,  --------->   Reduce 1  ---->  part-0
  stored on          Map 3  ---/     send each key to its             Reduce 2  ---->  part-1
  GFS/HDFS)          (parallel)      reducer (partition)              (parallel)
                  emit (key, value)  key -> [v1, v2, ...]             combine values
```

### Map function
Processes one input record / key-value pair and emits intermediate key-value pairs. Naturally parallel: many mappers process different partitions independently. Example: input "cloud computing cloud" -> `(cloud,1), (computing,1), (cloud,1)`.

### Shuffle, sort, reduce
- Shuffle: transfers intermediate records to the reducer responsible for each key (commonly reducer = hash(key) mod R).
- Sort/group: guarantees a reducer receives all values for a key.
- Reduce: combines values to produce the final result.
- Shuffle is communication-intensive and often the performance bottleneck.

### Worked example: Word Count (notes slide 10)
Input lines: (1) `cloud security` (2) `cloud computing` (3) `security analytics`

| Phase | Output |
|---|---|
| Map | L1: (cloud,1) (security,1); L2: (cloud,1) (computing,1); L3: (security,1) (analytics,1) |
| Shuffle/sort (group by key) | analytics -> [1]; cloud -> [1,1]; computing -> [1]; security -> [1,1] |
| Reduce (sum) | (analytics,1) (cloud,2) (computing,1) (security,2) |

Pseudo-code [ADDED]:
```
map(key, line):                      reduce(word, counts):
    for each word w in line:             emit(word, sum(counts))
        emit(w, 1)
```
Same pattern: log analysis, indexing, counting, aggregation, batch analytics.

### How MapReduce achieves parallelism
- Data parallelism: different input partitions processed simultaneously by independent mappers.
- Task parallelism: many map and reduce tasks run concurrently on worker nodes.
- Pipelined stages: finished work can feed later stages while others still run.
- Speedup is not unlimited: network transfer, synchronization, skew, serialization and stragglers add overhead.

**Task-count numerical [ADDED]:** 500 GB of logs with 128 MB input splits -> 500 x 1024 / 128 = 4,000 map tasks (with 64 MB splits: 8,000). Number of reduce tasks R is chosen by the programmer (e.g. R = 20 -> 20 output files).

### Another worked design: failed login attempts per user (review question 8 in notes)
- Input record: `timestamp, userId, result` (SUCCESS/FAILED).
- Map: if result = FAILED emit `(userId, 1)`, else emit nothing.
- Shuffle: group by userId -> `userId -> [1,1,1,...]`.
- Reduce: sum -> `(userId, failedCount)`.
- Optional combiner [ADDED]: sums locally on each mapper before shuffle to cut network traffic.
- Example: records (u1,F),(u2,S),(u1,F),(u3,F),(u1,F) -> Map: (u1,1)x3,(u3,1) -> Reduce: u1=3, u3=1.

### Classroom activity: parallel log analyzer (500 GB nightly) - model answer
1. Partition: split logs by file/block (about 128 MB each, thousands of blocks), stored with replication so mappers run where blocks live.
2. Map: parse each line, emit IP, URL, status, timestamp (e.g. key = URL or IP).
3. Shuffle: group by IP or URL.
4. Reduce: request count, error count (status >= 400), top URLs.
5. Fault tolerance: if 2 workers fail, the scheduler re-runs their unfinished tasks on other workers using replicas of the input blocks; completed tasks elsewhere are not restarted.
6. To cut traffic and skew: use a combiner, process data where it is stored, choose a good partition key, and use enough reducers; if one URL is very hot, split its key.

---

## 3.3.3 FAULT TOLERANCE

In a cluster, machine and task failures are expected, not exceptional. Mechanisms:
- Input data is stored redundantly (replicas), so lost data can be read from another copy.
- Failure detection: framework notices a task/worker has stopped making progress.
- Task re-execution: the scheduler launches the unfinished task again on another worker using available input data. Other completed tasks generally need not restart.
- Stragglers (slow tasks) can be mitigated with speculative execution (a backup copy of the slow task; the first to finish wins), in systems that support it.
- Checkpointing or persisted intermediate state can reduce repeated work (implementation dependent).
- Trade-off: replication and retries consume extra resources.

```
Input block -> Replica A   |  Mapper on Worker 1 --X (fails)  -->  failure detected
                           |  Task re-run on Worker 4 (reads another replica)  -->  continue to Reduce
```

Extra detail [ADDED, from the original MapReduce design]: the master pings workers periodically; if a worker does not answer, its in-progress tasks are reset to idle and rescheduled. Completed map tasks on a failed worker must also be re-run because their output sits on that worker's local disk, whereas completed reduce tasks need not be re-run since output is written to the global file system. Master failure is rare; the job is usually restarted.

---

## 3.3.4 EFFICIENCY

Four factors: **parallelism** (more workers help if enough independent work exists), **data locality** (process data near where it is stored: less network traffic), **communication** (shuffle, replication, coordination cost), **skew** (uneven partitions create stragglers). Amdahl's law: the non-parallelizable fraction limits maximum speedup. A good system balances computation, I/O and communication instead of just adding nodes.

**Metrics:** execution time; speedup S(p) = T(1) / T(p); parallel efficiency E(p) = S(p) / p; throughput; resource utilization; data skew / straggler rate; fault-recovery overhead.

**Numericals [ADDED, formulas from notes]**

N1. A job takes T(1) = 120 min on one node, T(4) = 40 min on 4 nodes, T(8) = 25 min on 8 nodes.
- S(4) = 120/40 = 3.0, E(4) = 3.0/4 = 0.75 = 75%.
- S(8) = 120/25 = 4.8, E(8) = 4.8/8 = 0.60 = 60%.
- Efficiency falls as nodes increase because overhead (communication, skew) grows.

N2. Amdahl's law: S(p) = 1 / ((1 - P) + P/p), P = parallel fraction. Let P = 0.9.
- p = 10: S = 1 / (0.1 + 0.09) = 5.26, E = 52.6%.
- p = 100: S = 1 / (0.1 + 0.009) = 9.17.
- p -> infinity: S = 1 / 0.1 = 10. Maximum speedup is 10 no matter how many nodes.
- Check P = 0.95, p = 20: S = 1 / (0.05 + 0.0475) = 10.26.

---

## 3.3.5 APPLICATIONS, COMPARISON, LIMITATIONS

**Applications:** log and security analytics; search and indexing; recommendation (aggregate user-item interactions); ETL and data warehousing; social/web analytics (clicks, events, trends, graphs); scientific/IoT batch data.

**MapReduce vs parallel/MPP database (notes slide 17)**

| MapReduce | Parallel / MPP database |
|---|---|
| General-purpose batch processing | Declarative SQL-based processing |
| Programmer writes Map/Reduce logic | Query optimizer chooses the execution plan |
| Works naturally with large distributed files | Structured data with database semantics |
| Strong fault-tolerant batch execution | Parallel scans, joins, sorting, aggregation |
| Explicit shuffle stages | Uses indexes, statistics, pipelining |
| Large-scale transformations and analytics | Interactive analytics and warehousing |

**Limitations:** shuffle overhead can dominate; small files create too many tasks; data skew; repeated batch jobs have high I/O and startup cost; iterative algorithms are slow if state is written/read each time; tuning partitions, reducers, resources matters; modern engines (DAG-based, in-memory such as Spark) often complement or replace classic MapReduce.

**Typical stack:** Applications -> SQL/APIs -> Processing engine -> Distributed storage -> Cluster resources (Hadoop MapReduce, HDFS, Spark, distributed SQL/MPP).

**Review questions in your notes (treat these as likely questions):** (1) compare shared-memory/disk/nothing, (2) explain Map, Shuffle/Sort, Reduce with example, (3) how MapReduce recovers from worker failure, (4) what is data locality and why it helps, (5) define speedup and parallel efficiency, (6) how data skew affects processing, (7) two applications of MapReduce and two cases where DB/MPP is preferable, (8) design MapReduce for counting failed logins per user. Answer-guides for these are in sections 3.3.1 to 3.3.5 above. For (7): MapReduce is good for log analysis and building search indexes; an MPP database is preferable for interactive SQL reporting on structured warehouse data and for queries that benefit from indexes and optimizers.

**How to write it in the exam:** MapReduce 5M = definition, 3-box flow diagram, word-count table, 2 lines on parallelism and fault tolerance. 10M = add shuffle bottleneck, fault tolerance, efficiency, applications, MapReduce vs parallel DB.

---

# 4. PREVIOUS YEAR QUESTIONS - SOLUTIONS (Module 3 only)

Grouped by topic. Marks guide the length. Content flagged `[ADDED]` is standard knowledge beyond your notes.

---

## 4.1 Topic: MapReduce (3.3)

### Q [PYQ Jan-Apr 2025, Q2A(ii), 5 marks]: Explain Map Reduce model with example.

**Answer**

**Introduction.** MapReduce is a distributed programming model for processing very large datasets in parallel across many machines. The programmer writes two functions, Map and Reduce. The framework takes care of splitting data, scheduling tasks, moving intermediate data, synchronization and recovery from failures.

**Execution flow (diagram)**
```
 INPUT       SPLITS        MAP TASKS         SHUFFLE & SORT           REDUCE TASKS       OUTPUT
 data   -->  split 1  -->  Map 1  --\
 (large      split 2  -->  Map 2  ---+--> group all values  -->  Reduce 1 --> result part 1
 files)      split 3  -->  Map 3  --/     of the same key       Reduce 2 --> result part 2
                      emit (key,value)    to one reducer
```

**Steps**
1. **Map:** each mapper reads one split and emits intermediate (key, value) pairs.
2. **Shuffle and sort:** intermediate pairs are partitioned, transferred over the network and grouped so that each reducer receives all values of a key as `key -> [v1, v2, ...]`.
3. **Reduce:** each reducer combines the list of values for a key into a final result and writes the output.

**Example: Word Count**
Input: `cloud security`, `cloud computing`, `security analytics`.

| Stage | Result |
|---|---|
| Map | (cloud,1) (security,1) (cloud,1) (computing,1) (security,1) (analytics,1) |
| Shuffle/sort | cloud -> [1,1]; security -> [1,1]; computing -> [1]; analytics -> [1] |
| Reduce | cloud = 2, security = 2, computing = 1, analytics = 1 |

**Key points**
- Parallelism: many map tasks run on different partitions at once; many reduce tasks run concurrently.
- Fault tolerance: input is replicated; a failed task is re-run on another worker.
- Data locality: map tasks are scheduled near the data to reduce network traffic.
- Applications: log analysis, indexing, counting, ETL, recommendation.

---

## 4.2 Topic: Relational vs NoSQL cloud databases (3.1 limitations / 3.2)

### Q [PYQ Nov-Dec 2021, Q1(B)(v), part of 10 marks (any 5 of 7), so about 2 marks]: What is the difference between Amazon SimpleDB and Amazon RDS?

Note: this question is not covered in your decks directly; the answer uses the relational vs NoSQL contrast from Module 3 plus standard AWS facts `[ADDED]`.

| Point | Amazon SimpleDB | Amazon RDS |
|---|---|---|
| Type | Non-relational (NoSQL) key-attribute store | Managed relational database service |
| Data model | Domains (like tables), items (like rows), attributes (name-value pairs) | Tables, rows, columns with primary/foreign keys |
| Schema | Schema-less, flexible; items in a domain can have different attributes | Fixed schema |
| Query | Simple SELECT-style queries, no joins | Full SQL with joins |
| Transactions | No full ACID transactions; reads eventually consistent by default (consistent read optional) | Full ACID |
| Engines | Single proprietary service | MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Aurora |
| Scale and size | Small to medium datasets, limited domain size, automatic indexing | Larger structured databases; scales up by instance size and read replicas |
| Management | Fully managed, no admin | Managed: backups, patching, Multi-AZ failover |
| Best for | Lightweight flexible metadata, simple lookups | Traditional apps (banking, ERP, e-commerce) needing relational integrity |

One-line summary for a 2-mark answer: SimpleDB is a schema-free NoSQL attribute store with simple queries and eventual consistency, while RDS is a managed relational database offering full SQL, joins and ACID transactions.

---

## 4.3 Topic: Cloud storage services (3.2 adjacent)

### Q [PYQ Jan-Apr 2025, Q5(iii), 5 marks]: Amazon Simple Storage Service (S3) (write a note)

Note: S3 is not in your Module 3 decks; the answer is standard AWS knowledge `[ADDED]`. It is adjacent to 3.2 (cloud storage), so keep it short and tie it back to replication and durability.

**Definition.** Amazon S3 is a highly scalable, durable, pay-as-you-go object storage service of AWS, accessed over the internet through web APIs (REST/HTTP). It stores any amount of data such as backups, images, videos and logs.

**Concepts**
- **Bucket:** top-level container with a globally unique name, created in a chosen region.
- **Object:** the stored item = data + metadata, identified by a unique **key** inside the bucket (flat namespace; "folders" are just key prefixes).
- Objects can be very large (up to 5 TB each); the total capacity is practically unlimited.

```
 Client / Application  --HTTP (PUT/GET/DELETE)-->  S3 service
                                                     |
                                      Bucket "college-data"
                                        |-- key: notes/mod3.pdf  (object: data + metadata)
                                        |-- key: video/lec1.mp4
                                      replicated automatically across multiple data centers (AZs)
```

**Features**
1. Durability: designed for 99.999999999% (11 nines) durability by storing copies in multiple facilities.
2. Availability: high (Standard class designed for 99.99%).
3. Storage classes: Standard, Intelligent-Tiering, Standard-IA, One Zone-IA, Glacier tiers for archives.
4. Versioning and lifecycle policies (move/delete objects automatically).
5. Security: IAM, bucket policies, ACLs, encryption at rest and in transit.
6. Consistency: strong read-after-write consistency for objects.
7. Pay only for storage used and requests/data transfer.

**Uses:** backup and archive, static website hosting, media storage, data lakes and big-data analytics input, software distribution.

**Link to Module 3:** like GFS it replicates data for fault tolerance and scales horizontally, but S3 is an object store accessed by key over HTTP, whereas GFS is a file system built for Google's internal batch workloads.

---

## 4.4 PYQ coverage check

| Topic | PYQs found | Fresh-question risk |
|---|---|---|
| Relational DB storage techniques | None | High |
| Default mechanism since 80s / ACID | None | High |
| GFS | None | High |
| BigTable | None | High |
| Dynamo | None | High |
| Datastore | None | High |
| Parallel DB architectures | None | High |
| MapReduce | 1 (2025, 5M) | Medium: may repeat, may become 10M with fault tolerance |
| Amazon SimpleDB vs RDS | 1 (2021) | Low-medium |
| S3 | 1 (2025, adjacent) | Low |

---

# 5. PRACTICE QUESTIONS I EXPECT [LIKELY - self-made, not official PYQs]

Each has a short answer guide pointing to the section where the full content is.

| No | Question | Marks | Answer guide |
|---|---|---|---|
| 1 | Explain the architecture of Google File System with a neat diagram. Describe read and write operations. | 10 | 3.2.1: diagram, 3 components, 64 MB chunk, read 5 steps, write 6 steps, replication, heartbeat |
| 2 | A 200 MB file is stored in GFS (chunk 64 MB, 3 replicas). Find the number of chunks and copies. What happens if a chunk server fails? | 5 | 4 chunks (64,64,64,8), 12 copies; master detects by heartbeat, redirects, re-replicates |
| 3 | Compare traditional file system and GFS. | 5 | 3.2.1 table |
| 4 | Explain BigTable data model and architecture. | 10 | 3.2.2: row key, family, column, timestamp, master, tablet servers, Chubby, GFS, SSTable |
| 5 | Describe the BigTable write path. | 5 | commit log, MemTable, flush to SSTable, compaction |
| 6 | Compare BigTable with RDBMS. / BigTable with GFS. | 5 | 3.2.2 tables |
| 7 | Explain Dynamo architecture: consistent hashing, replication, quorum. | 10 | 3.2.3 |
| 8 | N = 3, R = 2, W = 2. Does the system give overlap? What if R = 1, W = 1? | 5 | 4 > 3 yes; 2 > 3 no, stale reads possible |
| 9 | What is consistent hashing? Why virtual nodes? | 5 | 3.2.3 with keys-moved numerical |
| 10 | Explain hinted handoff and vector clocks. | 5 | 3.2.3 |
| 11 | Explain Datastore: entity, kind, properties, keys. Compare with RDBMS. | 10 | 3.2.4 |
| 12 | Compare GFS, BigTable, Dynamo and Datastore. | 10 | 3.2.5 table |
| 13 | Explain data storage techniques in relational databases. | 10 | 3.1.1 |
| 14 | Compare row-oriented and column-oriented storage. | 5 | 3.1.1 table + N1 |
| 15 | Explain ACID properties with example. | 5 | 3.1.2 |
| 16 | Why did RDBMS become the default since the 1980s, and what are its limitations in cloud? | 10 | 3.1.2 |
| 17 | Compare shared memory, shared disk, shared nothing architectures. | 10 | 3.3.1 diagrams + table |
| 18 | Explain MapReduce with fault tolerance and efficiency. | 10 | 3.3.2 to 3.3.4 |
| 19 | Design a MapReduce job to count failed logins per user. | 5 | 3.3.2 |
| 20 | Compute speedup and efficiency (T1=120, T4=40) and explain Amdahl's law. | 5 | 3.3.4 N1, N2 |

---

# 6. LAST-MINUTE REVISION SHEET

- RDBMS default since 1980s: tables + SQL + ACID; Codd 1970. Limits in cloud: vertical scaling, hard to distribute, rigid schema.
- Storage techniques: heap (fast insert), sequential (sorted, range), indexed (primary/secondary/clustered/non-clustered), hash (equality, O(1)), B+ tree (O(log n), ranges), row (OLTP) vs column (OLAP), partitioning, compression, normalization, pages.
- ACID: Atomicity (all or nothing), Consistency (valid state), Isolation (no interference), Durability (survives crash).
- GFS: 1 master (metadata) + many chunk servers (64 MB chunks, 3 replicas); client gets locations from master, then talks to chunk servers directly; heartbeat; re-replication.
- BigTable: row key + column family:column + timestamp; Master + Tablet Servers + Chubby + GFS + SSTable; write = commit log -> MemTable -> SSTable -> compaction; sparse, versioned.
- Dynamo: key-value, ring, consistent hashing + vnodes, N replicas, R + W > N, eventual consistency, hinted handoff, vector clocks.
- Datastore: Kind (table), Entity (row), Property (column), Key; indexes; transactions; Firestore in Datastore mode.
- Shared memory (contention, limited scale) / shared disk (storage contention) / shared nothing (scalable, cloud model).
- MapReduce: Map -> Shuffle/Sort -> Reduce; fault tolerance = replicated input + task re-execution + speculative execution; efficiency = locality, skew, shuffle cost; S = T1/Tp, E = S/p, Amdahl.
