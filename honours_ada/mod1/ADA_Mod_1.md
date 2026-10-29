# Advanced Data Analytics — Module 1
## Frequent Itemset Mining & Clustering

> Course: Honours ADA (216H03C701) | Sem VII | K.J. Somaiya School of Engineering
> PYQ Source: LAB CA — Collaborative Analytical Challenge (SET A & SET B)

---

## SECTION 1 — TOPIC MAP

```
Module 1: Frequent Itemset Mining & Clustering
│
├── 1. Introduction to Data Mining
│   ├── What is Data Mining (KDD)?
│   ├── Why Data Mining? (Data explosion problem)
│   ├── Data Mining Functions
│   │   ├── Association / Frequent Pattern Analysis
│   │   ├── Classification
│   │   ├── Cluster Analysis
│   │   └── Others (Outlier, Prediction, Ranking)
│   └── Applications of Data Mining
│
├── 2. KDD Process
│   ├── Database View (7-step pipeline)
│   │   ├── Data Sources
│   │   ├── Data Integration
│   │   ├── Data Cleaning
│   │   ├── Data Warehouse
│   │   ├── Selection (Task-relevant data)
│   │   ├── Data Mining
│   │   └── Pattern Evaluation → Knowledge
│   └── ML/Statistics View (Pre-processing → Mining → Post-processing)
│
├── 3. Market-Basket Model
│   ├── Items, Baskets, Transactions
│   ├── Support (sup = Pr(X ∪ Y))
│   ├── Confidence (conf = Pr(Y | X))
│   ├── Interest / Interestingness
│   ├── Frequent Itemsets (threshold s)
│   ├── Maximal vs. Closed Frequent Itemsets
│   └── Association Rules (X → Y)
│
├── 4. A-Priori Algorithm
│   ├── Downward Closure / Monotonicity Property
│   ├── Two-Pass Approach (Pass 1: singletons, Pass 2: pairs)
│   ├── Candidate Generation (Join + Prune steps)
│   ├── L1, L2, L3 ... Lk generation
│   ├── Counting in Memory
│   │   ├── Triangular Matrix (Approach 1)
│   │   └── Triples [i, j, count] (Approach 2)
│   └── Generating Strong Association Rules from Frequent Itemsets
│
├── 5. Handling Large Datasets in Main Memory
│   ├── PCY (Park-Chen-Yu) Algorithm
│   │   ├── Pass 1: Hash pairs into buckets + item counts
│   │   ├── Between Passes: Compress to Bit Vector
│   │   └── Pass 2: Count only candidate pairs (freq item + freq bucket)
│   ├── Multistage Algorithm
│   │   ├── 3 passes, 2 independent hash functions
│   │   └── Bitmap 1 + Bitmap 2 filtering
│   └── Multihash Algorithm
│       └── Two hash tables in one pass
│
├── 6. Limited-Pass Algorithms
│   ├── Random Sampling
│   ├── SON Algorithm (Savasere-Omiecinski-Navathe)
│   │   ├── Read subsets into memory
│   │   ├── Find local frequent itemsets per chunk
│   │   └── Union = Candidates; Verify globally (2 passes)
│   └── Other Approaches (FP-Growth, Partition-based)
│
├── 7. Counting Frequent Items in a Stream
│   └── DGIM Algorithm (Datar-Gionis-Indyk-Motwani)
│       ├── Sliding window of last N bits
│       ├── Exponentially sized buckets of 1s
│       ├── Merge rule: at most 2 buckets of each size
│       └── Estimate count of 1s = sum of full buckets + half of oldest
│
└── 8. Clustering
    ├── Introduction to Clustering
    │   ├── Unsupervised learning — no labels
    │   ├── Intra-cluster similarity MAX, Inter-cluster similarity MIN
    │   ├── Distance measures (Euclidean, Cosine, Jaccard)
    │   └── Hierarchical vs. Partitioning approaches
    │
    ├── CURE Algorithm (Clustering Using REpresentatives)
    │   ├── Why CURE? (k-means fails on non-spherical shapes)
    │   ├── Step 1: Sample & Partition
    │   ├── Step 2: Pick c well-scattered representative points
    │   ├── Step 3: Shrink representatives toward centroid by α
    │   ├── Step 4: Hierarchical merging (min distance between reps)
    │   └── Step 5: Assign remaining points to nearest rep
    │
    ├── Clustering in Non-Euclidean Spaces [*]
    │   └── Jaccard, Edit distance based similarity
    │
    └── Clustering for Streams and Parallelism
        ├── BFR Algorithm (Bradley-Fayyad-Reina)
        │   ├── 3 Sets: Discard Set (DS), Compressed Set (CS), Retained Set (RS)
        │   ├── Summary vectors (N, LS, SS) per cluster
        │   └── Mahalanobis distance for assignment
        └── Parallel Clustering (SON-style distributed approach)
```
> [*] = Limited notes available; supplemented from standard references.

---

## SECTION 2 — TOPIC-WISE QUESTION TYPES TABLE

| Topic | Theory | Numerical | Derivation | Algorithm Trace | Diagram | PYQ Appeared |
|---|---|---|---|---|---|---|
| Data Mining Definition & KDD | Yes | No | No | No | Yes (KDD pipeline diagram) | No |
| Data Mining Functions | Yes | No | No | No | No | No |
| Applications of Data Mining | Yes | No | No | No | No | No |
| Market-Basket Model (Items, Baskets, Support, Confidence) | Yes | Yes (compute support/confidence) | No | No | No | No |
| Association Rules & Interestingness | Yes | Yes | No | No | No | No |
| Maximal vs. Closed Frequent Itemsets | Yes | Yes (identify from table) | No | No | No | No |
| **Apriori Algorithm** | **Yes** | **Yes (full trace)** | **No** | **Yes** | **Yes (flowchart)** | **YES — SET A Q1, SET B Q1** |
| Counting Pairs in Memory (Triangular Matrix/Triples) | Yes | Yes | No | No | No | No |
| **PCY Algorithm** | **Yes** | **Yes (bucket hashing, bit vector)** | **No** | **Yes** | **Yes (memory diagram)** | No (practice numericals) |
| Multistage Algorithm | Yes | Yes | No | Yes | Yes | No |
| Multihash Algorithm | Yes | No | No | No | Yes | No |
| Random Sampling | Yes | No | No | No | No | No |
| SON Algorithm | Yes | No | No | Yes | No | No |
| **DGIM Algorithm** | **Yes** | **Yes (bucket updates, estimate 1s)** | **No** | **Yes** | **No** | **YES — SET A Q2, SET B Q2** |
| **Bloom Filter** | **Yes** | **Yes (hash, false positives)** | **No** | **Yes** | **No** | **YES — SET A Q3, SET B Q3** |
| CURE Algorithm | Yes | Yes (shrink formula) | No | Yes | Yes (workflow diagram) | No |
| BFR Algorithm | Yes | No | No | No | No | No |
| k-Means vs. CURE Comparison | Yes | No | No | No | Yes (comparison table) | No |
| Clustering in Non-Euclidean Spaces [*] | Yes | No | No | No | No | No |
| Parallel Clustering / SON-Distributed | Yes | No | No | No | No | No |

> **Bold** = High priority topic. **YES in PYQ column** = confirmed appeared in Lab CA exam.
> [*] = Limited notes; knowledge supplemented from standard references.
> Note: Bloom Filter and DGIM appear in the Lab CA but correspond to syllabus points under "Counting Frequent Items in a Stream" and Module 2 overlap. They are included here for completeness.

---

## SECTION 3 — TOPIC-BY-TOPIC DETAILED BREAKDOWN

---

### 3.1 Introduction to Data Mining

**What it is:**
Data Mining (also called Knowledge Discovery in Databases — KDD) is the process of extracting interesting, non-trivial, implicit, previously unknown, and potentially useful patterns or knowledge from huge amounts of data.

The key word is *interesting*. A pattern is interesting if it is:
- Non-trivial (not obvious)
- Implicit (hidden, not directly visible)
- Previously unknown
- Potentially useful for some decision

**Why it matters:**
Data grows from terabytes to petabytes. We are "drowning in data but starving for knowledge." Data mining automates the discovery of useful patterns.

**Data Mining Functions (what it can do):**
| Function | Description | Example |
|---|---|---|
| Association Analysis | Find items that co-occur | Diaper → Beer |
| Classification | Predict a class label | Fraud detection |
| Cluster Analysis | Group similar data | Customer segments |
| Outlier Detection | Find anomalies | Credit card fraud |
| Prediction | Forecast values | Stock prices |

**How to answer "What is Data Mining?" in an exam (Short Note):**

> Data Mining is the extraction of interesting patterns from large datasets using computational techniques. It is a step in the KDD process that involves applying algorithms (association rules, clustering, classification) on preprocessed data to discover hidden patterns. Applications include market basket analysis, fraud detection, recommendation systems, and web mining.

---

### 3.2 KDD Process

The KDD (Knowledge Discovery in Databases) process is the complete end-to-end pipeline from raw data to actionable knowledge.

**The 7 Steps (Database View):**

```
Raw Data Sources
      ↓
Data Integration   ← Combine from multiple sources
      ↓
Data Cleaning      ← Remove noise, inconsistencies
      ↓
Data Warehouse     ← Store clean, integrated data
      ↓
Selection          ← Extract task-relevant subset
      ↓
Data Mining        ← Apply algorithms (THE core step)
      ↓
Pattern Evaluation ← Filter trivial/uninteresting patterns
      ↓
Knowledge
```

**ML/Statistics View (3 phases):**
- **Pre-processing**: Integration, normalization, feature selection, dimensionality reduction
- **Data Mining**: Pattern discovery, classification, clustering, outlier analysis
- **Post-processing**: Pattern evaluation, selection, interpretation, visualization

**How to answer a "KDD diagram" question:**

Draw the staircase diagram showing the 7 steps. Label each step. Mention that Data Mining is the core step but KDD is the complete process. Use the analogy: KDD is the full gold mining operation; Data Mining is just the sifting.

---

### 3.3 Market-Basket Model

**The Setup:**
- A store sells items (I = {i₁, i₂, ..., iₘ})
- Each customer visit = one **basket** (transaction t ⊆ I)
- The database T = {t₁, t₂, ..., tₙ} = all transactions
- Goal: Find items that are bought together frequently

**Key Definitions:**

| Term | Formula | Meaning |
|---|---|---|
| Support (absolute) | count(X ∪ Y) | Number of baskets containing both X and Y |
| Support (relative) | count(X ∪ Y) / n | Fraction of baskets containing X ∪ Y |
| Confidence | count(X ∪ Y) / count(X) | Given X is bought, probability Y is also bought |
| Interestingness | conf(I → j) − Pr[j] | How much more likely is j given I, vs. randomly |

**Association Rule:** Written as X → Y
- Example: {Diaper, Milk} → {Beer} [support = 60%, confidence = 75%]
- This means: In 60% of all baskets, diaper + milk + beer appear together; and 75% of baskets that have diaper + milk also have beer.

**Frequent Itemset:** An itemset X is *frequent* if support(X) ≥ minsup (the threshold s).

**The Downward Closure Property (Monotonicity):**
> If an itemset X is frequent, then ALL subsets of X are also frequent.
> Contrapositive: If any subset of X is infrequent, X cannot be frequent → PRUNE X.

This property is the backbone of Apriori.

**Maximal vs. Closed Frequent Itemsets:**
- **Maximal**: Frequent, and no proper superset is frequent. (Most compact representation)
- **Closed**: Frequent, and no proper superset has the same support count. (Lossless compression)

**Example:**
```
Support threshold = 3
Itemset    Support    Maximal?    Closed?
A          4          No          No  (superset AB is also frequent)
B          5          No          Yes (only superset ABC has count 2 < 3)
AB         4          Yes         Yes
BC         3          Yes         Yes
ABC        2          No          Yes
```

---

### 3.4 Apriori Algorithm

**[HIGHEST PRIORITY — APPEARED IN BOTH SET A AND SET B]**

**Core Idea:** Use the Downward Closure property to avoid counting itemsets whose subsets are already infrequent. Instead of checking all 2^n possible itemsets, grow candidates level by level.

**Algorithm Steps:**

```
1. Scan DB → count individual items → form L1 (frequent 1-itemsets)
2. From Lk, generate Ck+1 (candidate (k+1)-itemsets):
   a. JOIN step: self-join Lk with itself (items sharing first k-1 items)
   b. PRUNE step: remove any candidate whose k-subset is not in Lk
3. Scan DB → count candidates in Ck+1
4. Lk+1 = candidates in Ck+1 with count ≥ minsup
5. Repeat until Ck+1 is empty
```

**Flowchart (draw this in exam):**
```
[ItemSets] → Generate K-Itemset Candidates (Join Step)
                         ↓
              Check Support (Pruning)
                         ↓
              [Frequent Items]
                         ↓
         Set of K-1 frequent itemsets is ∅? → YES → Stop
                    ↓ NO
             (loop back)
```

**Worked Example (Exam-Style):**

Transactions (minsup = 3, minconf = 75%):
| TID | Items |
|---|---|
| 1 | Bread, Milk, Diaper |
| 2 | Bread, Beer, Diaper, Milk |
| 3 | Milk, Diaper, Beer |
| 4 | Bread, Milk |
| 5 | Bread, Diaper, Beer |
| 6 | Milk, Diaper |

**Pass 1 — Count singletons:**

| Item | Count |
|---|---|
| Bread | 4 |
| Milk | 5 |
| Diaper | 5 |
| Beer | 3 |

L1 = {Bread, Milk, Diaper, Beer} (all ≥ 3)

**Pass 2 — Generate C2 (all pairs of L1), count them:**

| Pair | Count |
|---|---|
| {Bread, Milk} | 3 |
| {Bread, Diaper} | 3 |
| {Bread, Beer} | 2 |
| {Milk, Diaper} | 4 |
| {Milk, Beer} | 2 |
| {Diaper, Beer} | 3 |

L2 = {{Bread, Milk}, {Bread, Diaper}, {Milk, Diaper}, {Diaper, Beer}} (count ≥ 3)

**Pass 3 — Generate C3 from L2 (join + prune):**
- Join: {Bread, Milk, Diaper} — check all 2-subsets: {Bread,Milk}✓, {Bread,Diaper}✓, {Milk,Diaper}✓ → Keep
- Other possible: {Bread, Diaper, Beer} → subset {Bread, Beer} ∉ L2 → PRUNE

C3 = {{Bread, Milk, Diaper}}

Count: {Bread, Milk, Diaper} appears in T1, T2, T4 → count = 3 ≥ 3

L3 = {{Bread, Milk, Diaper}}

**Strong Association Rules from L3:**
- Support = 3/6 = 50%
- For rule A → B: conf = count(A ∪ B) / count(A)
  - {Bread, Milk} → Diaper: conf = 3/3 = 100% ✓
  - {Bread, Diaper} → Milk: conf = 3/3 = 100% ✓
  - {Milk, Diaper} → Bread: conf = 3/4 = 75% ✓

All three rules meet minconf = 75% → 3 strong association rules.

**Memory Concerns:**
- Apriori requires k passes over the database (one per size level)
- Main memory bottleneck: storing pair counts for Pass 2
  - Triangular Matrix: 4 bytes per pair, n(n-1)/2 entries = 2n² bytes total
  - Triples [i, j, count]: 12 bytes per existing pair — better if < 1/3 of pairs occur

---

### 3.5 PCY Algorithm (Park-Chen-Yu)

**The Problem with Apriori Pass 1:**
In Pass 1 of Apriori, only item counts are stored in memory. Most memory sits idle. PCY uses this idle memory to build a hash table that can prune more pairs in Pass 2.

**PCY Pass 1 (Enhanced):**
```
FOR each basket:
    FOR each item: count[item]++          ← same as Apriori
    FOR each PAIR of items:
        bucket = h(item_i, item_j)
        bucket_count[bucket]++            ← NEW: hash the pair
```

**Between Passes:**
Replace the bucket count array with a **Bit Vector**:
- Bit = 1 if bucket_count[bucket] ≥ minsup (frequent bucket)
- Bit = 0 otherwise
- This uses 1/32 the memory of the integer counts

**PCY Pass 2:**
A pair {i, j} is a candidate ONLY IF:
1. Both i AND j are frequent (in L1)
2. The pair {i, j} hashes to a bucket whose bit = 1 (frequent bucket)

**Key Insight:**
A bucket being frequent does NOT mean the pair is frequent (false positives due to hash collisions). But if a bucket is infrequent, NO pair hashing to that bucket can be frequent → those pairs are eliminated.

**Memory Layout:**
```
PASS 1                          PASS 2
┌────────────────┐              ┌────────────────┐
│  Item Counts   │              │ Frequent Items │
├────────────────┤              ├────────────────┤
│                │              │    Bitmap      │
│  Hash Table    │  ──shrink──► │                │
│  for Pairs     │              │ Counts of      │
│                │              │ Candidate Pairs│
└────────────────┘              └────────────────┘
```

**PCY Numerical — Step by Step:**

Given: Transactions with items {a, b, c, d, e}, s = 2, hash function h(x, y) = (val(x) + val(y)) mod 5

1. **Pass 1:** Count all items. Compute bucket counts by hashing every pair.
2. **Bit Vector:** Mark bucket[i] = 1 if count ≥ s, else 0.
3. **C2:** Include pair {i,j} only if both are in L1 AND h(i,j) bucket has bit = 1.
4. **Pass 2:** Count candidate pairs, find L2.

**False Positives:**
A pair can pass the bit vector check even though it is not frequent, because multiple pairs hash to the same bucket and their combined count crosses the threshold. This is a false positive — it gets counted in Pass 2 but is then eliminated.

---

### 3.6 Multistage Algorithm

**Goal:** Reduce candidates further than PCY using an additional pass.

**Idea:** After PCY's Pass 1, do a middle pass where you re-hash ONLY the pairs that passed PCY's bit vector (i.e., use a second, independent hash function), creating a second bit vector. In Pass 3, a pair is a candidate only if it passes BOTH bit vectors.

```
Pass 1: Count items + Hash all pairs → Bitmap 1
Pass 2: Re-hash only PCY-qualifying pairs → Bitmap 2
Pass 3: Count pairs that qualify under Bitmap 1 AND Bitmap 2
```

**Rules:**
- The two hash functions MUST be independent
- Both bitmaps must be checked in Pass 3 — you can't drop one
- Cost: 3 passes vs. 2 for PCY; benefit: far fewer candidates

---

### 3.7 Multihash Algorithm

**Goal:** Similar benefit to Multistage but in only 2 passes.

**Idea:** In Pass 1, use TWO independent hash tables simultaneously. Each uses half the memory of the single PCY table. After Pass 1, shrink both to bit vectors.

In Pass 2, a pair is a candidate only if it passes BOTH bit vectors.

**Risk:** Fewer buckets per table → higher average count → more buckets appear frequent → less pruning. Works well only if pair distribution is sparse enough.

---

### 3.8 SON Algorithm (Limited-Pass)

**Goal:** Find all frequent itemsets in at most 2 passes over the data.

**Key Theorem:** An itemset cannot be frequent in the full database D unless it is frequent in at least one partition of D.

**Algorithm:**
```
Pass 1: Divide DB into p memory-sized chunks
        For each chunk: find locally frequent itemsets (local_minsup = s/p × chunk_size)
        Union of all local frequent itemsets = CANDIDATES

Pass 2: Scan full DB once
        Count all candidates globally
        Keep those with global count ≥ s → TRUE FREQUENT ITEMSETS
```

**No false negatives** — any globally frequent itemset must be locally frequent in at least one partition, so it will appear as a candidate.

**Distributed Version:** SON maps naturally to MapReduce:
- Map: Each node finds local frequent itemsets
- Reduce: Aggregate candidate counts globally

---

### 3.9 DGIM Algorithm (Counting Frequent Items in a Stream)

**Problem:** A stream of bits (0s and 1s) arrives. We maintain a sliding window of the last N bits. At any time, estimate the count of 1s in the last k positions (k ≤ N), using only O(log²N) memory.

**DGIM Key Idea:** Maintain a summary of "buckets," where each bucket represents a run of 1s. Each bucket has:
- A **timestamp** (the position of its most recent 1)
- A **size** (always a power of 2: 1, 2, 4, 8, ...)

**DGIM Rules:**
1. At most 2 buckets of each size exist at any time
2. Bucket sizes are non-decreasing from newest to oldest
3. When a new bit = 1 arrives: create a bucket of size 1 at the current timestamp. If there are now 3 buckets of size 1, merge the two oldest into one bucket of size 2. Cascade merges upward as needed.
4. Discard buckets whose timestamps fall outside the window (timestamp < current − N + 1)

**Estimation:** To count 1s in the last k positions:
- Find all buckets entirely within the window of k positions
- For the oldest bucket that partially falls in the window: add **half** its size
- Sum = estimate of 1s

**Error Bound:** The estimate has error at most 50% of the oldest bucket's count, which is ≤ 50% of the true count.

**Example: [From SET A PYQ]**

Initial state at timestamp 100: `(100,1), (98,1), (95,2), (91,2), (86,4), (78,4), (69,8)`
Window size = 32 (timestamps 69 to 100)

Timestamp 101, bit = 1:
- Create (101, 1)
- Three size-1 buckets: (101,1), (100,1), (98,1) → merge two oldest: (100,1)+(98,1) → (100,2)
- Three size-2 buckets: (100,2), (95,2), (91,2) → merge: (95,2)+(91,2) → (95,4)
- Three size-4 buckets: (95,4), (86,4), (78,4) → merge: (86,4)+(78,4) → (86,8)
- Window now 70–101; bucket (69,8) is outside → remove
- Result: `(101,1), (100,2), (95,4), (86,8)`

Timestamp 102, bit = 1: Create (102,1). Only 2 size-1 buckets → no merge.
`(102,1), (101,1), (100,2), (95,4), (86,8)`

Timestamp 103, bit = 0: No new bucket.
`(102,1), (101,1), (100,2), (95,4), (86,8)`

Timestamp 104, bit = 1: Create (104,1). Three size-1: (104,1),(102,1),(101,1) → merge: (103,2).
`(104,1), (103,2), (100,2), (95,4), (86,8)`

Timestamp 105, bit = 1: Create (105,1). Two size-1 → no merge.
**Final: `(105,1), (104,1), (103,2), (100,2), (95,4), (86,8)`**

Estimate for last 20 timestamps (timestamps 86–105):
All buckets fit within this range. Oldest included: (86,8)
Estimate = 1 + 1 + 2 + 2 + 4 + 8/2 = **14**

---

### 3.10 Bloom Filter

**Problem:** Given a set S of known items, for any query item x, answer "Is x in S?" quickly with minimal memory. Allow some false positives but zero false negatives.

**Structure:** A bit array of m bits, initialized to all 0s. Use k independent hash functions h₁, h₂, ..., hₖ.

**Insertion of element x:**
For each hash function hᵢ, set bit[hᵢ(x)] = 1.

**Query for element x:**
If ALL k positions h₁(x), h₂(x), ..., hₖ(x) are 1 → answer "possibly in S"
If ANY position is 0 → answer "definitely NOT in S"

**False Positive:** All positions for x happen to be 1 (set by other elements), even though x was never inserted.

**False Negative:** Impossible. If x was inserted, all its bits were set to 1 and can never go back to 0.

**Example: [From SET A PYQ]**

Inserting 12 (using two hash functions, results: positions 2 and 7)
Inserting 25 (positions 5 and 6)
Inserting 37 (positions 7 and 2)

Query 15 (hashes to positions 5 and 6): Both are 1 → "possibly present" → FALSE POSITIVE (15 was not inserted)
Query 14 (hashes to positions 4 and 3): Position 3 or 4 = 0 → "definitely absent" ✓

---

### 3.11 Clustering — Introduction

**What is Clustering?**
Clustering is the task of partitioning n data points into k groups (clusters) such that:
- Points within a cluster are **similar** to each other (high intra-cluster similarity)
- Points in different clusters are **dissimilar** (low inter-cluster similarity)

It is **unsupervised** learning — no class labels are known in advance.

**Distance Measures:**
| Measure | Used for | Formula |
|---|---|---|
| Euclidean | Numeric/spatial data | √Σ(xᵢ - yᵢ)² |
| Cosine | Text/vector data | 1 - (x·y)/(‖x‖‖y‖) |
| Jaccard | Set data | 1 - \|A∩B\|/\|A∪B\| |

**Two Major Paradigms:**
- **Hierarchical (Agglomerative):** Start with each point as its own cluster. Repeatedly merge the two closest clusters. Result: a dendrogram.
- **Partitioning (k-Means):** Assign k initial centroids. Assign each point to nearest centroid. Recompute centroids. Repeat until stable.

**Problem with k-Means:**
1. Assumes spherical clusters (fails on curved, elongated, or concentric shapes)
2. Highly sensitive to outliers (one outlier pulls the centroid off-center)
3. Must specify k in advance

---

### 3.12 CURE Algorithm (Clustering Using REpresentatives)

**Why CURE Exists:**
Standard k-means uses one centroid per cluster. This fails for non-convex shapes like bananas, crescents, or S-curves. Single-link hierarchical clustering captures shape but has the "chaining effect" and is O(n²) or O(n³).

CURE is the middle ground.

**Core Idea:**
- Represent each cluster by **c well-scattered representative points** (not a single centroid)
- **Shrink** those representative points toward the cluster centroid by a factor α (typically 0.2–0.7)
- Shrinking reduces outlier effects while preserving shape

**Shrinking Formula:**
```
New Point = Old Point + α × (Centroid − Old Point)
r' = r + α(μ - r)
```

**CURE Architecture Workflow:**
```
Data → Draw Random Sample → Partition Sample → Partially Cluster Partitions
                                                          ↓
Clusters ← Label Data on Disk ← Cluster Partial Clusters ← Eliminate Outliers
```

**CURE Step-by-Step:**

**Step 1: Sampling & Partitioning**
Draw a random sample from the dataset (e.g., 2,000 from 1,000,000 points). If still too large, divide into p sub-partitions and partially cluster each partition into initial mini-clusters.

**Step 2: Select c Representative Points**
For each cluster:
1. Pick p₁ = point furthest from the centroid
2. Pick p₂ = point furthest from p₁
3. Pick p₃ = point furthest from both p₁ and p₂
4. Continue until c scattered points are selected

**Step 3: Shrink Representatives**
Move each representative toward the centroid:
`r' = r + α × (centroid − r)`

**Step 4: Hierarchical Merging**
Distance between two clusters = minimum distance between any representative of cluster A and any representative of cluster B. Merge the closest pair of clusters. Repeat until k clusters remain.

**Step 5: Assign Remaining Points**
Stream through remaining (unsampled) data points. Assign each point to the cluster whose shrunk representative point is nearest.

**Worked Numerical:**

Cluster C₁ has points: P₁=(1,1), P₂=(1,5), P₃=(5,1), P₄=(5,5). c=2 reps, α=0.5.

**Find centroid:**
μ₁ = ((1+1+5+5)/4, (1+5+1+5)/4) = (3, 3)

**Select r₁ (furthest from centroid):**
All 4 points are equidistant from (3,3): d = √((1-3)² + (1-3)²) = √8 ≈ 2.83
Select r₁ = P₁ = (1,1)

**Select r₂ (furthest from r₁):**
d(P₂, r₁) = √(0 + 16) = 4.0
d(P₃, r₁) = √(16 + 0) = 4.0
d(P₄, r₁) = √(16 + 16) = √32 ≈ 5.66 ← maximum
Select r₂ = P₄ = (5,5)

**Shrink with α=0.5:**
r₁' = (1,1) + 0.5×((3,3)−(1,1)) = (1,1) + 0.5×(2,2) = (1,1) + (1,1) = **(2, 2)**
r₂' = (5,5) + 0.5×((3,3)−(5,5)) = (5,5) + 0.5×(−2,−2) = (5,5) + (−1,−1) = **(4, 4)**

Shrunk representatives for C₁: S₁ = {(2,2), (4,4)}

**Distance to another cluster C₂** with S₂ = {(10,2), (10,4)}:
d((2,2),(10,2)) = 8.0
d((2,2),(10,4)) = √(68) ≈ 8.25
d((4,4),(10,2)) = √(40) ≈ 6.32
d((4,4),(10,4)) = √36 = **6.0** ← minimum

d(C₁, C₂) = **6.0**

---

### 3.13 BFR Algorithm (Clustering for Large Datasets)

**What it is:**
BFR (Bradley-Fayyad-Reina) is a variant of k-means designed for massive datasets that cannot fit in main memory. It reads data in chunks (a single pass) and stores only compact mathematical summaries.

**Core Assumptions:**
1. Clusters are normally distributed in Euclidean space
2. Cluster axes are aligned with coordinate axes (diagonal covariance)

**Three Sets in Memory:**
| Set | What it holds | How stored |
|---|---|---|
| **Discard Set (DS)** | Points confidently assigned to a main cluster | Cluster Feature Vector (N, LS, SS) only |
| **Compressed Set (CS)** | Mini-clusters too small to join DS yet | Feature Vector (N, LS, SS) per mini-cluster |
| **Retained Set (RS)** | True outliers with no cluster | Raw coordinates |

**Cluster Feature Vector:**
- N: number of points
- LS: linear sum vector (Σxᵢ for each dimension)
- SS: squared sum vector (Σxᵢ² for each dimension)
- Mean: μᵢ = LSᵢ/N
- Variance: σᵢ² = SSᵢ/N − (LSᵢ/N)²

**Distance Metric: Mahalanobis Distance**
```
d(x, μ) = √Σ((xᵢ - μᵢ) / σᵢ)²
```
This normalizes distance by each dimension's standard deviation, making ellipsoidal clusters work correctly.

**BFR Processing:**
1. Load initial chunk → run k-means → form initial DS with summary vectors
2. For each subsequent chunk, for each point x:
   - If Mahalanobis distance to a DS cluster < threshold (e.g., 3σ) → assign to DS, update (N, LS, SS)
   - Else: try grouping with RS. If tight group forms → promote to CS
   - True isolates → stay in RS
3. After all chunks: merge CS into nearest DS cluster

---

### 3.14 Clustering in Non-Euclidean Spaces [*SELF-CONSTRUCTED]

> Note: This topic is mentioned in the syllabus but has minimal dedicated notes. The following is from standard textbook knowledge.

When data points are not in Euclidean space (e.g., documents, biological sequences, graphs), standard centroid-based algorithms fail because the mean of two items is undefined.

**Approaches:**
- **k-Medoids (PAM):** Instead of a centroid, use an actual data point as the cluster representative (the "medoid"). Works with any distance function.
- **CURE in non-Euclidean space:** CURE uses representative points (actual data points), so it works with any distance measure. The shrinking step is modified: instead of arithmetic shrinking, points are moved toward the medoid.
- **Distance-based measures:** Use Jaccard (for sets), Cosine (for vectors), Edit distance (for strings), or graph-based distances.

**Key challenge:** The triangle inequality must hold for hierarchical merging to be meaningful.

---

### 3.15 Clustering for Streams and Parallelism

**Stream Clustering:**
Data arrives continuously and cannot be stored. Each point must be processed once and either assigned to a cluster or discarded.

Approaches:
- **CURE-style streaming:** Maintain cluster representatives in memory; assign new stream point to nearest representative.
- **BFR-style streaming:** Maintain (N, LS, SS) summaries and use Mahalanobis distance for streaming assignment.

**Parallel Clustering (SON approach applied to clustering):**
- Distribute data across p nodes
- Each node clusters its local partition independently
- Gather all local cluster representatives
- Run a global clustering step on the collected representatives
- Assign original data points to the nearest global cluster

This is the same idea as SON for frequent itemsets: solve locally, combine globally.

---

## SECTION 4 — PYQ SOLUTIONS

> Only questions clearly related to Module 1 topics are solved here.
> Questions from other modules (TF-IDF, Naive Bayes, Recommendation Systems) that appeared in the Lab CA are not included, as they belong to Modules 4/5.
> DGIM and Bloom Filter solutions are included as they appear under "Stream Mining" in Module 1's teaching plan.

---

### PYQ SET A — Q1: Apriori Algorithm

**Question (paraphrased):** Transactions are given (containing Bread, Milk, Diaper, Beer items). Min support count = 3. Run Apriori. State the frequent itemsets and derive strong association rules.

**Transactions (from SET A context):**
| TID | Items |
|---|---|
| 1 | Bread, Milk, Diaper |
| 2 | Bread, Beer, Diaper, Milk |
| 3 | Milk, Diaper, Beer |
| 4 | Bread, Milk |
| 5 | Bread, Diaper, Beer |
| 6 | Milk, Diaper |

**Step 1: Candidate 1-itemsets with minsup = 3**

| Item | Count |
|---|---|
| Bread | 4 |
| Milk | 5 |
| Diaper | 5 |
| Beer | 3 |

**L1 = {Bread, Milk, Diaper, Beer}** (all items ≥ 3)

**Step 2: Generate C2 (all pairs from L1), count in DB**

| Pair | Count |
|---|---|
| {Bread, Milk} | 3 |
| {Bread, Diaper} | 3 |
| {Bread, Beer} | 2 |
| {Milk, Diaper} | 4 |
| {Milk, Beer} | 2 |
| {Diaper, Beer} | 3 |

**L2 = {{Bread, Milk}, {Bread, Diaper}, {Milk, Diaper}, {Diaper, Beer}}**

**Step 3: Generate C3 from L2 using join + prune**

Join L2 with itself (sharing first item):
- {Bread, Milk, Diaper} — subsets: {Bread,Milk}✓, {Bread,Diaper}✓, {Milk,Diaper}✓ → **Keep**
- {Bread, Diaper, Beer} — subset {Bread,Beer} ∉ L2 → **Prune**

C3 = {{Bread, Milk, Diaper}} → count = 3 (T1, T2, T4)

**L3 = {{Bread, Milk, Diaper}}**

**Strong Association Rules (minconf = 75%):**

Support({Bread, Milk, Diaper}) = 3/6 × 100 = **50%**

For each non-empty subset as antecedent:
- {Bread, Milk} → Diaper: conf = 3/3 = **100%** ✓
- {Bread, Diaper} → Milk: conf = 3/3 = **100%** ✓
- {Milk, Diaper} → Bread: conf = 3/4 = **75%** ✓
- {Bread} → {Milk, Diaper}: conf = 3/4 = 75% ✓
- {Milk} → {Bread, Diaper}: conf = 3/5 = 60% (below 75% — may be excluded)
- {Diaper} → {Bread, Milk}: conf = 3/5 = 60% (below 75% — may be excluded)

**Final Answer: 3 (or 6 depending on minconf) strong association rules, all with 50% support.**

---

### PYQ SET B — Q1: Apriori Algorithm

**Question (paraphrased):** Transactions contain Laptop, Mouse, Keyboard, Headphones. minsup = 3, derive frequent itemsets and association rules.

**Solution approach: identical to SET A**

**L1** = {Laptop, Mouse, Keyboard, Headphones} (all frequent)

**L2** = {{Laptop, Mouse}, {Laptop, Keyboard}, {Mouse, Keyboard}, {Keyboard, Headphones}}

**L3** = {{Laptop, Mouse, Keyboard}} (count = 3)

**Strong Rules (support = 50%, confidence = 75%):**
- {Laptop, Mouse} → Keyboard
- {Laptop, Keyboard} → Mouse
- {Mouse, Keyboard} → Laptop

---

### PYQ SET A — Q2: DGIM Algorithm

**Question:** Initial configuration at timestamp 100:
`(100,1), (98,1), (95,2), (91,2), (86,4), (78,4), (69,8)`

Process bits at timestamps 101=1, 102=1, 103=0, 104=1, 105=1.
Estimate 1s in last 20 timestamps.

**Solution:**

**Timestamp 101, bit=1:**
- Create (101,1) → three size-1 buckets → merge (100,1)+(98,1)=(100,2)
- Three size-2 → merge (95,2)+(91,2)=(95,4)
- Three size-4 → merge (86,4)+(78,4)=(86,8)
- Bucket (69,8): window is now 70–101 → **drop (69,8)**
- State: `(101,1), (100,2), (95,4), (86,8)`

**Timestamp 102, bit=1:**
- Create (102,1) → two size-1 → no merge
- State: `(102,1), (101,1), (100,2), (95,4), (86,8)`

**Timestamp 103, bit=0:**
- No new bucket
- State: `(102,1), (101,1), (100,2), (95,4), (86,8)`

**Timestamp 104, bit=1:**
- Create (104,1) → three size-1: (104,1),(102,1),(101,1) → merge two oldest: (102,2)
- State: `(104,1), (102,2), (100,2), (95,4), (86,8)`

**Timestamp 105, bit=1:**
- Create (105,1) → two size-1 → no merge
- **Final: `(105,1), (104,1), (102,2), (100,2), (95,4), (86,8)`**

**Estimate for last 20 timestamps (ts 86 to 105):**
All buckets are within range [86, 105]. Oldest is (86, 8).
Estimate = 1 + 1 + 2 + 2 + 4 + 8/2 = 1 + 1 + 2 + 2 + 4 + 4 = **14**

---

### PYQ SET B — Q2: DGIM Algorithm

**Initial config at timestamp 200:**
`(200,1), (198,1), (195,2), (191,2), (186,4), (178,4), (169,8)`

Process: 201=1, 202=0, 203=1, 204=1, 205=1. Estimate for last 15 timestamps.

**Timestamp 201, bit=1:**
- Create (201,1) → merge cascades: (200,1)+(198,1)=(200,2); (195,2)+(191,2)=(195,4); (186,4)+(178,4)=(186,8)
- Drop (169,8) (outside window 170–201)
- State: `(201,1), (200,2), (195,4), (186,8)`

**Timestamp 202, bit=0:** No change.
State: `(201,1), (200,2), (195,4), (186,8)`

**Timestamp 203, bit=1:** Create (203,1) → two size-1 → no merge.
State: `(203,1), (201,1), (200,2), (195,4), (186,8)`

**Timestamp 204, bit=1:** Create (204,1) → three size-1: merge (203,1)+(201,1)=(203,2).
State: `(204,1), (203,2), (200,2), (195,4), (186,8)`

**Timestamp 205, bit=1:** Create (205,1) → two size-1 → no merge.
**Final: `(205,1), (204,1), (203,2), (200,2), (195,4), (186,8)`**

**Estimate for last 15 timestamps (ts 191–205):**
Buckets within range: (205,1), (204,1), (203,2), (200,2), (195,4). Bucket (186,8) is outside.
Oldest included: (195,4)
Estimate = 1 + 1 + 2 + 2 + 4/2 = 1 + 1 + 2 + 2 + 2 = **8**

---

### PYQ SET A — Q3: Bloom Filter

**Question:** Inserting 12, 25, 37. Hash functions map to specific positions. Test items 15 and 14.

**From the solution:**
- Insert 12 → set bits 2 and 7
- Insert 25 → set bits 5 and 6
- Insert 37 → set bits 7 and 2 (same positions as 12)

**Final bit array:** Positions 2, 5, 6, 7 = 1; rest = 0

**Test 15:** Maps to positions 5 and 6. Both are 1 → "possibly present" → **FALSE POSITIVE** (15 was not inserted)
**Test 14:** Maps to positions 4 and 3. Position 3 or 4 = 0 → **"Definitely absent"** ✓

---

### Practice PCY Numerical [from PCY_and_Apriori_Practice_Numericals.pdf]

**Problem 1: PCY (4 transactions, items a,b,c,d,e, s=2, 5 buckets)**
h(x,y) = (val(x)+val(y)) mod 5; val(a)=1,b=2,c=3,d=4,e=5

**Pass 1 - Item Counts:**
a:3, b:3, c:3, d:2, e:3 → **L1 = {a, b, c, d, e}** (all ≥ 2)

**Bucket Mapping (hash all pairs):**

| Bucket | Pairs Hashed | Total | Bit |
|---|---|---|---|
| 0 | {b,c}(2) + {a,d}(1) | 3 | 1 |
| 1 | {a,e}(2) + {b,d}(1) | 3 | 1 |
| 2 | {b,e}(2) + {c,d}(1) | 3 | 1 |
| 3 | {a,b}(2) + {c,e}(3) | 5 | 1 |
| 4 | {a,c}(2) + {d,e}(1) | 3 | 1 |

Bit Vector = [1,1,1,1,1] → No candidate pairs pruned in this case.

**Pass 2 counts & L2:**
{a,b}:2, {a,c}:2, {a,d}:1, {a,e}:2, {b,c}:2, {b,d}:1, {b,e}:2, {c,d}:1, {c,e}:3, {d,e}:1

**L2 = {{a,b}, {a,c}, {a,e}, {b,c}, {b,e}, {c,e}}**

---

**Problem 3: PCY False Positive Example (s=3, 4 buckets)**
h(x,y) = (val(x)×val(y)) mod 4

| Bucket | Pairs & Counts | Total | Bit |
|---|---|---|---|
| 0 | {a,d}(1)+{b,d}(3)+{c,d}(2) | 6 | 1 |
| 1 | (empty) | 0 | 0 |
| 2 | {a,b}(2)+{b,c}(2) | 4 | 1 |
| 3 | {a,c}(1) | 1 | 0 |

Bit Vector = [1, 0, 1, 0]

**False Positives:** Bucket 2 has total count 4 ≥ 3, so bit = 1. But {a,b} has count 2 < 3 and {b,c} has count 2 < 3. Both pairs hash to bucket 2 due to collision. Both become **false positive candidates** — they enter C2 but are eliminated when counted in Pass 2.

---

### CURE Numerical [from CURE Clustering.pdf — Running Example]

**Points:** A(1,2), B(2,1), C(2,3), D(8,8), E(9,9), F(8,10)
**Parameters:** k=2 clusters, c=2 representative points, α=0.2

**Step 1: Initial Distance Matrix**
Smallest distances: d(A,B) = √2 ≈ 1.41, d(D,E) = 1.41

**Step 2: First Merges**
Merge (A,B) → Cluster AB; Merge (D,E) → Cluster DE

**Step 3: Centroids**
C_AB = ((1+2)/2, (2+1)/2) = (1.5, 1.5)
C_DE = ((8+9)/2, (8+9)/2) = (8.5, 8.5)

**Step 4: Select c=2 Representatives**
Cluster AB: Representatives are A(1,2) and B(2,1) (most scattered points)
Cluster DE: Representatives are D(8,8) and E(9,9)

**Step 5: Shrink with α=0.2**
Cluster AB (centroid = (1.5,1.5)):
- A' = (1,2) + 0.2×[(1.5,1.5)−(1,2)] = (1,2) + 0.2×(0.5,−0.5) = **(1.1, 1.9)**
- B' = (2,1) + 0.2×[(1.5,1.5)−(2,1)] = (2,1) + 0.2×(−0.5,0.5) = **(1.9, 1.1)**

Cluster DE (centroid = (8.5,8.5)):
- D' = (8,8) + 0.2×[(8.5,8.5)−(8,8)] = **(8.1, 8.1)**
- E' = (9,9) + 0.2×[(8.5,8.5)−(9,9)] = **(8.9, 8.9)**

**Step 6: Distance Between AB and DE (using shrunk reps)**
d(A'(1.1,1.9), D'(8.1,8.1)) = 9.90
d(A'(1.1,1.9), E'(8.9,8.9)) = 11.03
d(B'(1.9,1.1), D'(8.1,8.1)) = 8.73
d(B'(1.9,1.1), E'(8.9,8.9)) = 8.73

**Cluster distance = min = 8.73**

**Next merge:** C(2,3) is compared to clusters AB and DE. Nearest AB representative to C:
- d(C, A') = √((2−1.1)² + (3−1.9)²) = √(0.81+1.21) ≈ 1.42 → merge C with AB

**Final clusters: {A,B,C} and {D,E,F}**

---

## APPENDIX: KEY FORMULAS REFERENCE

| Formula | Name | Use |
|---|---|---|
| support = count(X ∪ Y) / n | Support | How often items co-occur |
| confidence = count(X ∪ Y) / count(X) | Confidence | Strength of rule X→Y |
| interest = conf(I→j) − Pr[j] | Interestingness | Is the rule non-trivial? |
| r' = r + α(μ − r) | CURE shrinking | Move rep point toward centroid |
| d(C₁,C₂) = min_{u∈S₁, v∈S₂} d(u,v) | CURE cluster distance | Between-cluster distance |
| d(x,μ) = √Σ((xᵢ−μᵢ)/σᵢ)² | Mahalanobis distance | BFR cluster assignment |
| μᵢ = LSᵢ/N | BFR mean | From summary vectors |
| σᵢ² = SSᵢ/N − (LSᵢ/N)² | BFR variance | From summary vectors |

---

## APPENDIX: ALGORITHM COMPARISON TABLE

| Feature | Apriori | PCY | Multistage | SON | CURE |
|---|---|---|---|---|---|
| Type | Frequent Itemsets | Frequent Itemsets | Frequent Itemsets | Frequent Itemsets | Clustering |
| Passes | k (one per level) | 2 | 3 | 2 | 1 (on sample) |
| Memory trick | None | Hash table + bitmap | Two bitmaps | Partition | Representative points |
| False negatives? | No | No | No | No | No |
| Handles large data? | Struggles | Better than Apriori | Best of hash methods | Yes (distributed) | Yes (sampling) |
| Shape assumption | N/A | N/A | N/A | N/A | Any shape |
| Outlier handling | N/A | N/A | N/A | N/A | Good (α shrinking) |

| Feature | k-Means | CURE | BFR |
|---|---|---|---|
| Shape | Spherical only | Any (curved, elongated) | Ellipsoidal |
| Outlier sensitivity | High | Low (shrinking) | Moderate (RS isolation) |
| Memory | Full dataset needed | Random sample | Chunk-by-chunk (single pass) |
| Distance | Euclidean | Any | Mahalanobis |
| Representation | 1 centroid | c shrunk reps | (N, LS, SS) summary |
| Scale | Small-medium | Large (sample) | Massive (streaming) |
