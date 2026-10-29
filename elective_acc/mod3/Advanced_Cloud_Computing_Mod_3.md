# Advanced Cloud Computing — Module 3: Managing Data (10 hrs, CO3)

> **Scope (as given):** 3.1 Relational databases: Data Storage Techniques, Default data storage and retrieval mechanism since the 80s · 3.2 Cloud File Systems: GFS Architecture, BigTable Storage, Dynamo Architecture, Datastore.
> (3.3 Parallel DB Architectures / MapReduce is in the official syllabus PDF but NOT in your scope → not covered. The 2025 "MapReduce with example" PYQ belongs there.)

## 🚨 UTMOST IMPORTANT — CONTEXT CARRY-OVER (keep in every chat summary)

1. **Task:** one deliverable file `Advanced_Cloud_Computing_Mod_3.md` with 4 parts: (1) Topic map tree, (2) topic-wise question-type table with PYQ markers, (3) topic-by-topic exam-ready notes + numericals, (4) solved PYQs of *this module only*. Anything not from notes/PYQ is marked 🆕.
2. **Sources analysed (all of them):**
   - Notes: `Module 3.1.pptx` (74 slides, relational DB), `Module 3.2.pptx` (113 slides, GFS/BigTable/Dynamo/Datastore), `Cloud_File_Systems_GFS_BigTable_Dynamo_Datastore.pptx` (18 slides, summary/comparison deck). Images in the slides were viewed directly (tables, diagrams).
   - PYQs (one dir up): `cloud computing.PDF` (ESE **May 2025**, Minors, 75 marks), screenshots of ESE **Dec 2022** (100 m), **Nov–Dec 2021** (50 m), **May–Jun 2021** (50 m, Distributed & Cloud Computing), plus `LY-SVU2023-Syllabus.pdf` (161 pp; Module 3 is on p.22).
3. **KEY FINDING:** *No past paper has a direct question on Module 3 topics* (GFS, BigTable, Dynamo, Datastore, RDBMS storage techniques). This module is new in the SVU-2023 syllabus (old papers are on the older Cloud Computing syllabus: virtualization, Aneka, AWS, AppEngine, etc.). Only **adjacent** items exist: *Amazon SimpleDB vs RDS* (Nov-Dec 2021), *SAN vs NAS* (Dec 2022; match-the-pair May-Jun 2021), *Amazon S3* (May 2025). These are solved in Part 4 and flagged ⭐~ ("adjacent, not strictly Mod 3"). Everything else in Part 4 is 🆕 predicted.
4. **Marker legend:** 📘 = in the notes · ⭐ = appeared in an official PYQ (none directly) · ⭐~ = adjacent PYQ · 🆕 = added by me (not in notes/PYQ — extra depth or predicted question).
5. **Exam format hints from PYQs:** ESE 50 marks (1h45) → Q1 = MCQ/match/short (10m) + "any 5 of 7" short notes (2 m each); Q2–Q4 = 10 marks each with OR. Older 100-mark papers: "Solve any four of six" 5-mark short notes, and 10-mark long answers. Instruction always: **draw neat diagrams, assume suitable data**. So: diagram + labelled points + a comparison table wins marks.

---

# PART 1 — TOPIC MAP

```
MODULE 3: MANAGING DATA
│
├── 3.1 RELATIONAL DATABASES
│   ├── A. Foundations 📘
│   │   ├── Data → Database (characteristics, why needed)
│   │   ├── DBMS vs RDBMS (comparison table)
│   │   └── Components: Table/Relation, Row/Tuple, Column/Attribute, Primary Key, Foreign Key
│   │
│   ├── B. DATA STORAGE TECHNIQUES (12 techniques) 📘
│   │   ├── 1. Table-based storage
│   │   ├── 2. Row-oriented storage ........ (OLTP)
│   │   ├── 3. Column-oriented storage ..... (OLAP)
│   │   ├── 4. Heap file organization
│   │   ├── 5. Sequential file organization
│   │   ├── 6. Indexed storage
│   │   │   ├── Primary index
│   │   │   ├── Secondary index
│   │   │   ├── Clustered index
│   │   │   └── Non-clustered index
│   │   ├── 7. Hash-based storage
│   │   ├── 8. B-Tree / B+ Tree storage
│   │   ├── 9. Partitioning
│   │   │   ├── Horizontal / Vertical
│   │   │   └── Range / Hash / List
│   │   ├── 10. Compression (Row, Column, Dictionary, RLE)
│   │   ├── 11. Normalization
│   │   ├── 12. Data pages & blocks
│   │   ├── Comparison table + Applications (bank, e-commerce, DW, hospital, library, reservation)
│   │   └── Scenario: choose technique (fees→row, reports→column, search→index, bulk import→heap)
│   │
│   └── C. DEFAULT STORAGE & RETRIEVAL MECHANISM SINCE THE 1980s 📘
│       ├── Evolution: file-based → hierarchical → Codd's relational model (1970) → RDBMS default (80s)
│       ├── Why it became default (tables, SQL, normalization, security, transactions)
│       ├── Client–Server DB architecture (Client → DB Server → Storage: HDD/SSD/RAID)
│       ├── SQL-based retrieval (SELECT/INSERT/UPDATE/DELETE)
│       ├── ACID properties (Atomicity, Consistency, Isolation, Durability) + banking case study
│       ├── Transaction management (BEGIN/COMMIT/ROLLBACK, transaction states)
│       ├── Concurrency control (lost update, dirty read; locks, timestamp ordering, MVCC)
│       ├── Advantages
│       └── Limitations in cloud → motivation for GFS / BigTable / Dynamo / NoSQL
│
└── 3.2 CLOUD FILE SYSTEMS
    ├── D. Why cloud file systems? (scalability, fault tolerance, throughput; 4 systems at a glance) 📘
    │
    ├── E. GOOGLE FILE SYSTEM (GFS) 📘
    │   ├── Definition, why Google built it, features
    │   ├── Architecture: GFS Client · Master Server (metadata) · Chunk Servers
    │   ├── File storage: 64 MB chunks, chunk handle
    │   ├── Read operation / Write operation (primary & secondary replicas)
    │   ├── Replication (3 copies) & fault tolerance (heartbeat, re-replication)
    │   ├── Advantages · Limitations · Applications
    │   └── Traditional FS vs GFS
    │
    ├── F. BIGTABLE STORAGE 📘
    │   ├── NoSQL intro (Traditional DB vs NoSQL)
    │   ├── Definition, features, applications
    │   ├── Data model: Row key · Column family · Column · Timestamp
    │   ├── Architecture: Client · BigTable Master · Tablet Servers · GFS · Chubby
    │   ├── Tablets & SSTables
    │   ├── Read / Write path (commit log → MemTable → SSTable → compaction)
    │   ├── Advantages · Limitations · Applications
    │   └── BigTable vs RDBMS · BigTable vs GFS
    │
    ├── G. DYNAMO ARCHITECTURE 📘
    │   ├── Intro (Amazon key-value store; availability over consistency), why needed
    │   ├── Characteristics: distributed, decentralized, highly available, fault tolerant, scalable, eventually consistent
    │   ├── Data model: key → value
    │   ├── Mechanisms: Partitioning · Replication · Consistency · Versioning · Failure handling · Membership
    │   │   ├── Consistent hashing → Virtual nodes
    │   │   ├── Replication factor N
    │   │   ├── Eventual consistency
    │   │   ├── Quorum: N, R, W (R + W > N)
    │   │   ├── Failure detection → Hinted handoff
    │   │   └── Versioning: vector clocks → conflict resolution
    │   └── Shopping-cart example
    │
    ├── H. DATASTORE 📘
    │   ├── Cloud datastore concept: why, characteristics (scalability, availability, durability, fault tolerance, persistence), types
    │   ├── Google Cloud Datastore (= Firestore in Datastore mode)
    │   ├── Data model: Kind → Entity → Properties; Key; Ancestor (hierarchy)
    │   ├── Indexing · Queries · Transactions
    │   ├── Strong vs eventual consistency
    │   ├── Architecture (API → Entity store + Indexes → distributed storage + replication)
    │   └── RDBMS vs Datastore · Dynamo vs Datastore
    │
    └── I. CROSS-CUTTING: Comparison of the four systems · Choosing the right storage model 📘
```

---

# PART 2 — TOPIC-WISE QUESTION TYPES

**Legend:** ⭐ = appeared in official PYQ · ⭐~ = appeared in PYQ in adjacent form · 📘 = notes explicitly contain this type (table/activity/scenario/"exam key point") · 🆕 = my prediction · — = unlikely.
**Types:** SN = short note (5 m) · LT = long theory (10 m) · DG = diagram/draw-and-explain · CMP = compare/differentiate · NUM = numerical/"assume data" · SCN = scenario/case/example · OBJ = MCQ/match/fill/define (1–2 m). *No derivations exist in this module.*

| Topic | SN | LT | DG | CMP | NUM | SCN | OBJ |
|---|---|---|---|---|---|---|---|
| **3.1** DBMS vs RDBMS, components, keys | 📘 | 🆕 | 📘 (PK→FK→PK) | 📘 (DBMS vs RDBMS table) | — | — | 🆕 |
| Row-oriented vs column-oriented storage | 📘 | 🆕 | 📘 | 🆕 (OLTP vs OLAP) | 🆕 (I/O cost) | 📘 (student info system) | 🆕 |
| Heap & sequential file organization | 📘 | — | 📘 | 🆕 | 🆕 (scan cost) | 📘 | 🆕 |
| Indexed storage (primary/secondary/clustered/non-clustered) | 📘 | 🆕 | 📘 | 🆕 (clustered vs non-clustered) | — | 📘 | 🆕 |
| Hash-based & B / B+ tree | 📘 | — | 📘 (B+ tree) | 🆕 (hash vs B+) | 🆕 (height / bucket) | 📘 | 🆕 |
| Partitioning, compression | 📘 | — | 📘 | — | — | 🆕 | 🆕 |
| Normalization | 📘 | — | 📘 (before/after) | — | — | 📘 | 🆕 |
| Pages & blocks; comparison of 12 techniques | — | 🆕 | 📘 | 📘 (comparison table) | — | 📘 (applications list) | — |
| History/evolution & why RDBMS default since 80s | 📘 | 🆕 | — | 🆕 (file vs hierarchical vs relational) | — | — | 🆕 |
| Client–server DB architecture, SQL retrieval | 📘 | 🆕 | 📘 | — | — | 📘 | — |
| **ACID properties** | 📘 | 🆕 | — | — | — | 📘 (online banking case study) | 🆕 |
| Transaction states, concurrency control | 📘 | 🆕 | 📘 (state diagram) | — | 🆕 (lost update) | 📘 (₹10,000 example) | 🆕 |
| Limitations of RDBMS in cloud | 📘 | 🆕 | — | 🆕 (RDBMS vs NoSQL) | — | — | 🆕 |
| RDBMS vs cloud NoSQL DB (SimpleDB vs RDS) | — | — | — | ⭐~ (Nov-Dec 2021) | — | — | — |
| **3.2** Why cloud file systems | 📘 | — | — | — | — | — | 🆕 |
| **GFS architecture** (client/master/chunkserver) | 📘 | 🆕 (most likely 10 m) | 📘 | — | — | — | 🆕 |
| GFS read / write flow | 📘 | 🆕 | 📘 | — | — | — | — |
| GFS chunking / replication numericals | — | — | 📘 | — | 📘 (200 MB video activity) | 📘 | — |
| GFS fault tolerance, limitations, apps | 📘 | 🆕 | — | — | — | 📘 | — |
| Traditional FS vs GFS; GFS vs BigTable | — | — | — | 📘 (2 tables) | — | — | — |
| NoSQL intro; traditional DB vs NoSQL | 📘 | — | — | 📘 | — | — | 🆕 |
| **BigTable** data model (row key, CF, column, timestamp) | 📘 | 🆕 | 📘 | — | 🆕 (cell address) | 📘 | 🆕 |
| BigTable architecture (master, tablet servers, Chubby, GFS) | 📘 | 🆕 | 📘 | — | — | — | 🆕 |
| Tablets & SSTables; read/write path | 📘 | 🆕 | 📘 | — | — | — | 🆕 |
| BigTable vs RDBMS | — | — | — | 📘 | — | — | — |
| **Dynamo** intro, characteristics, why needed | 📘 | 🆕 | 📘 | — | — | 📘 (shopping cart) | 🆕 |
| Consistent hashing, virtual nodes | 📘 | 🆕 | 📘 (ring) | 🆕 (vs hash mod N) | 🆕 (key movement) | — | 🆕 |
| Replication, eventual consistency | 📘 | — | 📘 | — | — | 📘 (₹50→₹60) | 🆕 |
| **Quorum N, R, W** | 📘 | — | — | — | 📘 (N=3,R=2,W=2) | — | 🆕 |
| Hinted handoff, failure detection | 📘 | — | 📘 | — | — | 📘 | 🆕 |
| Vector clocks / versioning | 📘 | — | — | — | 🆕 | 📘 | 🆕 |
| **Datastore** concept & characteristics | 📘 | — | 📘 | — | — | 📘 | 🆕 |
| Datastore data model (kind, entity, property, key, ancestor) | 📘 | 🆕 | 📘 | 📘 (RDBMS vs Datastore) | — | 📘 | 🆕 |
| Indexing, queries, transactions, consistency | 📘 | — | 📘 | — | — | 📘 | 🆕 |
| Dynamo vs Datastore | — | — | — | 📘 | — | — | — |
| Comparison of GFS/BigTable/Dynamo/Datastore; "choose the right one" | — | 🆕 | — | 📘 (4-way table) | — | 📘 | 🆕 |
| Adjacent: SAN vs NAS (storage) | — | — | — | ⭐~ (Dec 2022) | — | — | ⭐~ (match, May-Jun 2021) |
| Adjacent: Amazon S3 | ⭐~ (May 2025, 5 m) | — | — | — | — | — | — |

**Reading the table:** the *highest-probability* items for a 10-mark question: **GFS architecture + read/write**, **BigTable data model + architecture**, **Dynamo (consistent hashing + quorum + hinted handoff)**, **Datastore model**, **ACID/RDBMS limitations**. For 5-mark short notes: row vs column storage, indexing types, B+ tree, hinted handoff, vector clock, SSTable/MemTable, Chubby, Kind/Entity/Property. Best "comparison" bets: RDBMS vs NoSQL, GFS vs BigTable, Dynamo vs Datastore, RDBMS vs Datastore.

---

# PART 3 — TOPIC-BY-TOPIC EXPLANATION

> **How to read each topic:** *Idea in plain words* → *What to write in the exam (format)* → diagram you can redraw → numericals (if any). 🆕 boxes are extras beyond the slides; add them only if you have marks/time left.

---

## 3.1 RELATIONAL DATABASES

### A. Foundations 📘

**Plain words.** *Data* = raw facts (marks, bank transactions). A *database* = organised, related data stored electronically so it can be searched, updated and managed. Without a database: duplication, slow search, inconsistency. With one: fast search, security, concurrent access, backup/recovery.
**DBMS** = software that creates, stores, retrieves, updates, deletes data and manages users/permissions/security/integrity. A DBMS need *not* use tables (MongoDB, Redis, Neo4j are non-relational DBMSs).
**RDBMS** = DBMS built on the **relational model**: data in **tables (relations)**; tables linked by **keys**.

| Feature | DBMS | RDBMS |
|---|---|---|
| Full form | Database Management System | Relational DBMS |
| Data organisation | Can use different models | Primarily tables |
| Tables | Not mandatory | Fundamental |
| Relationships between tables | Not necessarily supported | Core feature |
| Primary / foreign key | May or may not apply | Commonly used / supported |
| SQL | May or may not use | Typically uses SQL |
| Normalization | Not a requirement | Commonly used |
| Referential integrity | Not necessarily | Supported |
| Transactions | Depends on DBMS | Typically strong support (ACID) |
| Examples | MongoDB, Redis, Neo4j | MySQL, PostgreSQL, Oracle, SQL Server |

**Components of a relational DB:** Table (relation = one entity, e.g. Student) · Row/Tuple (one record: `101 | Rahul | Computer | 20`) · Column/Attribute (one property) · **Primary key** (uniquely identifies a row, e.g. StudentID) · **Foreign key** (column that refers to another table's primary key; creates the relationship).

```
STUDENT                      ENROLLMENT                   COURSE
Student_ID (PK) ───────────► Student_ID (FK)
                             Course_ID  (FK) ───────────► Course_ID (PK)
```
**Why popular:** structured format, easy SQL querying, consistency, ACID transactions, strong security, standardized model.

**Exam format:** 5-mark → definition + table diagram + 5–6 bullet features + DBMS-vs-RDBMS 4–5 row table.

---

### B. Data Storage Techniques 📘

**Big picture (say this first in the answer):** A relational database decides *how rows are physically laid out on disk* and *how to find them fast*. Techniques fall in three groups:
- **Layout:** table-based, row-oriented, column-oriented, pages/blocks
- **File organisation:** heap, sequential
- **Access structures:** index (primary/secondary/clustered/non-clustered), hash, B/B+ tree
- **Size/management:** partitioning, compression, normalization

Running example table used by the notes:

| StudentID | Name | Department | Age |
|---|---|---|---|
| 101 | Alice | Computer | 20 |
| 102 | Bob | Electronics | 21 |
| 103 | Charlie | Mechanical | 22 |

#### 1. Table-based storage
Primary technique: each table = one entity; row = record; column = attribute; unique table name.
*Adv:* simple organisation, easy retrieval/maintenance, SQL works efficiently.

#### 2. Row-oriented storage (OLTP)
All values of one record stored together (contiguously).
```
Row 1 → (101, Alice, Computer, 20)
Row 2 → (102, Bob, Electronics, 21)
Row 3 → (103, Charlie, Mechanical, 22)
```
*Adv:* retrieve a whole record in one read, fast INSERT/UPDATE/DELETE, ideal for banking, e-commerce, ERP. *Disadv:* analytic queries touching few columns still read whole rows (wasted I/O).

#### 3. Column-oriented storage (OLAP)
Values of the same column stored together.
```
StudentID  → 101,102,103
Name       → Alice,Bob,Charlie
Department → Computer,Electronics,Mechanical
Age        → 20,21,22
```
*Adv:* fast aggregates (SUM, AVG, COUNT), excellent compression (similar values together), good for data warehouses. *Disadv:* slow insert/update, bad for frequent transactions.

**Row vs column — exam table 🆕 (built from the notes' points):**
| | Row-oriented | Column-oriented |
|---|---|---|
| Stored together | Whole record | Whole column |
| Best for | OLTP (transactions) | OLAP (analytics/reports) |
| Insert/update | Fast | Slow |
| Aggregate over one column | Reads unnecessary data | Reads only that column |
| Compression | Moderate | Excellent |
| Example use | Banking, ERP, hospital | Data warehouse |

#### 4. Heap file organization
Records stored in no particular order, wherever free space exists (new records at the end). `105, 102, 110, 101, 108, 103`.
*Adv:* very simple, fast insertion, good for frequent inserts, no ordering upkeep. *Disadv:* slow searching, full table scan needed.

#### 5. Sequential file organization
Records stored **sorted by primary key** (`101,102,103,104,105`).
*Adv:* fast sequential access, efficient **range queries**. *Disadv:* slow insertion/deletion (must keep order), reorganisation may be needed.

#### 6. Indexed storage
An **index** = separate structure storing the *location* of records (like a textbook index).
```
Index (StudentID → Address)       Search StudentID=102:
101 → 1000                        Index → Address 1050 → Actual record
102 → 1050
103 → 1100
```
Four types:
- **Primary index** – on the primary key; many DBMSs create it automatically.
- **Secondary index** – on a non-primary-key attribute. `CREATE INDEX idx_department ON Student(Department);` then `SELECT * FROM Student WHERE Department='CSE';` can use it.
- **Clustered index** – determines/closely matches the *physical order* of table rows; leaf level holds the actual data (e.g. SQL Server). Only **one** per table. 
```
        Clustered Index (on Student_ID)
        ┌──────────┼──────────┐
     101-102     103-104     105
        │           │          │
   Data Page 1  Data Page 2  Data Page 3      ← leaf = actual rows
```
- **Non-clustered index** – kept *separately* from table data: key → pointer → table record. A table can have **many**.
```
NON-CLUSTERED INDEX (on Name)
Amit  → location of Amit's row
Neha  → location of Neha's row
Priya → location of Priya's row
Rahul → location of Rahul's row      (table remains separate)
```
*Adv of indexing:* very fast searching, efficient sorting, faster joins. *Disadv:* extra storage, slightly slower insert/update.

**Clustered vs non-clustered 🆕 (for a CMP question):** clustered = data *is* the index leaf, one per table, physical order; non-clustered = separate structure with pointers, many per table, extra lookup hop.

#### 7. Hash-based storage
`Hash(Key) → Bucket`. e.g. StudentID 101→Bucket 5, 102→Bucket 2, 103→Bucket 7.
*Adv:* very fast **equality** search, average O(1). *Disadv:* poor for range queries; collisions must be handled.

#### 8. B-Tree and B+ Tree
Balanced tree; most RDBMS use **B+ trees** for indexing. Search, insert, delete all **O(log n)**; supports range queries.
```
          50
        /    \
      20      80
     /  \    /  \
   10   30  60   90
```
🆕 *Why B+ over B:* in a B+ tree all data pointers sit in leaves and leaves are linked → range scans are a simple walk along the leaf chain.

#### 9. Partitioning
Large table split into smaller partitions (e.g. Sales table → 2023 Sales, 2024 Sales, 2025 Sales).
Types: **Horizontal** (split rows), **Vertical** (split columns), **Range** (by value range e.g. year), **Hash** (by hash of key), **List** (by listed values e.g. region).
*Adv:* faster queries, easier maintenance, better scalability.

#### 10. Compression
Types: Row compression, Column compression, **Dictionary** compression (replace repeated values by short codes), **Run-Length Encoding** (store value+count). 🆕 e.g. RLE: `CSE,CSE,CSE,CSE,IT,IT` → `(CSE,4)(IT,2)`.
*Adv:* saves disk space, faster backups, better cache performance.

#### 11. Normalization
Split data into related tables to remove redundancy.
Before: `(101, Alice, DBMS, Dr.Rao)`, `(101, Alice, OS, Dr.Shah)` — name repeats.
After: Student(101, Alice) · Course(C1 DBMS, C2 OS) · Enrollment(101,C1), (101,C2).
*Adv:* less redundancy, better consistency, easier maintenance.

#### 12. Data pages and blocks
Disk stores fixed-size **pages/blocks**, each holding several records (Disk → Page1{Rec1,Rec2} → Page2{Rec3,Rec4} → Page3). The unit of I/O is the page, not the record. *Adv:* efficient disk I/O, better caching, faster access.

#### Comparison of storage techniques (from notes) 📘
| Technique | Best for | Search | Insert | Storage efficiency |
|---|---|---|---|---|
| Heap | Frequent inserts | Slow | Very fast | Good |
| Sequential | Ordered data | Medium | Slow | Good |
| Indexed | Fast retrieval | Very fast | Medium | Medium |
| Hash | Exact-match search | Very fast | Fast | Medium |
| B+ tree | General purpose | Very fast | Fast | Good |
| Row storage | OLTP | Fast | Fast | Good |
| Column storage | OLAP / DW | Very fast (analytics) | Slow | Excellent |
| Partitioning | Very large tables | Fast | Fast | Excellent |

**Applications 📘:** Banking → row storage + B+ tree indexes · E-commerce → indexed + partitioned · Data warehouse → column storage + compression · Hospital mgmt → row-oriented + indexes · Library mgmt → B+ tree indexing + normalization · Online reservation → indexed + hash-based.

#### Scenario question 📘 (Student Information System) — model answer
| Task | Technique | Reason |
|---|---|---|
| Recording fee payments | **Row-oriented** | Frequent whole-record INSERTs (OLTP) |
| Department-wise performance reports | **Column-oriented** | Aggregates over few columns (OLAP) |
| Search student by roll number | **Indexed** (B+ tree on roll no.) | Pinpoint lookup without full scan |
| Bulk admission import | **Heap file** | Append anywhere, fastest insert, no ordering cost |

#### Numericals for 3.1 storage techniques 🆕 (not in notes — likely "assume suitable data" type)
**N1. Row vs column I/O.** Table: 1,000,000 rows, 4 columns, each 4 bytes (16 B/row). Query `SELECT AVG(Age)`.
- Row store reads whole table: 1,000,000 × 16 B = **16 MB**.
- Column store reads only Age: 1,000,000 × 4 B = **4 MB** → **4× less I/O** (before compression; with RLE/dictionary even less).

**N2. Search cost.** n = 1,000,000 records. Heap: full scan → average n/2 = 500,000 record checks (worst 1,000,000). Sorted + binary search: ⌈log₂ 10⁶⌉ ≈ **20**. B+ tree with fan-out 100: height ≈ log₁₀₀(10⁶) = **3** page reads. Hash index: ≈ **1** bucket access (equality only).

**N3. Records per block.** Block = 4096 B, record = 128 B → 4096/128 = **32 records/block**; 1,000,000 records → 1,000,000/32 = **31,250 blocks**. Heap full scan = 31,250 block reads.

---

### C. Default Data Storage and Retrieval Mechanism Since the 1980s 📘

**Exam-style one-liner:** *"From the 1980s the relational database (RDBMS) accessed through SQL became the default way enterprises stored and retrieved structured data, because it offered simple tables, reduced redundancy through normalization, a standard language (SQL), strong security and reliable ACID transactions."*

#### 1. Evolution of database systems
1. **File-based systems (before 1980):** text/CSV/binary files e.g. `Student.txt: 101 Rahul Computer`. Problems: redundancy, inconsistency, difficult searching, no relationships between files, poor security, difficult backup.
2. **Hierarchical model:** tree (University → Department → Student). *Adv:* fast parent–child access. *Disadv:* rigid structure, hard to model many-to-many.
3. **Relational model (1970, Dr. E. F. Codd):** data in tables, manipulated with relational algebra → foundation of RDBMS; adopted as the enterprise standard from the 1980s.
Examples: Oracle, IBM DB2, MS SQL Server, MySQL, PostgreSQL.

#### 2. Why RDBMS became the default
Table structure (easy to understand) · reduced redundancy via normalization · standard SQL · improved consistency · easier maintenance · strong security · reliable transaction processing.

#### 3. Client–Server database architecture
```
Users
  │
Client Application  (banking s/w, e-commerce site, college ERP, HMS)  — sends SQL, shows results
  │  SQL queries
Database Server     (MySQL / Oracle / PostgreSQL server) — stores data, processes SQL,
  │                  executes transactions, manages users, security, backups
Database Engine
  │
Storage devices     (HDD / SSD / RAID)
```
Example flow: Student → college website → SQL query → MySQL DB → returns student details → website displays.

#### 4. SQL-based retrieval
SQL = standard language for relational DBs. For `Student(RollNo, Name, Branch, CGPA)`:
```sql
SELECT * FROM Student;                          -- all records
SELECT Name, CGPA FROM Student;                 -- specific columns
SELECT * FROM Student WHERE RollNo = 101;       -- one student
INSERT INTO Student VALUES (104,'Neha','ECE',8.9);
UPDATE Student SET CGPA = 9.0 WHERE RollNo = 101;
DELETE FROM Student WHERE RollNo = 103;
```
(🆕 the notes list these operations; statements written by me.)

#### 5. ACID properties 📘 (very high probability)
| Letter | Meaning | Example (bank transfer ₹5,000 A→B) |
|---|---|---|
| **A**tomicity | Transaction is one unit: all or nothing | Debit A succeeds but credit B fails (crash) → **rolled back**; no partial update |
| **C**onsistency | DB moves from one valid state to another; invalid data rejected | CGPA can't exceed the maximum; total money unchanged |
| **I**solation | Concurrent transactions don't interfere | Two users book the last train seat simultaneously → only one succeeds |
| **D**urability | Once committed, permanent even after crash | Payment record survives a power failure |

**Case study: online banking 📘** — Atomicity: both debit and credit happen or neither. Consistency: balances remain valid. Isolation: simultaneous transfers don't interfere. Durability: confirmed transfer is permanently recorded.

#### 6. Transaction management
Transaction = sequence of operations as one logical unit.
```
BEGIN TRANSACTION
   Debit  Account A
   Credit Account B
COMMIT          (if error → ROLLBACK)
```
State diagram 📘:
```
Start → Active → Partially Committed → Committed
           │
         Failed → Rollback (Aborted)
```

#### 7. Concurrency control
Multi-user access without control causes **lost updates, dirty reads, inconsistent data**. Example: balance ₹10,000; User A withdraws ₹2,000 and User B withdraws ₹3,000 simultaneously — without control one overwrites the other.
Techniques: **lock-based protocols**, **timestamp ordering**, **MVCC (multiversion concurrency control)**.

**Numerical 📘+🆕 (lost update):** Balance = 10,000. Both read 10,000. A writes 10,000−2,000 = 8,000; B (still holding the old read) writes 10,000−3,000 = **7,000** → final 7,000 (A's withdrawal lost). Correct serial result = 10,000−2,000−3,000 = **5,000**. With locking, B waits for A to commit, then reads 8,000 and writes **5,000**.

#### 8. Advantages (list)
Structured storage, SQL, ACID, data integrity, security, mature technology, reliable backups; suitable for banking, ERP, healthcare, university systems.

#### 9. Limitations in cloud computing 📘 (very high probability — it is the bridge to 3.2)
- **Vertical scaling** (more CPU/RAM) has limits.
- Hard to distribute across **thousands of servers**.
- **Schema changes** are complex.
- Less suitable for **rapidly changing / unstructured** data.
- **High licensing cost** for some enterprise DBs.
→ These limits motivated **GFS, BigTable, Amazon Dynamo and NoSQL** databases.

🆕 *Extra (CAP/BASE):* RDBMS favours **C**onsistency (ACID); at cloud scale you must tolerate **P**artitions, so systems choose between C and A (CAP theorem). Dynamo picks availability (BASE: Basically Available, Soft state, Eventual consistency).

**Table: RDBMS vs NoSQL 📘 (from slide "Traditional Database vs NoSQL")**
| Feature | Relational | NoSQL |
|---|---|---|
| Schema | Fixed | Flexible |
| Scalability | Vertical | Horizontal |
| Data model | Tables | Key-value, column, document, graph |
| Joins | Supported | Limited / not required |
| Performance | Good for transactions | Good for large-scale data |
| Availability | Moderate | Very high |

---

## 3.2 CLOUD FILE SYSTEMS

### D. Why cloud file systems? 📘
Cloud apps generate data beyond one server; storage must survive machine/disk/network failures; data is spread over many **commodity** machines; replication, partitioning and metadata management are the building blocks; different workloads need different consistency/availability/performance trade-offs.
Goals: **Scalability** (add machines), **Fault tolerance** (replicate), **High throughput** (parallel access).

**Four systems at a glance:**
| System | Role |
|---|---|
| **GFS** | Distributed *files* / large-scale data (Google) |
| **BigTable** | Structured, sparse data built on GFS (Google) |
| **Dynamo** | Highly available key-value data (Amazon) |
| **Datastore** | Managed NoSQL for application data (Google Cloud) |

---

### E. Google File System (GFS) 📘

**Definition (write this):** *GFS is a scalable distributed file system developed by Google to store and process massive amounts of data across thousands of inexpensive commodity servers, providing high performance, fault tolerance and reliability for large data-intensive applications.* Used by Search, Gmail, Maps, YouTube.

**Why built:** traditional FS had limited capacity, single point of failure, hard to scale, poor fault tolerance, costly hardware, couldn't process petabytes. Google needed: huge files, thousands of servers, survive hardware failure, high-speed access, automatic recovery.

**Features:** distributed storage, high scalability, fault tolerance via replication, high throughput, automatic failure recovery, optimized for large files, concurrent access by many clients.

#### Architecture (3 components) — DRAW THIS
```
                 ┌────────────┐
                 │ GFS Client │  (Search, Gmail, Maps apps)
                 └─────┬──────┘
        1. metadata    │            ▲ 2. chunk handle + locations
           request     ▼            │
                 ┌────────────┐
                 │   MASTER   │  (metadata only: file names, directory
                 │   Server   │   structure, chunk IDs & locations,
                 └─────┬──────┘   access permissions, replication info)
         heartbeat /   │   control messages
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
  ┌───────────┐  ┌───────────┐  ┌───────────┐
  │ChunkServer│  │ChunkServer│  │ChunkServer│   ← actual data (64 MB chunks,
  │  Chunk A  │  │  Chunk B  │  │  Chunk C  │     3 replicas each)
  └───────────┘  └───────────┘  └───────────┘
 3. Client ◄──── data flows DIRECTLY ────► Chunk Servers (Master not in data path)
```
- **GFS Client:** application using GFS; asks Master for metadata, then talks directly to chunk servers; reads/writes data.
- **Master ("brain"):** stores **metadata only** — file names, directory structure, chunk IDs, chunk locations, permissions, replication info; monitors chunk servers (heartbeats), manages replication, detects failures.
- **Chunk Servers:** store the actual file data as fixed-size chunks; each holds many chunks.

🆕 *Extra depth (from the original GFS paper, not in slides):* Master keeps metadata in RAM (fast) and logs changes in an **operation log** with checkpoints; chunk locations aren't persisted but learned from chunk servers at start-up via heartbeats; Master grants a time-limited **lease** to one replica = **primary**; chunks carry **checksums**; GFS has relaxed consistency and supports **record append**.

#### File storage
File split into **64 MB chunks** (original design), each with a unique **chunk handle (ID)**; chunks may sit on different chunk servers.
`180 MB file → Chunk1 64 MB, Chunk2 64 MB, Chunk3 52 MB`.

#### Read operation (steps) 
1. Client asks Master for metadata (file name + chunk index). 
2. Master returns chunk handle and chunk-server locations. 
3. Client contacts the nearest/chosen chunk server directly. 
4. Chunk server sends the data. → **Master is not involved in data transfer** (avoids bottleneck).

#### Write operation (steps)
1. Client asks Master for chunk information. 
2. Master identifies the **Primary** chunk server (and replicas). 
3. Client sends data to **all replicas**. 
4. **Primary** coordinates (orders) the write. 
5. **Secondary** replicas apply the write. 
6. Confirmation returned to client.
```
Client ──(1)──► Master        Client ──(3 data)──► Primary ──► Secondary 1
Client ◄─(2)── Master (primary + replicas)                └──► Secondary 2
Client ◄────────── (6) ack ◄── Primary ◄── (5) acks ◄──────┘
```

#### Replication & fault tolerance
Each chunk stored on multiple chunk servers — typically **3 replicas** → availability, reliability, load balancing.
If a chunk server fails: Master detects via **heartbeat** messages → clients are redirected to another replica → Master **creates a new replica** on a healthy server to restore the replication level — automatic, no manual intervention.

#### Advantages / Limitations / Applications
- **Adv:** highly scalable, petabytes, high throughput, low-cost hardware, automatic recovery, supports distributed computing, optimized for large sequential reads/writes.
- **Limitations:** not good for many small files; **Master can become a bottleneck**; heavy network traffic during replication; tuned for Google's workloads; not for low-latency random access.
- **Applications:** search engines, web indexing, analytics, machine learning, video storage/streaming, email, cloud storage, big-data processing (storage layer under MapReduce).

#### Traditional FS vs GFS 📘
| Feature | Traditional FS | GFS |
|---|---|---|
| Storage | Single server | Distributed servers |
| Scalability | Limited | Very high |
| Fault tolerance | Low | High |
| Replication | Usually no | Yes |
| File size support | Small–medium | Very large |
| Availability | Moderate | High |
| Hardware | High-end servers | Commodity hardware |
| Recovery | Manual | Automatic |
| Throughput | Moderate | High |

#### Numericals — GFS 📘 (+ 🆕 variations)
**N-GFS-1 (notes' activity):** 200 MB video, chunk = 64 MB, 3 replicas.
- Chunks = ⌈200/64⌉ = ⌈3.125⌉ = **4** (64, 64, 64, **8** MB).
- Copies = 4 × 3 = **12 chunk copies**, spread over chunk servers (each replica on a different server).
- Raw storage used = 200 MB × 3 = **600 MB** (the last chunk only occupies 8 MB, not 64).
- If one chunk server fails: Master (heartbeat) detects → redirects clients to surviving replicas → creates a new replica elsewhere → 3 copies restored.

**N-GFS-2 🆕:** 1 TB file, 64 MB chunks, 3 replicas. Chunks = 1 TB / 64 MB = 1,048,576 MB / 64 = **16,384**. Replicas = 16,384 × 3 = **49,152**. Raw storage = **3 TB**.

**N-GFS-3 🆕 (why big chunks):** same 1 TB with 64 KB blocks would need 16,777,216 metadata entries (1,024× more) → Master RAM/overload; hence large chunks reduce metadata and client–master traffic.

**N-GFS-4 🆕:** 180 MB file → ⌈180/64⌉ = 3 chunks (64+64+52) → 9 copies at 3×.

---

### F. BigTable Storage 📘

#### NoSQL intro
**NoSQL = "Not Only SQL"**: non-relational databases for huge volumes of structured, semi-structured and unstructured data; give horizontal scalability, high availability, fault tolerance, flexible schema, faster access to large datasets. (Comparison table is under 3.1-C above.)

**Definition (write this):** *Google BigTable is a distributed, scalable, column-family NoSQL database developed by Google to store petabytes of structured data across thousands of commodity servers, offering high scalability, high performance, low latency and fault tolerance.*
**Features:** distributed architecture, column-family storage, automatic partitioning, dynamic scalability, fault tolerance, replication, high throughput, sparse data, billions of rows.
**Used in:** Google Search, Gmail, Maps, Earth, Analytics, YouTube, Finance (+ ML datasets, IoT, real-time analytics, logging).

#### Data model — a sorted, sparse, multi-dimensional map
BigTable uses **Row Key → Column Family → Column → Timestamp**.
- **Row key:** unique id of a row; **sorted lexicographically**; determines physical storage order; immutable after creation; efficient searching.
- **Column family:** logical group of related columns (Personal{Name,Age}, Contact{Email,Mobile}, Education{Degree,CGPA}); unit of storage/access control.
- **Column:** lies inside a family; different rows can have different columns (→ sparse).
- **Timestamp:** each cell keeps multiple versions (2024 ₹50,000; 2025 ₹55,000; 2026 ₹60,000) → version control/history.
```
Row key │        Personal        │      Contact        │   Education
        │ Name     Age           │ Email    Mobile     │ Degree  CGPA
user001 │ Asha     20            │ asha@..  98xxx      │
user002 │ Rahul                  │ rahul@.. —          │ B.Tech  8.2        ← sparse: empty cells cost nothing
Cell = (row key, column family:column, timestamp) → value
```
Sparse example from notes: Rahul(Email✓ Mobile✓ Address✗), Priya(✓✓✓), Amit(✓✗✗).

#### Architecture — DRAW THIS
BigTable is built on **GFS (storage), Chubby (lock service), SSTables (file format)**.
```
                    ┌────────┐
                    │ Client │────────── (data reads/writes go directly to tablet servers)
                    └───┬────┘
          ┌─────────────┴──────────────┐
          ▼                            ▼
   ┌───────────────┐  assigns     ┌──────────┐
   │BigTable Master│─ tablets ───►│  Chubby  │ (distributed lock service:
   └───────┬───────┘  & balances  └──────────┘  master election, sync,
           │                                      metadata, failure detection)
   ┌───────┼────────────┐
   ▼       ▼            ▼
┌────────┐┌────────┐┌────────┐
│Tablet  ││Tablet  ││Tablet  │  serve reads/writes, split big tablets
│Server 1││Server 2││Server 3│
│Tablet A││Tablet B││Tablet C│
└───┬────┘└───┬────┘└───┬────┘
    └─────────┴─────────┘
              ▼
   Google File System (stores SSTable files + commit logs; replication)
```
- **Client:** sends read/write requests, talks to Tablet Servers.
- **Master:** assigns tablets to tablet servers, load balancing, recovery after failure, monitors tablet servers; **not** in the normal data path.
- **Tablet Server:** stores/manages tablets; reads, writes, splits large tablets, serves clients.
- **GFS:** stores SSTable files; replication, fault tolerance, large-scale storage.
- **Chubby:** master election, synchronization, metadata (🆕 e.g. location of the root tablet), failure detection.
- **Tablet:** **horizontal partition** of a table (Student table → Tablet1 rows 1–1000, Tablet2 rows 1001–2000, Tablet3 rows 2001–3000) → parallel processing, load balancing, easy scalability.
- **SSTable (Sorted String Table):** BigTable's file format — **immutable**, sorted by row key, fast searching, efficient storage; benefits: faster reads, efficient indexing, better compression, high performance.

#### Read and write path 📘
**Read:** client sends request → tablet server locates the row → data fetched from the appropriate SSTable (🆕 merged with MemTable) → result returned.
**Write:** client sends write → **(1) appended to commit log (durability)** → **(2) stored in in-memory MemTable** → **(3) when MemTable is full it is flushed to disk as a new SSTable** → **(4) background compaction** merges SSTables.
```
Write ─► Commit log (on GFS) ─► MemTable (RAM) ──full──► new SSTable (GFS) ──► compaction merges SSTables
Read  ─► MemTable + SSTables ─► merged result
```
🆕 *Extra:* tablet location is found via a 3-level hierarchy (Chubby file → root tablet → METADATA tablets → user tablet); clients cache locations.

**Advantages:** scalable, high performance, billions of rows, fault tolerant, automatic load balancing, distributed, efficient for sparse data, flexible schema.
**Limitations:** no complex SQL joins; limited transaction support vs RDBMS; complex architecture; optimized for Google's infrastructure; unsuitable for complex relational queries.

**BigTable vs Relational 📘**
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
| Data size | Petabytes | GB to TB |

**BigTable vs GFS 📘**
| Feature | GFS | BigTable |
|---|---|---|
| Type | Distributed file system | NoSQL database |
| Stores | Files | Structured data |
| Data unit | Chunks | Tablets |
| Storage | File-based | Column-family |
| Uses | Large file storage | Structured data storage |
| Depends on | Standalone | Built on GFS |

**Numericals (🆕 — notes have none; likely "assume data"):**
- **N-BT-1 cell lookup:** value of *(user001, Contact:Email, latest timestamp)* → "asha@example". Number of versions of salary cell = 3 (2024/2025/2026); latest = ₹60,000.
- **N-BT-2 tablet count:** 3,000,000 rows, tablet = 1,000 rows → 3,000 tablets; on 10 tablet servers → 300 tablets/server (balanced by Master).

---

### G. Dynamo Architecture 📘

**Definition:** Dynamo = Amazon's **highly available, distributed key-value storage system** for apps needing very high availability, scalability, low latency and fault tolerance, even when servers fail (shopping carts, product catalogs, customer preferences, session info). Philosophy: *better to stay available and accept temporary inconsistency than become unavailable during failures.*

**Why needed:** RDBMS struggle with millions of users/requests, continuous availability, geo-distributed servers, very low response time; typically centralized/strongly consistent. If the shopping cart depended on Server A and A fails, the service goes down. Dynamo uses **data partitioning, replication, distributed nodes, failure detection, recovery**.

**Characteristics:** Distributed · **Decentralized** (no single central DB server; no master) · Highly available · Fault tolerant (disk/server/network/software/power failure) · Scalable (add nodes) · **Eventually consistent**.

**Data model:** simple key-value (`Key → Object`): `User101 → {Name:"John", Cart:"Product101, Product205"}`; `Product1001 → {Name:"Laptop", Price:65000}`. Simple, schema-flexible, fast key-based access, **no joins**.

**Architecture (draw):**
```
                   Client
                     │ get(key)/put(key,value)
          ┌──────────┴───────────┐
          ▼          ▼           ▼
       Node 1     Node 2      Node 3        ← each node owns part of the key space
       Data A     Data B      Data C           (Nodes arranged on a logical RING)
       Replica    Replica     Replica
       Node 4     Node 5      Node 6        ← replicas on other nodes
```
**Major mechanisms (mind-map 📘):** Partitioning (consistent hashing → virtual nodes) · Replication (multiple copies) · Consistency (eventual) → fault tolerance → hinted handoff → versioning.

#### 1. Consistent hashing (partitioning)
**Problem with `hash(key) % N`:** adding/removing a server changes N → most keys must move.
**Idea:** put **both keys and nodes on the same hash space arranged as a ring**; each key is stored on the first node found going clockwise from the key's position.
```
            Node A
           ●
      ●          ●
   Node D          Node B       key K: hash(K) → position on ring
           ●                    → stored at next node clockwise
          Node C
```
**Advantages:** scalability (add servers without reshuffling everything), fault tolerance (neighbour/replica nodes take over), **reduced data movement** (only a portion moves), dynamic membership (join/leave/fail/recover without stopping the system).

**Virtual nodes (vnodes):** a physical server owns **multiple positions** on the ring (Physical A → V1,V2,V3; Physical B → V4,V5,V6) → better load balancing, easier add/remove, better failure recovery, more uniform distribution.

**Data partitioning example 📘:** 1,000,000 keys over 4 nodes → 250,000 each.

#### 2. Replication
Several copies of each item. **Replication factor N** = number of copies (N=3 → three replicas; N=5 → five). If Node A fails, Node B/C still serve → data still available. Benefits: availability, fault tolerance, durability, reduced data-loss risk. Higher N → more storage, network traffic, sync overhead.

#### 3. Eventual consistency
Replicas may diverge for a short time but **converge when updates stop**.
Example 📘: price ₹50 on A,B,C. Update to ₹60: A=60, B=60, C=50 (temporary inconsistency) → after synchronisation A=B=C=60.
*Pros:* high availability, low latency, better scalability. *Con:* different users may briefly see different versions.

#### 4. Quorum — N, R, W 📘 (numerical favourite)
- **N** = number of replicas, **R** = replicas that must respond to a **read**, **W** = replicas that must acknowledge a **write**.
- If **R + W > N**, read set and write set **overlap** in at least one replica → a read sees at least one replica that took the latest write.
- Example: N=3, R=2, W=2 → R+W = 4 > 3 ✔ overlap.

**Why overlap is guaranteed (pigeonhole) 🆕:** a write touches W nodes, a read touches R nodes out of N; if R+W > N the two sets can't be disjoint.

**Numerical table 🆕 (make your own quick checks):**
| N | R | W | R+W | > N? | Behaviour |
|---|---|---|---|---|---|
| 3 | 2 | 2 | 4 | Yes | Balanced (Dynamo typical) |
| 3 | 1 | 3 | 4 | Yes | Fast reads, slow/fragile writes (any node down blocks writes) |
| 3 | 3 | 1 | 4 | Yes | Fast writes, slow reads |
| 3 | 1 | 1 | 2 | **No** | Fastest/most available, may read stale data (pure eventual) |
| 5 | 3 | 3 | 6 | Yes | Tolerates 2 failures for both reads & writes |
| 5 | 2 | 2 | 4 | **No** | Stale reads possible |
*Fault tolerance:* writes survive N−W node failures, reads survive N−R failures. For N=3,R=2,W=2: tolerates **1** node failure for both.

#### 5. Failure detection & hinted handoff
Dynamo detects unreachable nodes (e.g. A ✓, B ✓, C ✗) and redirects operations to other replicas.
**Hinted handoff:** if the intended replica (Node C) is down, **another node D temporarily stores the data** (with a hint of its intended owner); when C recovers, D **sends the data to C**. Keeps writes available.
```
Data X should go to  A, B, C       C is DOWN
A ← X     B ← X     D ← X (temporary "hinted" copy)
C recovers:  D ──── X ────► C   (D then deletes its temp copy)
```
(🆕 this is the "sloppy quorum" variant mentioned in the Dynamo-vs-Datastore slide.)

#### 6. Versioning & conflict resolution — vector clocks
Replicas can get independent updates (User 1 and User 2 both edit the cart) → conflicts. Dynamo keeps version info via **vector clocks** to tell: (a) one version is newer (it *descends* from the other), or (b) versions are **concurrent/conflicting** → reconcile.
Example 📘: V1 = [A:1], V2 = [A:2] → V2 derived from V1 (newer). V1 = [A:1], V2 = [B:1] → **concurrent** → needs conflict resolution.
**Rule 🆕:** clock X ≤ clock Y if every counter in X ≤ the counter in Y. If neither X ≤ Y nor Y ≤ X → conflict. E.g. [A:2,B:1] vs [A:1,B:2] → conflict (merged by application, e.g. union of cart items).

#### Real-life example 📘 (shopping cart, steps)
Customer C101 adds iPhone → **key** C101 → `hash(C101)` finds position → cart **replicated** on Nodes A,B,C → Node B fails ❌ → A and C serve → **hinted handoff** stores temp copy on another node → B returns → temp node sends data back (recovery) → replicas **eventually consistent**.

**Exam format for "Explain Dynamo architecture" (10 m):** definition (2) → characteristics (2) → diagram of ring (2) → consistent hashing + vnodes (2) → replication/quorum/eventual consistency (2) → hinted handoff + vector clocks (2) → one example.

---

### H. Datastore 📘

**Definition:** a **cloud datastore** is a storage system to store, organise, manage and retrieve data in the cloud, offering scalability, availability, reliability, accessibility and fault tolerance over the network (customer records, product catalogs, transactions, images/videos, logs, IoT data, sessions, documents).
**Google Cloud Datastore:** highly scalable **managed NoSQL** database; historically "App Engine Datastore", now **Firestore in Datastore mode**. Needs: scalable storage, automatic replication, high availability, flexible structures, distributed access.

**Why datastores (problems with local disk):** (1) limited storage (1 TB → need 10 TB); (2) server failure → app unavailable & data inaccessible (fix: replication/redundancy); (3) growing users (1,000 → 10,000 → 1,000,000) need to scale; (4) global access (India, USA, Europe, Singapore, Australia → one cloud datastore).

**Characteristics:**
1. **Scalability** – vertical (bigger server: 4 cores/16 GB → 32 cores/128 GB) vs **horizontal** (add servers); cloud-native stores prefer horizontal.
2. **Availability** – stays accessible if a machine fails (redundancy, replication, multiple availability zones).
3. **Durability** – no loss after successful store (Replica 1, 2, 3).
4. **Fault tolerance** – survives server/disk/network/software/AZ failure (data A in AZ-1, AZ-2, AZ-3).
5. **Data persistence** – survives app shutdown, server/VM/container restart (important when instances are created/destroyed often).

**Types of cloud datastores 📘:** relational, key-value, document, column-family, graph, object storage, file storage, block storage, in-memory.

#### Datastore data model — DRAW THIS
```
Relational:  Table → Rows → Columns          Datastore:  Kind → Entity → Properties (+ Key)

Kind: Student
 ├─ Entity 1   Key: Student+101   Properties: name=John, course=CSE
 └─ Entity 2   Key: Student+102   Properties: name=Mary, course=IT, email=…   (extra property OK)
```
- **Entity** = individual object (≈ row): `Student{studentId:101, name:"Rahul", course:"CSE", age:20}`.
- **Kind** = category grouping similar entities (≈ table): Student, Teacher.
- **Properties** = named values of an entity (≈ columns); entities of the *same kind can have different properties* → **flexible schema**.
- **Key** = unique identity: **Kind + ID** (e.g. Student+101) or a string name.
- **Ancestor (hierarchy):** entities can form parent–child paths: `University/ABC → Department/CSE → Student/101, Student/102`.

**Indexing:** indexes make queries efficient; e.g. query `course = "CSE"` uses an index mapping Course=CSE → Student 101, 105, 109. Many queries *depend* on indexes.
**Queries:** `Kind=Student WHERE course="CSE"`; `age > 20`; `course="CSE" AND age > 20`.
**Transactions:** atomic operations on related entities (read marks → update total → update result; failure ⇒ no incomplete update).
**Consistency:** *Strong* — read sees latest committed write (Write → Read → latest). *Eventual* — read may see an older value until replicas sync. (Datastore *historically* offered different guarantees by operation/query type.) 🆕 Note: in current Firestore-in-Datastore mode, Google documents strong consistency for queries too — answer as per your slides ("historically differed") unless the examiner asks about the modern version.

**Datastore architecture 📘:**
```
Application
    │
Datastore API
    ├───────────────┐
Entity Store      Indexes
    └───────┬───────┘
     Distributed Storage
   Node A    Node B    Node C   ◄── Replication
```

**RDBMS vs Datastore 📘**
| Relational DB | Datastore |
|---|---|
| SQL database | NoSQL database |
| Tables | Kinds |
| Rows | Entities |
| Columns | Properties |
| Fixed schema | Flexible schema |
| SQL queries | Datastore query mechanisms (property queries + indexes) |
| Joins common | Avoids traditional joins |
| Vertical scaling traditionally | Designed for horizontal scaling |
| Relational model | Document/entity model |
| Foreign keys | Key / ancestor relationships |
| Schema changes can be significant | Flexible entity structure |

**Dynamo vs Google Datastore 📘**
| Feature | Dynamo | Google Datastore |
|---|---|---|
| Developed by | Amazon | Google |
| Type | Distributed key-value store | NoSQL document/entity database |
| Data model | Key → Value | Kind → Entity → Properties |
| Major focus | Very high availability | Scalable application database |
| Consistency | Primarily eventual | Supports different guarantees |
| Partitioning | Consistent hashing | Distributed automatically |
| Replication | Yes | Yes |
| Failure handling | Sloppy quorum, hinted handoff | Managed by Google |
| Version handling | Vector clocks | Managed DB mechanisms |
| Query model | Primarily key-based | Property-based queries + indexes |
| Typical use | Amazon internal services | Google App Engine apps |

---

### I. Cross-cutting: Compare & choose 📘

| Dimension | GFS | BigTable | Dynamo | Datastore |
|---|---|---|---|---|
| Primary abstraction | Files / chunks | Tables / tablets | Key-value | Entities |
| Main priority | Throughput | Scalability | Availability | Managed app data |
| Partitioning | Chunks | Tablets | Hash ring | Managed |
| Replication | Yes | Yes | Yes | Managed |
| Consistency | Strong-ish semantics | Strong consistency model | Eventual | Managed / transactional features |
| Typical workload | Large data files | Structured big data | Always-on services | Cloud applications |
| Architecture style | Master + chunk servers | Master + tablet servers (on GFS) | Decentralized ring (no master) | Managed service |

**Choose GFS** for very large files and high-throughput batch/streaming · **BigTable** for massive sparse structured data with row-based access · **Dynamo-style** when high availability & low latency matter and eventual consistency is acceptable · **Datastore** for a managed NoSQL service for app entities (no cluster management).

**One-line memory hooks 📘 (the deck's "Exam-oriented key points"):** GFS: Master = metadata, chunk servers = data + replicas; client gets metadata from Master but moves bulk data directly. BigTable: tablets served by tablet servers; row key + column families + columns + timestamped values. Dynamo: decentralized + consistent hashing + replication + eventual consistency; N,R,W with R+W>N. Datastore: managed schema-flexible NoSQL with entities, kinds, properties.
**Core idea:** cloud storage systems distribute data, replicate it, and trade among scalability, consistency, availability and performance.

---

# PART 4 — PYQ SOLUTIONS

## 4.0 Audit: every PYQ question screened against Module 3

| Paper | Questions screened | Direct Module-3 questions | Adjacent items |
|---|---|---|---|
| **May 2025** (75 m, Minors) | Q1 (characteristics of cloud, levels of virtualization, XaaS, Aneka, microservices, Aneka foundation services), Q2 (SOA, MapReduce, deployment models, VM/.vmx, VM migration), Q3 (Aneka fabric, microservices vs monolith, Docker), Q4 (Aneka scheduling, EC2, AppEngine/GCP), Q5 (Aneka, VM migration, **S3**, data-centre impact, AWS arch, MaaS) | **None** | Q5(iii) **Amazon S3** ⭐~; Q2A(ii) *MapReduce* = syllabus 3.3 (out of your scope) |
| **Dec 2022** (100 m) | SaaS, scalability vs elasticity, private vs public, **SAN vs NAS**, Jenkins/CI, Web 2.0, utility computing, PaaS, execution virtualization, Hyper-V, Aneka, AppEngine, DVFS, federation, Docker, MBaaS, Xen, VMware, spot cloud, MaaS | **None** | Q1(iv) **SAN vs NAS storage virtualization** ⭐~ |
| **Nov–Dec 2021** (50 m) | VT-x/VT-d match, AppEngine tech, federation, Aneka, process-level virt, physical vs actual core, Web 1.0/2.0/3.0, reference model, PaaS categories, **Amazon SimpleDB vs RDS**, server consolidation, power mgmt, legal issues in federation, MOCC, AppEngine components, MaaS, Aneka dynamic provisioning | **None** | Q1B(v) **SimpleDB vs RDS** ⭐~ (closest to 3.1/3.2) |
| **May–Jun 2021** (50 m, Distributed & Cloud Computing) | Power mgmt layers, MapReduce/MPI, VM live migration, **SAN/LAN/NAS match**, reliability/availability, load policies, Microsoft services, HPC/HTC, GPU vs CPU, cluster job mgmt, public vs private cloud, science gateways | **None** | Q1(A)IV **SAN/LAN/NAS match** ⭐~ |

**Conclusion:** Module 3 as a syllabus unit has never been examined in the available papers. The questions below are (a) the four adjacent official questions, solved; then (b) 🆕 predicted questions solved exam-style. **Do not rely on "it was asked before" — rely on the Part 2 probability ranking.**

---

## 4.1 Adjacent official PYQs (⭐~) — solved

### Q (Nov–Dec 2021, Q1B(v)): *What is the difference between Amazon SimpleDB and Amazon RDS?* (short answer, ~5 m)

**Answer.**
- **Amazon RDS (Relational Database Service):** managed **relational** DB service; runs engines such as MySQL, PostgreSQL, Oracle, SQL Server, MariaDB; fixed schema, **SQL**, joins, **ACID** transactions; scales mainly **vertically** (bigger instance, plus read replicas); AWS handles patching, backup, failover.
- **Amazon SimpleDB:** managed **non-relational (NoSQL) key-value/attribute store** — data in *domains → items → attributes (name–value pairs)*; **schema-less**; **no joins**, simple SELECT-style query; **eventually consistent** by default (consistent read optional); automatically indexed; built for **high availability and horizontal scaling** with small data sets — the same philosophy as Dynamo (Part 3-G).

| Basis | Amazon RDS | Amazon SimpleDB |
|---|---|---|
| Model | Relational (tables, rows, columns) | NoSQL (domains, items, attributes) |
| Schema | Fixed | Flexible / schema-less |
| Query | Full SQL, joins | Simple queries, no joins |
| Transactions | ACID | No multi-item ACID transactions |
| Consistency | Strong | Eventual (consistent read optional) |
| Scaling | Vertical (+ read replicas) | Horizontal, automatic |
| Best for | Structured, transactional apps (banking, ERP) | Light-weight, flexible, high-availability data (metadata, catalogs) |

(🆕 SimpleDB/RDS specifics are standard AWS facts, not from your notes; the RDBMS-vs-NoSQL reasoning is from Module 3 notes.)

### Q (Dec 2022, Q1(iv), 5 m): *Compare SAN and NAS storage virtualization.* — adjacent (storage, probably covered under virtualization module)

| Basis | SAN (Storage Area Network) | NAS (Network Attached Storage) |
|---|---|---|
| Access level | **Block-level** access (appears as a local disk) | **File-level** access (shared folders) |
| Network | Dedicated high-speed network (Fibre Channel / iSCSI) | Standard Ethernet/LAN (NFS, SMB/CIFS) |
| Connects | Servers ↔ shared disk arrays | Clients ↔ a file server/appliance with disks |
| Protocols | FC, iSCSI, FCoE | NFS, SMB/CIFS |
| Performance | Very high, low latency (databases, VMs) | Moderate; good for file sharing |
| Cost/complexity | High | Lower, simple setup |
| Typical use | Databases, virtualization, enterprise apps | File shares, backups, home directories |
| Virtualization role | Pools block storage into LUNs presented to hosts/VMs | Pools file shares; file system managed by NAS |
Diagram:
```
SAN:  Servers ──FC/iSCSI switch──► Disk arrays (block)
NAS:  Clients ──LAN──► NAS appliance (file system + disks) (file)
```

### Q (May–Jun 2021, Q1(A)IV, 2 m): *Match: 1 SAN, 2 LAN, 3 NAS with A) Connect client hosts to big servers, B) Connects client hosts directly to the disk arrays, C) Connects servers to network storage such as disk arrays.*
SAN → **C**; LAN → **A**; NAS → **B**. Options listing: a(1A,2B,3C) b(1B,2A,3C) c(1C,2B,3A) d(1C,2A,3B) → **Answer: (d) 1-C, 2-A, 3-B**.

### Q (May 2025, Q5(iii), 5 m): *Amazon Simple Storage Service (S3)* — adjacent (cloud object storage)
- **Definition:** AWS **object storage** service: virtually unlimited, durable, highly available storage accessed over HTTP/REST (and SDK/CLI).
- **Concepts:** **Bucket** (container, globally unique name, region-bound) → **Object** (data + metadata, up to 5 TB) identified by a **key**; flat namespace (folders are just key prefixes).
- **Features:** durability 99.999999999 % ("11 nines") via replication across multiple facilities/AZs; versioning; lifecycle policies; storage classes (Standard, Intelligent-Tiering, Standard-IA, Glacier…); encryption; access control (IAM, bucket policies, ACLs); static website hosting; cross-region replication.
- **Uses:** backup/archive, media storage, data lakes/big-data analytics, static websites, software distribution.
```
Client ──HTTP(S) PUT/GET (bucket + key)──► S3 ──► objects replicated over multiple AZs
```
(🆕 S3 facts are standard AWS knowledge, not in your Module 3 notes. S3 shares Dynamo's lineage of key→object access, tying to Part 3-G.)

> **MapReduce (May 2025 Q2A(ii))** → syllabus 3.3, excluded from your scope as you specified. Ask me if you want 3.3 added.

---

## 4.2 🆕 PREDICTED QUESTIONS — grouped by topic, solved exam-style
*(All 🆕: none of these appeared in a PYQ; they are the question types the notes make most probable. Diagram + headings + a table = full marks.)*

### Topic 3.1-B: Storage techniques

**P1 (5 m). Explain row-oriented and column-oriented storage with example.**
*Ans.* **Row-oriented:** all values of one record stored contiguously: `Row1→(101,Alice,Computer,20)…`. Fast for OLTP (insert/update/delete, whole-record fetch); used in banking, e-commerce, ERP; weak for analytic queries (reads unneeded columns). **Column-oriented:** values of one column stored together: `StudentID→101,102,103; Name→Alice,Bob,Charlie; Dept→…; Age→20,21,22`. Fast aggregates (SUM/AVG/COUNT), excellent compression, ideal for OLAP/data warehouses; slow inserts/updates. Diagram (draw both layouts) + comparison table from Part 3-B + example: `SELECT AVG(Age)` reads 4 MB vs 16 MB (N1).

**P2 (10 m). Explain indexed storage in relational databases. Describe the types of indexes with examples.**
*Ans.* Definition + textbook analogy; diagram (Index → address 1050 → record); four types — primary, secondary (`CREATE INDEX idx_department ON Student(Department)`), clustered (leaf = data pages; one per table), non-clustered (key→pointer, many per table) — with the two small diagrams from 3-B; advantages (fast search, sorting, joins) and disadvantages (extra space, slower writes); clustered vs non-clustered table; mention B+ tree is the usual structure (O(log n)).

**P3 (5 m). Heap vs sequential file organization.**
| | Heap | Sequential |
|---|---|---|
| Order | None (insert where space) | Sorted by primary key |
| Insert | Very fast | Slow (keep order) |
| Search | Slow (full scan) | Medium; fast sequential/range |
| Range queries | Poor | Efficient |
| Use | Bulk loading, frequent inserts | Ordered data, range reports |

**P4 (5 m). Short note: B+ tree / hashing.** B+ tree: balanced, all searches O(log n), insert/delete O(log n), range queries via linked leaves, used by most RDBMS for indexes — diagram 50/20,80/10,30,60,90. Hashing: `Hash(key)→bucket`, O(1) equality search, poor range queries, collisions handled by chaining/overflow. Compare in 3 lines.

**P5 (5 m). Scenario — Student Information System: which technique for each task?** → answer table in Part 3-B (fees→row; reports→column; search→index; bulk import→heap) with a reason for each.

**P6 (5 m). Normalization with example; partitioning types.** Use the Alice/DBMS/OS before-after example; partitioning: horizontal/vertical/range/hash/list with Sales-by-year example.

### Topic 3.1-C: Default mechanism & ACID

**P7 (10 m). Why did relational databases become the default storage and retrieval mechanism since the 1980s? Explain the client-server architecture.**
*Ans (structure):* (1) Before 1980 – file systems & hierarchical model and their problems; (2) 1970 Codd's relational model; (3) Reasons: table structure, normalization, SQL, consistency, security, reliable transactions; (4) Client–server diagram: Users → Client app → SQL → DB server → DB engine → HDD/SSD/RAID, with the student-portal example; (5) SQL retrieval examples; (6) Advantages; (7) conclude with limitations in cloud.

**P8 (10 m). Explain ACID properties with an online banking example. Also explain transaction states.**
*Ans.* Table of A/C/I/D with ₹5,000 transfer (Part 3-C-5) + case study; transaction block `BEGIN … COMMIT / ROLLBACK`; state diagram Start→Active→Partially Committed→Committed; Active→Failed→Rollback. Add the lost-update numerical (final 7,000 vs correct 5,000) to illustrate Isolation.

**P9 (5 m). Describe concurrency problems and control techniques.** Lost updates, dirty reads, inconsistent data; example ₹10,000 − ₹2,000 − ₹3,000; remedies: locking, timestamp ordering, MVCC (one line each).

**P10 (10 m). Discuss limitations of RDBMS in cloud computing. How do GFS/BigTable/Dynamo address them?**
*Ans.* Limitations (5 bullets, Part 3-C-9) → table RDBMS vs NoSQL → mapping: **GFS** removes single-server capacity/failure limits (commodity machines, replication); **BigTable** gives horizontal scaling, flexible/sparse schema; **Dynamo** gives availability & partition tolerance via consistent hashing + eventual consistency; **Datastore** gives managed flexible NoSQL. Trade-off: give up joins/full ACID, gain scale & availability.

### Topic 3.2-E: GFS

**P11 (10 m). Explain the architecture of Google File System with a neat diagram. Describe the read and write operations.** *(highest probability)*
*Ans (structure, ~marks):* Definition (1) · Why GFS/features (1) · Diagram with Client–Master–ChunkServers (3) · Role of each component with metadata list (2) · Chunking: 64 MB, chunk handle, 180 MB example (1) · Read steps (1) · Write steps (1) · Replication/fault tolerance (heartbeat → redirect → re-replicate) (1) · Advantages/limitations (short). Content: Part 3-E verbatim.

**P12 (5 m, numerical). A 200 MB file is stored in GFS with 64 MB chunks and 3 replicas. Find number of chunks, total chunk copies, and raw storage; explain what happens if a chunk server fails.**
*Solution.* Chunks = ⌈200/64⌉ = **4** (64+64+64+8 MB). Copies = 4×3 = **12**. Raw storage = 200×3 = **600 MB** (last chunk only 8 MB used). Failure: Master detects missing heartbeat → clients served from other replicas → Master re-replicates lost chunks to healthy servers → 3 copies restored.
*Variation (🆕):* 1 TB file → 16,384 chunks, 49,152 replicas, 3 TB raw.

**P13 (5 m). Compare traditional file system and GFS.** → 9-row table (Part 3-E). **Limitations of GFS (5 m)** → five bullets: small files, master bottleneck, replication traffic, Google-specific, no low-latency random access.

### Topic 3.2-F: BigTable

**P14 (10 m). Explain BigTable data model and architecture.**
*Ans.* Definition (1) · Row key/column family/column/timestamp with the Rahul/Priya/Amit sparse example and salary-versions example (3) · Architecture diagram: Client, Master, Chubby, Tablet servers, GFS (3) · Components' roles (2) · Tablet & SSTable (1) · Read/Write path: commit log→MemTable→SSTable→compaction (1). Content: Part 3-F.

**P15 (5 m). Write short notes on SSTable and MemTable / Chubby / Tablet.**
*SSTable:* immutable, sorted-by-row-key file format on GFS; fast lookup, efficient indexing, compression. *MemTable:* in-memory sorted buffer of recent writes, flushed to a new SSTable when full; every write first goes to the commit log for durability. *Compaction:* merges SSTables. *Chubby:* distributed lock service — master election, synchronisation, metadata, failure detection. *Tablet:* horizontal partition (row range) served by one tablet server.

**P16 (5 m). BigTable vs RDBMS / BigTable vs GFS.** → tables in Part 3-F.

### Topic 3.2-G: Dynamo

**P17 (10 m). Explain Dynamo architecture. Discuss consistent hashing, replication, and eventual consistency.**
*Ans.* See "Exam format" at end of 3-G: definition, characteristics, ring diagram, consistent hashing & vnodes, replication (N=3), eventual consistency (₹50→₹60 example), hinted handoff, vector clocks, shopping cart.

**P18 (5 m, numerical). In Dynamo N=3, R=2, W=2. (a) Is the read-after-write overlap guaranteed? (b) How many node failures can reads/writes tolerate? (c) What if R=1, W=1?**
*Solution.* (a) R+W = 4 > N = 3 → **yes**, every read quorum shares ≥1 replica with the latest write quorum. (b) Writes tolerate N−W = **1** failure; reads tolerate N−R = **1** failure. (c) R+W = 2 ≤ 3 → no guaranteed overlap → fastest and most available, but may return **stale** data (eventual consistency only).

**P19 (5 m, numerical 🆕). Why is consistent hashing better than `hash(key) mod N`? Illustrate with data.**
*Solution.* With keys 1…20 and 4 servers (`k mod 4`), adding a 5th server changes the mapping to `k mod 5`. Keys keeping the same server: 1, 2, 3, 20 → only **4 of 20 stay; 16 (80 %) must move**.
Consistent hashing: ring positions 0–99, nodes A=20, B=45, C=70, D=90; a key goes to the first node clockwise: key 10→A, 30→B, 50→C, 75→D, 95→A (wraps). Add node E=60: only keys in (45, 60] move (key 50: C→E); keys 10, 30, 75, 95 are **unaffected** → only ~1 of 5 here, in general ≈ K/N keys. With replication N=3, key 30's replicas = next 3 distinct nodes clockwise = B, C, D.

**P20 (5 m). Explain hinted handoff / vector clocks / virtual nodes.** Use diagrams and examples of Part 3-G (D holds X for C; [A:1] vs [A:2] vs [B:1]; physical node A → V1,V2,V3).

### Topic 3.2-H: Datastore

**P21 (10 m). Explain the Google Cloud Datastore data model and its characteristics. Compare it with an RDBMS.**
*Ans.* Definition + Firestore-in-Datastore-mode note · why datastores (4 problems) · characteristics (scalability, availability, durability, fault tolerance, persistence) · model diagram Kind→Entity→Properties + Key + ancestor example · indexing/queries/transactions · consistency (strong vs eventual) · RDBMS-vs-Datastore table.

**P22 (5 m). Distinguish Dynamo and Google Datastore.** → 11-row table (Part 3-H).

### Cross-topic

**P23 (10 m). Compare GFS, BigTable, Dynamo and Datastore. Which would you choose for (a) storing web-crawl logs, (b) user profiles with sparse attributes, (c) always-on shopping cart, (d) a managed app backend?**
*Ans.* Four-way table (Part 3-I). (a) **GFS** (huge sequential files, throughput); (b) **BigTable** (sparse, row-keyed, versioned); (c) **Dynamo** (availability, writes never rejected, eventual consistency OK); (d) **Datastore** (managed, flexible entities, no cluster ops). Close with the trade-off sentence: *systems trade among scalability, consistency, availability and performance.*

**P24 (objective, 1–2 m each).** Quick answers:
- GFS chunk size? **64 MB**. Default replicas? **3**. Who stores metadata? **Master**. Do clients send data through the Master? **No**.
- BigTable file format? **SSTable**. Lock service? **Chubby**. Horizontal partition? **Tablet**. Write goes first to? **Commit log, then MemTable**.
- Dynamo's data model? **Key-value**. Partitioning technique? **Consistent hashing**. Quorum condition? **R + W > N**. Mechanism for temporarily unavailable replica? **Hinted handoff**. Version tracking? **Vector clocks**. Consistency? **Eventual**.
- Datastore basic unit? **Entity** (grouped by **Kind**); table ≈ Kind, row ≈ Entity, column ≈ Property.
- RDBMS ACID: **A**tomicity, **C**onsistency, **I**solation, **D**urability. Technique best for OLAP? **Column-oriented**. Best for bulk insert? **Heap**. Index that dictates physical order? **Clustered**. Best for range queries among hash/B+ tree? **B+ tree**.
- Match: Row storage–OLTP; Column storage–OLAP; Hash–equality search; Sequential–range queries; Heap–fast insertion.

---

## FINAL REVISION CHECKLIST (priority order)
1. GFS architecture diagram + read/write steps + chunk numerical.
2. BigTable data model (row key, CF, column, timestamp) + architecture + write path.
3. Dynamo: consistent hashing/vnodes, N-R-W numerical, hinted handoff, vector clock.
4. Datastore: Kind/Entity/Property/Key/Ancestor, RDBMS-vs-Datastore & Dynamo-vs-Datastore tables.
5. 3.1: 12 storage techniques (esp. row vs column, indexes, B+ tree), scenario table, ACID with banking case, limitations in cloud.
6. All comparison tables (they are the notes' favourite format).
