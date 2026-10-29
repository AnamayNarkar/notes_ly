# Cloud Computing — Module 2: Service Management in Cloud Computing
**Course:** Cloud Computing (LY B.Tech Comp, SVU-KJSSE 2023 syllabus) | **Module 2 = 10 of 45 hrs (~22%)** | **CO2**
**Evaluation (from syllabus PDF):** IA 20 + ISE 30 + **ESE 50** = 100

---

# 🚨 0. CONTEXT CARRY-OVER — UTMOST IMPORTANT (keep in every chat summary, never drop)

> **If this conversation is summarised/compacted, the block below MUST be preserved verbatim.**

**TASK:** Help the user prepare **Module 2 only** of Cloud Computing. Single deliverable = this one file `Cloud_Computing_Mod_2.md` (no separate artifacts). Images must be read with multimodal vision, **no OCR scripts**.

**Syllabus (Module 2 – Service Management in Cloud Computing, 10 hrs, CO2):**
- **2.1** SERVICE LEVEL AGREEMENT (SLA), SLA Contents, Types of SLA, Service Level Objectives (SLOs), SLA Requirements, Key Performance Indicators (KPIs), Metrics for Monitoring and Auditing, SLA Requirements w.r.t. Cloud Delivery Models, Examples of Cloud SLAs, Limitations of SLA, Numericals on Service Availability, SLA Violation and Penalty Computation
- **2.2** Cloud Economics: Economic Viewpoint, Utility Pricing in Detail, Value of on-Demand Services, Penalty Costs for Exponential Demand

**Required deliverables (all inside this file):**
1. Topic map (tree, in a code block) → §1
2. Topic-wise question-type table with special indicator for PYQ-appeared types → §2
3. Topic-by-topic detailed explanation, how to present it in exam (short note / diagram / table), then numericals → §3
4. PYQ solutions grouped by topic, solved exam-style, only Module-2-related PYQs → §4
5. Anything in syllabus but missing from notes/PYQ → self-made, **clearly marked 🟡**

**Files analysed (all fully read):**
- `mod2/Module 2.1.pptx` (202 slides – SLA), `mod2/Module 2.2pptx.pptx` (69 slides – Cloud Economics), `mod2/SLA_in_Cloud_Computing_20_Slides_Buyya_Aligned.pptx` (20 slides – SLA/SLI/SLO/lifecycle), `mod2/The 5 Phases of the Cloud SLA Lifecycle.pptx` (13 slides)
- `../question_papers_all_time/`: `cloud computing.PDF` (ESE Jan–Apr 2025, Minors), 7 screenshots (ESE Dec 2022; ESE Nov–Dec 2021; ESE May–Jun 2021), `LY-SVU2023-Syllabus.pdf` (161 pp)

**🔑 KEY PYQ FINDING (do not forget):** After reading every PYQ, **there is NO direct Module 2 question (SLA / SLO / KPI / availability numerical / penalty / cloud economics / utility pricing) in any available paper.** Module 2 appears to be new in the SVU 2023 syllabus (CO2), while the papers are older Mod-1/Aneka/virtualization-heavy papers. Only **6 adjacent questions** (utility computing, advantage of cloud, availability MCQ, scalability vs elasticity, demand-vs-event provisioning, Spot Cloud) are related — solved in §4 and tagged **◐ (adjacent)**. Everything else for Module 2 is based on notes (📘) or my prediction (🟡).

**Legend used everywhere:**
| Mark | Meaning |
|---|---|
| 📘 | Comes from the supplied notes/slides |
| ★ | Question *type* appeared in an official PYQ for this exact topic (**none exist for Mod 2**) |
| ◐ | Adjacent PYQ (related topic, not exact) |
| 🟡 | **Self-made / predicted** – NOT from notes or official PYQ |

**Errors/quirks spotted in the notes (fixed here):**
1. Slide 201 (Problem 5) writes `80,000×100/25 = ₹20,000` — the operation is written upside down. Correct: `80,000 × 25/100 = ₹20,000`.
2. Slide 140 (IaaS/PaaS/SaaS comparison table) is garbled in the PPT — reconstructed properly in §3.9.
3. Slide 83 calls "measured monthly uptime 99.97%" a *KPI*; the Buyya-style deck calls the same thing an *SLI*. Both are accepted; write SLI/KPI as "measured value".
4. Slide 66 (Mod 2.2): final penalty line is the *integral result* (cumulative), and the "rate" form is `k₁eᵗ` — explained in §3.17.

---

# 1. TOPIC MAP

```
MODULE 2 : SERVICE MANAGEMENT IN CLOUD COMPUTING  (10 hrs, CO2)
│
├── 2.1  SERVICE LEVEL AGREEMENT (SLA)
│   │
│   ├── T1  SLA – Introduction
│   │     ├── Definition, Need / Why required
│   │     ├── Objectives, Importance
│   │     ├── Characteristics of a good SLA (clear, measurable, realistic, flexible, enforceable)
│   │     ├── Parties involved (Provider, Customer) + responsibilities
│   │     ├── Basic structure (diagram)
│   │     ├── Benefits / Advantages (6)  ── quality, responsibilities, conflicts, confidence, measurable, monitoring
│   │     └── SLA Life Cycle (T2)
│   │
│   ├── T2  SLA Life Cycle
│   │     ├── 6-stage: Requirements → Negotiation → Agreement → Delivery/Implementation → Monitoring → Review (→ Renewal)
│   │     └── 5-phase (Buyya): Definition → Publishing & Discovery → Negotiation → Operation (Monitoring + Enforcement) → De-commissioning
│   │
│   ├── T3  SLA Contents (15 clauses)
│   │     ├── Service description, Scope, Availability, Performance metrics
│   │     ├── Roles & responsibilities, SLOs, Monitoring & reporting
│   │     ├── Security & compliance, Backup & DR, Incident & problem mgmt
│   │     └── Change mgmt, Violations & penalties, Exclusions, Review & revision, Termination
│   │
│   ├── T4  Types of SLA
│   │     ├── Customer-based SLA  (one customer, many services)
│   │     ├── Service-based SLA   (one service, all customers)
│   │     └── Multi-level SLA     (Corporate → Customer → Service)
│   │
│   ├── T5  Service Level Objectives (SLOs)
│   │     ├── Definition, characteristics, examples
│   │     ├── SLA vs SLO
│   │     └── SLA vs SLI vs SLO vs KPI
│   │
│   ├── T6  SLA Requirements
│   │     ├── General (availability, reliability, scalability, performance, security, backup, DR, support, monitoring)
│   │     └── Functional vs Non-functional requirements
│   │
│   ├── T7  Key Performance Indicators (KPIs)
│   │     ├── Definition, importance, SMART characteristics
│   │     └── Metrics: Availability, Response time, Latency, Throughput, Error rate,
│   │                  Resource utilisation, Reliability (MTBF), Scalability, Bandwidth, Customer satisfaction
│   │
│   ├── T8  Metrics for Monitoring and Auditing
│   │     ├── Monitoring: objectives, 4 types (Infra / Application / Network / Security), process, tools
│   │     └── Auditing: objectives, 4 types (Internal / External / Security / Compliance), audit logs
│   │
│   ├── T9  SLA Requirements w.r.t. Cloud Delivery Models
│   │     ├── IaaS (VM/storage/network availability, RTO/RPO …)
│   │     ├── PaaS (platform/DB/API availability, runtime, auto-scaling …)
│   │     ├── SaaS (app availability, authentication, privacy, support …)
│   │     └── Comparison table + Shared Responsibility Model
│   │
│   ├── T10 Examples of Cloud SLAs
│   │     ├── AWS (EC2 99.99%, credit table), Azure (up to 99.99%), Google Cloud (99.95%+)
│   │     └── Comparison table
│   │
│   ├── T11 Limitations of SLA
│   │     ├── (7 limitations)  difficult to measure, complex, credits not cash, exclusions,
│   │     │                     downtime still allowed, monitoring challenges, vendor dependency
│   │     └── (5 disadvantages in detail) complex to prepare, difficult to monitor,
│   │                          may not cover all situations, negotiation takes time, penalties don't cover losses
│   │
│   ├── T12 NUMERICALS ON SERVICE AVAILABILITY
│   │     ├── Availability % formula, alternate (uptime) formula
│   │     ├── Downtime from SLA availability  (derived formula)
│   │     ├── "Number of nines" tables (year / month)
│   │     ├── Factors affecting + techniques to improve availability
│   │     └── 🟡 MTBF/MTTR, series/parallel, planned-maintenance exclusion
│   │
│   └── T13 SLA VIOLATION & PENALTY COMPUTATION
│         ├── What is a violation, causes (6), detection methods (5) + detection flowchart
│         ├── Penalty models: Service credit | Refund | Free extension | Discount on future bill
│         ├── Formula: Penalty = Monthly cost × Penalty% / 100
│         ├── Tiered (slab) penalties
│         └── Best practices to avoid violations
│
└── 2.2  CLOUD ECONOMICS
    │
    ├── T14 Economic Viewpoint
    │     ├── Why cloud economics, traditional DC vs cloud example
    │     ├── 6 objectives: ↓infra cost | CapEx→OpEx | ↑utilisation | agility & scalability | ↓complexity | optimise spending
    │     └── Factors considered: initial investment, maintenance, scalability, utilisation, risk
    │
    ├── T15 Utility Pricing in Detail
    │     ├── Definition (PAYG / usage-based), why "utility", how it works, architecture diagram
    │     ├── Resources charged & units
    │     ├── 5 characteristics: PAYG, no upfront, flexible, measured service, elasticity
    │     ├── Advantages (7) / Disadvantages (5)
    │     └── Pricing in AWS / Azure / GCP
    │
    ├── T16 Value of On-Demand Services
    │     ├── Definition (on-demand self-service)
    │     ├── 10 advantages (cost savings, PAYG, elastic scalability, time-to-market, utilisation,
    │     │                  agility, availability, global access, less IT mgmt, innovation)
    │     ├── Real-life example (video streaming)
    │     └── Limits / what goes wrong if demand outgrows provisioning
    │
    └── T17 Penalty Costs for Exponential Demand
          ├── Penalty cost definition (demand ≠ resources)
          ├── Formula  Penalty ∝ ∫|D(t) − R(t)| dt
          ├── Derivation with D(t)=eᵗ, R(t)=e^(t−tp)  →  Penalty ∝ c·k₁·eᵗ
          └── Causes: viral events, flash sales, ticket booking, Black Friday …
```

---

# 2. TOPIC-WISE QUESTION TYPES

**How to read:** columns = the *kind* of question that can be asked. Cells show the evidence.

| Mark | Meaning |
|---|---|
| ★ | Appeared in an official PYQ **for this exact topic** — **NONE exist for Module 2** (so no ★ appears below) |
| ◐ | Appeared in an adjacent PYQ (solved in §4) |
| 📘 | Notes contain this type of content (explicit example/exercise/exam-question slide) |
| 🟡 | Not in notes/PYQ — my prediction |
| – | Unlikely |

SN = short note (5M) · LN = long answer (10M) · DG = diagram · NUM = numerical · DER = derivation · CMP = compare/differentiate (table) · DEF = define / 1-2M / MCQ / fill-blank · CS = case study / scenario

| # | Topic | SN | LN | DG | NUM | DER | CMP | DEF/MCQ | CS |
|---|---|---|---|---|---|---|---|---|---|
| T1 | SLA – intro, need, benefits | 📘 | 📘 | 📘 structure | – | – | 🟡 | 📘 | 📘 bank on Azure |
| T2 | SLA life cycle | 📘 (deck's *exam question*) | 📘 | 📘 | – | – | 📘 phase matrix | 🟡 | 📘 banking 4 h downtime |
| T3 | SLA contents | 📘 | 📘 | 📘 | – | – | – | 📘 list the clauses | 📘 AWS EC2 SLA |
| T4 | Types of SLA | 📘 | 📘 | 📘 3 diagrams | – | – | 📘 | 🟡 | 📘 university / hospital |
| T5 | SLO (+SLA/SLI/KPI) | 📘 | 🟡 | – | 🟡 identify SLA/SLO/SLI | – | 📘 SLA vs SLO; 📘 *"Differentiate SLA, SLI and SLO"* | 📘 | 📘 |
| T6 | SLA requirements | 📘 | 🟡 | 📘 | – | – | 📘 func vs non-func | 📘 | 📘 hospital activity |
| T7 | KPIs | 📘 | 🟡 | 🟡 | 📘 | – | 🟡 KPI vs SLO | 📘 SMART | 📘 |
| T8 | Monitoring & auditing | 📘 (deck: *"Discuss SLA monitoring"*) | 🟡 | 🟡 process | – | – | 🟡 monitoring vs auditing | 🟡 | 📘 EC2 monitoring case |
| T9 | SLA w.r.t. IaaS/PaaS/SaaS | 📘 | 📘 | 🟡 stack | – | – | 📘 | 🟡 | 📘 |
| T10 | Examples of cloud SLAs | 📘 | 🟡 | – | 🟡 credit from tier table | – | 📘 AWS/Azure/GCP | 🟡 | 📘 |
| T11 | Limitations of SLA | 📘 | 🟡 | – | 📘 ₹50 L loss vs ₹20 k credit | – | – | 🟡 | 📘 |
| T12 | Availability numericals | 🟡 nines | 🟡 | – | 📘📘📘 (heavy) | 🟡 downtime formula | – | ◐ availability MCQ; 📘 | 📘 |
| T13 | SLA violation & penalty | 📘 | 📘 | 📘 detection flowchart | 📘📘 (5 problems + more) | – | – | 🟡 | 📘 |
| T14 | Economic viewpoint | 📘 | 📘 | 📘 | 🟡 break-even | – | 📘 CapEx vs OpEx; traditional vs cloud | ◐ "major advantage of cloud" | 📘 |
| T15 | Utility pricing | 📘 ◐ | 📘 | 📘 architecture | 📘 (VM ₹10/hr) 🟡 | – | 🟡 | ◐ utility computing; ◐ Spot Cloud | 📘 |
| T16 | Value of on-demand | 📘 | 📘 | 📘 auto-scaling graph | – | – | 🟡 with vs without | ◐ scalability vs elasticity; ◐ demand- vs event-driven provisioning | 📘 streaming company |
| T17 | Penalty cost, exponential demand | 📘 | 📘 | 🟡 D(t) vs R(t) curves | 🟡 | 📘 (slides 66-68) | – | 📘 | 🟡 |

**Takeaways (what to expect in ESE-50):**
- **Numericals are the most "gettable" marks:** availability %, allowed downtime, violation check, penalty/credit, tiered credit. Almost certainly **at least one 5–10 M numerical** from T12/T13.
- **Diagrams to be ready to draw:** SLA structure, SLA contents tree, SLA lifecycle, 3 SLA types, utility-pricing flow, violation-detection flowchart, auto-scaling (D vs R curve).
- **Most "exam-question-like" slides in the notes:** Deck 3's slide 20 explicitly lists *"1. Explain SLA lifecycle. 2. Differentiate SLA, SLI and SLO. 3. Discuss SLA monitoring."* and slide 19 a case study (bank, 4 h downtime). Treat those as the most probable theory questions. 📘

---

# 3. TOPIC-BY-TOPIC DETAILED BREAKDOWN

> Style: easy language → what to write in the exam → diagram → numericals. Marks guide: **5 M ≈ definition + 5–6 points + (small diagram/example)**, **10 M ≈ definition + diagram + 8–10 points + example + advantages/limits**.

---

## 3.1 T1 — Service Level Agreement (SLA): Introduction 📘

**Easy idea:** You rent cloud stuff from AWS/Azure/GCP. How do you know it will actually work? You sign a contract that says "we promise 99.99% uptime; if we fail, you get money/credits back." That contract is the **SLA**.

**Definition (write this):** A *Service Level Agreement (SLA)* is a formal contract between a cloud service provider and a customer that specifies the **quality, availability, responsibilities and performance standards** of the cloud service, and the **penalties** if those standards aren't met.
Example: AWS promises 99.99 % uptime for EC2; if missed, customers get **service credits**.

**Why is SLA required?** (organisations keep critical apps/data in cloud; downtime = money loss)
- Clearly defines service expectations
- Guarantees availability
- Measures service quality
- Builds trust provider ↔ customer
- Protects customer interests
- Gives compensation if quality isn't maintained

**Objectives:** guarantee availability · ensure high performance · improve customer satisfaction · define responsibilities · set measurable standards · reduce misunderstandings · improve monitoring.

**Importance:** defines measurable quality · helps monitor provider · accountability · legal protection · enables auditing · continuous improvement.

**Characteristics of a good SLA:** Clearly defined · Measurable (uptime, latency, response time) · Realistic (achievable) · Flexible (can change with business) · Enforceable (legal provisions for violations).

**Parties & responsibilities**
| Cloud Service Provider (AWS/Azure/GCP) | Customer |
|---|---|
| Provide cloud services | Pay subscription fees |
| Maintain infrastructure | Use services properly |
| Monitor services | Follow security guidelines |
| Meet agreed performance | Report service issues |

**Basic structure of SLA (diagram – redraw in exam)** 📘
```
                 Service Level Agreement
                          |
        +-----------------+------------------+
        |                 |                  |
  Cloud Provider      Customer          Service Terms
  Responsibilities    Responsibilities       |
                                      Performance Metrics
                                      Availability
                                      Security
                                      Penalties
```

**Benefits**
| For customers | For providers |
|---|---|
| Guaranteed quality, high availability, transparency, reduced business risk, compensation on failure | Customer trust, better service management, competitive advantage, performance monitoring, satisfaction |

**Advantages of SLA (6 – very likely 5 M)** 📘
1. **Improves service quality** – minimum service level (uptime, response time, reliability) is contractually binding, so provider keeps improving. *Eg:* 99.99 % ⇒ minimal downtime.
2. **Defines responsibilities** – who does backup, security, maintenance, patches, DR, support. *Eg (IaaS):* provider = hardware/network/virtualisation; customer = OS/apps/data.
3. **Reduces conflicts** – expectations in writing; legal framework; compensation pre-agreed.
4. **Increases customer confidence** – transparency; customers can compare providers by SLA.
5. **Provides measurable performance** – KPIs: availability, response time, RTO, RPO, MTTR, latency, throughput. *Eg:* availability 99.95 %, support response ≤ 30 min, incident resolution ≤ 4 h.
6. **Supports continuous monitoring** – automated tools detect problems early; *eg:* CPU hits 90 % → auto-scale/alert.

**Real-life example (bank on Azure):** Availability 99.95 %, response < 200 ms, daily backup, recovery time 30 min; if < 99.95 % ⇒ service credits.

**Exam tip:** 5 M → definition + need (4 pts) + characteristics + example. 10 M → add structure diagram + benefits table + advantages + limitations (T11).

---

## 3.2 T2 — SLA Life Cycle 📘

Two versions appear in the notes; **learn the 5-phase one as the main answer** (it is the more formal/Buyya version) and mention the 6-stage as the simplified flow.

### (a) 6-stage (Module 2.1 slide 10 & Buyya deck slide 9) 📘
```
 Customer Requirements
          |
          v
   SLA Negotiation
          |
          v
    SLA Agreement
          |
          v
 Service Delivery (Implementation)
          |
          v
 Performance Monitoring
          |
          v
     SLA Review
          |
          v
 Improvement or Renewal
```

### (b) 5-phase Cloud SLA Lifecycle 📘 (Deck 4)
```
 1.DEFINITION ──> 2.PUBLISHING & ──> 3.NEGOTIATION ──> 4.OPERATION ──> 5.DE-COMMISSION
 (templates,      DISCOVERY          (bid, customise,   (deploy, monitor,  (release resources,
  SLIs, SLOs,     (catalogue/        sign contract)     enforce, penalty)  sanitise data,
  penalties)       registry)                                               settle bills)
```
| Phase | Primary focus | Key operations | Primary output |
|---|---|---|---|
| 1. Definition | Standardisation | Define SLIs, SLOs, penalty schemes | SLA template |
| 2. Publishing & Discovery | Market exposure | Register templates in public/private/federated registries; consumers search | Catalogue listing |
| 3. Negotiation | Agreement | Bidding & matchmaking, customisation (e.g. higher uptime/compliance), contract signing (digitally verified) | Binding contract |
| 4. Operation (Operationalisation, monitoring, enforcement) | Execution | Deploy VMs/containers; real-time telemetry (CPU, packet loss, latency); audit logging; proactive management (auto-scale, live VM migration, throttling); on breach log timestamp/duration, compute penalty credit, root-cause alerts | Compliance logs |
| 5. De-commissioning (Termination) | Off-boarding | Resource de-provisioning; secure data sanitisation (GDPR/HIPAA); final financial settlement; compliance archiving of logs | Final audit & receipt |

**Why lifecycle management is needed:** cloud is dynamic, virtualised, multi-tenant → static agreements are insufficient; need runtime flexibility, automated monitoring/scaling, orderly termination.

**Best practices (deck 4):** measurable metrics · automation first · end-to-end security (in every phase).

**Exam tip:** Deck explicitly lists *"Explain SLA lifecycle"* as an exam question → draw the 5-phase flow + the table's "focus/output" columns, 1–2 lines per phase. For 5 M write 5 phases × 1 line each + diagram.

---

## 3.3 T3 — SLA Contents 📘

**Definition:** SLA contents = essential clauses of an SLA that define scope of service, performance standards, responsibilities, monitoring, security and penalties.

**Diagram (redraw)** 📘
```
                      Service Level Agreement
                                |
 ---------------------------------------------------------------
 |         |          |            |        |         |         |
Service   Scope   Availability  Metrics  Roles &   Security  Penalties
Description        & Perf.              Resp.
                                |
 --------------------------------------------------
 |          |           |            |           |
Monitoring  Backup   Disaster     Review     Termination
                     Recovery
```

**The 15 clauses (memorise the order):**
| # | Clause | One-line explanation | Example |
|---|---|---|---|
| 1 | Service Description | What service: type, features, duration, location | AWS: EC2, S3, RDS, networking |
| 2 | Scope of Services | What's *included/excluded* | Includes compute, storage, support; excludes third-party software, customer hardware, customer's internet, config errors |
| 3 | Service Availability | % uptime | EC2 99.99 % |
| 4 | Performance Metrics | Response time, throughput, latency, CPU, memory, network speed, packet loss | Response < 200 ms, CPU < 70 %, latency < 50 ms |
| 5 | Roles & Responsibilities | Provider vs customer duties | provider: infra, backup, security; customer: pay, accounts, report |
| 6 | SLOs | Specific numeric targets | 99.99 %, < 200 ms, recovery 30 min, daily backup |
| 7 | Monitoring & Reporting | Continuous monitoring + reports | CloudWatch; monthly uptime reports |
| 8 | Security & Compliance | Encryption, IAM, firewall, MFA, audits; ISO 27001, GDPR, HIPAA, PCI DSS | Google encrypts data at rest + in transit |
| 9 | Backup & Disaster Recovery | Daily/weekly/incremental/full; failover, replication | Azure replicates storage across regions |
| 10 | Incident & Problem Management | How failures handled; severity levels | Critical = complete failure, High = major functionality, Medium = partial |
| 11 | Change Management | Updates, patches, planned maintenance notice | customers informed before maintenance |
| 12 | SLA Violations & Penalties | credits/refunds | 99.99 promised, 99.8 delivered → credits |
| 13 | Exclusions | Not covered | natural disasters, customer's internet, config errors, attacks due to customer negligence |
| 14 | Review & Revision | Monthly/quarterly/annual | update as needs change |
| 15 | Termination Clause | End date, notice, data migration, data deletion, final billing | |

**Incident-handling process (slide 66 flow):** Problem occurs → Customer reports → Technical support → Investigation → Solution implemented → Issue closed.

**Real-world example (AWS EC2 SLA):** Service = EC2 VMs; Availability 99.99 %; response < 200 ms; support 24×7; backup daily snapshots; security IAM + encryption + firewall; penalty = service credits; monitoring = CloudWatch.

**Advantages of well-defined contents:** clear expectations, better quality, better monitoring, trust, faster issue resolution, legal protection, fewer disputes. **Disadvantages:** time-consuming, complex legal language, hard to monitor every metric, needs periodic updates, can't cover everything.

**Exam tip:** 5 M → list ~8–10 clauses with 1 line each + diagram. 10 M → all 15 + example + pros/cons.

---

## 3.4 T4 — Types of SLA 📘

**Idea:** Different customers need different agreements → 3 ways of structuring an SLA.

| | **Customer-based** | **Service-based** | **Multi-level** |
|---|---|---|---|
| Meaning | One agreement with **one customer** covering **all services** they use | One agreement for **one service**, same for **all customers** | **One SLA built in 3 stacked layers**: Corporate (rules common to *all* customers) → Customer (extra terms for *one* customer) → Service (terms for *one* service). Final SLA = all three layers combined |
| Example | University signs one SLA with AWS for VMs, storage, DB, email | AWS EC2: 99.99 % + 24×7 support for every EC2 customer | **Corporate** (same for all): security, privacy, compliance, support policy → **Customer** (one customer): response time, backup schedule, recovery objectives → **Service** (one service): storage availability, DB uptime, VM performance |
| Pros | Easy to manage, customised, single agreement | Easy to maintain, standardised, same quality for all | Highly flexible, easy to customise, better management |
| Cons | Hard to update individual services; not reusable for other customers | Can't customise; may not satisfy everyone | Complex; difficult to administer |
| Flexibility / Complexity | High / Medium | Low / Low | Very high / High |
| Customisation | Yes | No | Yes |
| Best for | Large organisations | Standard services | Enterprises |

**Diagrams (redraw all three):**
```
 Customer-Based SLA        Service-Based SLA (EC2)        Multi-Level SLA
      University                   EC2 Service SLA             Corporate level
          |                              |                           |
 ---------------------        ---------------------          Customer level
 |    |     |      |          |        |        |                    |
EC2   S3   RDS  Cloud Email  Cust. A  Cust. B  Cust. C        Service level
```

**Multi-level SLA – what it actually means (easy idea):** Instead of one big flat contract, the SLA is built in **layers**, like a company rulebook → department rules → job-specific rules. Each layer covers a different *scope*, and the layers **stack together** to form the full agreement:
- **Corporate level** = rules that are the *same for everybody* (security, privacy, compliance, support policy). Written once, never repeated per customer.
- **Customer level** = extra terms for *one particular customer/group* (their response time, backup schedule, recovery objectives).
- **Service level** = terms for *one particular service* that customer uses (storage availability, DB uptime, VM performance).
- A customer's total SLA for a service = Corporate + Customer + Service terms combined. Common terms are not rewritten each time, so changing a corporate policy updates every customer at once, while each customer/service can still be customised. That is why it is "highly flexible", and also why it is "complex" (many layers to keep consistent).

*Example:* Provider = AWS, customer = a university using EC2 and S3.
Corporate: all AWS customers get ISO 27001 security + GDPR compliance + 24×7 support policy →
Customer (University): 15-min response time, nightly backup, 1 h recovery objective →
Service: EC2 99.99 % uptime; S3 durability 99.999999999 %.
*Contrast:* Customer-based = one customer, all services, in one flat document. Service-based = one service, all customers, in one flat document. Multi-level = layers combining both.

**Level contents of Multi-level (important):**
- *Corporate level* – applies to **all** customers: security policy, data privacy, compliance, support policy
- *Customer level* – a particular customer/group: response time, backup schedule, recovery objectives
- *Service level* – specific service: storage availability, DB uptime, VM performance

**Scenario (notes' classroom activity):** hospital moving patient system to cloud → **Customer-based SLA** (specific security & availability needs).

**Exam tip:** 5 M → 3 types + diagram + 1 pro/con each. 10 M → full comparison table + examples.

---

## 3.5 T5 — Service Level Objectives (SLOs) 📘

**Idea:** SLA is the whole contract (broad); **SLO is one specific measurable target inside it**.

**Definition:** A *Service Level Objective* is a measurable performance target that specifies the expected quality of a cloud service.

**Examples (table):**
| Objective | Target |
|---|---|
| Availability | 99.99 % |
| Response time | < 200 ms |
| Recovery time | 30 min |
| Backup frequency | Daily |
| Packet loss | < 1 % |

**Characteristics:** measurable · realistic · time-bound · customer-focused · performance-oriented.
**Importance:** measures quality, helps monitor provider, improves satisfaction, supports SLA compliance.
**Example (Google Cloud Storage):** SLO availability 99.95 %; below ⇒ provider may owe credits.

### SLA vs SLO 📘
| SLA | SLO |
|---|---|
| Complete agreement | Performance target |
| Legal contract | Technical objective |
| Includes penalties | No penalties by itself |
| Broad | Specific |

### SLA vs SLI vs SLO (+KPI) — *deck's own exam question* 📘
| Term | Full form | Meaning | Example |
|---|---|---|---|
| **SLI** | Service Level **Indicator** | The **measured** metric (what actually happened) | uptime, error rate, response time, latency, throughput; "measured uptime 99.97 %" |
| **SLO** | Service Level **Objective** | The **target** for an SLI | "Availability ≥ 99.95 %" |
| **SLA** | Service Level **Agreement** | The **contract**: SLOs + responsibilities + penalties | "Provider guarantees high availability; credits if SLO missed" |
| **KPI** | Key Performance Indicator | Measurable value to judge if service meets business/technical goals | availability, response time… |

> Memory trick: **SLI = measure → SLO = goal → SLA = contract with consequences.**
> Notes' mini-example: SLA: "provider guarantees high availability"; SLO: "availability ≥ 99.95 %"; KPI/SLI: "measured monthly uptime = 99.97 %" (→ target met).

🟡 **Quick numerical-style question you can get:** *"Uptime measured = 99.97 %; SLO = 99.95 %. Is the SLO met?"* → 99.97 ≥ 99.95 ⇒ Yes, met, no penalty.

---

## 3.6 T6 — SLA Requirements 📘

**Idea:** What quality of service the customer *expects* from the provider; must be written into the SLA.

**General requirements (diagram: list box in notes):**
1. **Availability** – agreed uptime (e.g. 99.99 %)
2. **Reliability** – operate without frequent failures
3. **Scalability** – increase/decrease resources on demand
4. **Performance** – fast response, low latency, high throughput
5. **Security** – encryption, authentication, firewalls, access control
6. **Backup** – regular backups
7. **Disaster recovery** – quick recovery after failure
8. **Technical support** – e.g. 24×7 help-desk
9. **Monitoring** – continuous monitoring

### Functional vs Non-functional requirements 📘
| Functional (WHAT the provider must deliver) | Non-functional (HOW WELL it must perform) |
|---|---|
| Compute (VMs) | Availability |
| Storage | Reliability |
| Network connectivity | Scalability |
| Backup & recovery | Performance |
| Load balancing | Security |
| Auto-scaling | Privacy |
| Database services | Compliance (GDPR, HIPAA, ISO 27001) |
| Authentication & authorisation | Response time, Recovery time, Monitoring, Disaster recovery |

**Classroom activity (hospital patient-management system) — model answer from notes:** 
- SLA type: **Customer-based** (specific security/availability needs)
- SLOs: 99.99 % availability; incident response within 30 min; daily encrypted backups
- Functional: VMs, database, storage, backup, authentication
- Non-functional: security, privacy, reliability, performance, compliance

---

## 3.7 T7 — Key Performance Indicators (KPIs) 📘

**Definition:** A KPI is a measurable value used to evaluate whether cloud services are meeting business and technical objectives.
(Example: website receives 1000 req/s with response time 180 ms → these values are KPIs.)

**Why KPIs matter:** measure quality · detect degradation · improve satisfaction · reduce downtime · support SLA compliance · better decisions · proactive maintenance.

**Good KPI = SMART:** Specific, Measurable, Achievable, Relevant, Time-bound.
- Poor: "System should be fast." → Good: "Average response time < 150 ms."

**Cloud performance metrics (with formulas/examples)**
| Metric | Meaning | Formula / Example |
|---|---|---|
| **Availability** | % of time service is operational | `(Total time − Downtime)/Total time × 100`. Month = 43,200 min, downtime 30 min → (43200−30)/43200×100 = **99.93 %** |
| **Response time** | Time server takes to respond to a request | Request 10:00:00 → response 10:00:00.150 = **150 ms**. Ideal: website < 200 ms, DB < 100 ms, critical apps < 50 ms |
| **Latency** | Delay in transmitting data over the network | Causes: distance, congestion, routing delays, hardware limits. Mumbai→Singapore 40 ms |
| **Throughput** | Data processed per unit time (Mbps, Gbps, transactions/s) | 5 GB in 50 s = **100 MB/s** |
| **Error rate** | % failed requests | `Failed/Total × 100`. 40 failed of 20,000 = **0.2 %** |
| **Resource utilisation** | CPU/memory/disk/network usage | CPU 65 %, memory 72 %, disk 40 % – avoids overload & under-use |
| **Reliability** | Operate continuously without failure | MTBF, failure rate |
| **Scalability** | Handle growing load | 10,000 → 100,000 users, cloud adds servers |
| **Network bandwidth** | Max data that can be transmitted | Mbps, Gbps |
| **Customer satisfaction** | Feedback, complaints, ticket resolution | NPS, CSAT |

**KPI table in notes:** Availability = % uptime · Response time = time to respond · Throughput = requests/sec · CPU usage = processor utilisation · Memory usage = RAM utilisation · Error rate = number of failures · Customer satisfaction = user feedback.

**Other metrics named in the notes (SLA-metric list):** RTO (Recovery Time Objective – max time to restore), RPO (Recovery Point Objective – max data-loss window), **MTTR** (Mean Time To Repair), MTBF.

🟡 *Definitions of RTO/RPO/MTTR/MTBF in one line each (not defined on slides, only named):* RTO = how fast service must be restored; RPO = how much recent data may be lost (time between last backup and failure); MTTR = average repair time; MTBF = average time between failures.

---

## 3.8 T8 — Metrics for Monitoring and Auditing 📘

### Monitoring
**Definition:** continuous observation of infrastructure, applications and services to ensure they perform according to the SLA.
**Objectives:** detect failures early · monitor resource usage · improve availability · prevent violations · optimise performance · alerts for abnormal behaviour.

**Four types**
| Type | Metrics watched |
|---|---|
| Infrastructure | CPU, RAM, disk, VMs, network devices |
| Application | app response time, error logs, user transactions, API performance |
| Network | bandwidth, packet loss, latency, traffic flow |
| Security | login attempts, unauthorised access, malware detection, firewall events |

**Monitoring process (6 steps):** Collect metrics → Analyse data → Compare with SLA thresholds → Trigger alerts if exceeded → Generate reports/dashboards → Corrective action.
**Tools:** Amazon CloudWatch, Azure Monitor, Google Cloud Monitoring, Prometheus, Grafana, Nagios, Zabbix.

### Auditing
**Definition:** systematic examination of cloud services, configurations, logs and security controls to verify compliance with policies, regulations and SLA commitments.
**Objectives:** verify SLA compliance · regulatory compliance · detect vulnerabilities · identify unauthorised activity · accountability.

| Audit type | By whom / what |
|---|---|
| Internal | by the organisation – internal controls |
| External | independent auditors/certification bodies |
| Security | encryption, authentication, firewall, access management |
| Compliance | ISO 27001, GDPR, HIPAA, PCI-DSS |

**Audit logs record:** logins/logouts, config changes, file access, resource provisioning, failed authentication, admin actions → used for troubleshooting, forensics, proving compliance.

**Case study – EC2 monitoring (notes):**
| Metric | SLA promise | Measured | Verdict |
|---|---|---|---|
| Availability | 99.99 % | 99.95 % | ✗ below |
| CPU utilisation | < 80 % | 92 % | ✗ too high |
| Response time | < 200 ms | 320 ms | ✗ exceeds |

Conclusion: SLA not met → corrective action: **auto-scaling, load balancing, infrastructure optimisation**.

🟡 **Monitoring vs Auditing (self-made, likely 5 M "differentiate"):**
| Monitoring | Auditing |
|---|---|
| Continuous, real-time | Periodic, systematic review |
| Detects failures/threshold breaches | Verifies compliance with SLA/regulations |
| Tools: CloudWatch, Azure Monitor, Nagios | Done by internal/external auditors using audit logs |
| Output: alerts, dashboards | Output: audit report / compliance certificate |

Violation-detection flow (Fig. in §3.13) ties monitoring → compare with SLA → alert → penalty.

---

## 3.9 T9 — SLA Requirements w.r.t. Cloud Delivery Models 📘

**Idea:** What the provider promises depends on **how much of the stack the provider manages**. IaaS < PaaS < SaaS in provider responsibility.

### IaaS (AWS EC2, Azure VM, Google Compute Engine)
Provider supplies virtual machines/storage/network; **customer manages OS, apps, data**.
SLA requirements: 1) compute (VM) availability (e.g. 99.95 %) 2) storage availability (durability, redundancy, fast access) 3) network availability (internet, internal network, load balancing) 4) backup & DR (frequency, restore process, **RTO, RPO**) 5) performance (CPU, memory, disk I/O, bandwidth allocation) 6) security (firewall, IAM, encryption, DDoS protection).
| Example IaaS SLA | |
|---|---|
| VM availability | 99.95 % |
| Storage availability | 99.99 % |
| Network availability | 99.9 % |
| Backup | Daily |
| RTO | 2 hours |
| RPO | 30 minutes |

### PaaS (Google App Engine, Azure App Service, AWS Elastic Beanstalk)
Provider manages infrastructure + platform; **customer develops/deploys apps**.
SLA requirements: platform/runtime availability (99.95 %) · database availability (99.99 %) · API availability (99.9 %) · runtime environment (Java, Python, Node.js, .NET, PHP) · automatic scaling · development tools (CI/CD, source control, monitoring).
| Example PaaS SLA | |
|---|---|
| Platform availability | 99.95 % |
| Database availability | 99.99 % |
| API response time | < 200 ms |
| Auto scaling | Enabled |
| Deployment support | 24×7 |

### SaaS (Gmail, Microsoft 365, Salesforce)
Provider manages whole stack; **customer just uses software**.
SLA requirements: application availability (99.9 %) · user authentication (password, MFA, SSO) · data privacy (encryption, access control, privacy policy) · data backup · performance (page load time, transaction response, max concurrent users) · customer support (24×7, email, chat, phone).
| Example SaaS SLA | |
|---|---|
| Application availability | 99.9 % |
| Login response time | < 2 s |
| Backup frequency | Daily |
| Customer support | 24×7 |
| Data encryption | AES-256 |
| MFA | Supported |

### Comparison of SLA requirements (reconstructed from slide 140) 📘
| Requirement | IaaS | PaaS | SaaS |
|---|---|---|---|
| Virtual machine availability | ✓ | ✗ | ✗ |
| Storage availability | ✓ | ✓ | ✓ |
| Network availability | ✓ | ✓ | ✓ |
| Runtime environment | Customer | Provider | Provider |
| Application availability | Customer | Shared | Provider |
| Database availability | Customer-managed | Provider | Provider |
| Automatic scaling | Optional | Usually included | Provider |
| Security | Shared responsibility | Shared responsibility | Mostly provider |
| Backup | Shared responsibility | Provider | Provider |
| Technical support | Infrastructure | Platform | Complete application |

### Shared Responsibility Model 📘
| Component | On-Premises | IaaS | PaaS | SaaS |
|---|---|---|---|---|
| Applications | Customer | Customer | Customer | Provider |
| Data | Customer | Customer | Customer | Shared |
| Runtime | Customer | Customer | Provider | Provider |
| Middleware | Customer | Customer | Provider | Provider |
| Operating System | Customer | Customer | Provider | Provider |
| Virtualisation | Customer | Provider | Provider | Provider |
| Servers | Customer | Provider | Provider | Provider |
| Storage | Customer | Provider | Provider | Provider |
| Networking | Customer | Provider | Provider | Provider |

→ Moving IaaS → PaaS → SaaS: provider takes more responsibility, customer's management burden falls.

🟡 **Diagram to draw in 10 M (stack):**
```
        On-Prem        IaaS          PaaS          SaaS
      +---------+  +---------+   +---------+   +---------+
 Cust | App/Data|  | App/Data|   | App/Data|   |         |
      | Runtime |  | Runtime |   +---------+   |         |
      | OS      |  | OS      |   |         |   |         |
      |Virtual. |  +---------+   | Provider|   | Provider|
      | Server  |  | Provider|   |  manages|   |  manages|
      | Storage |  |  manages|   |         |   |   all   |
      | Network |  |         |   |         |   |         |
      +---------+  +---------+   +---------+   +---------+
```
(Customer-managed part shrinks left → right.)

---

## 3.10 T10 — Examples of Cloud SLAs 📘

**Definition:** A cloud SLA is a formal agreement defining guaranteed service levels — availability, performance, support and penalties.
**Why study them:** providers differ; organisations compare SLAs because they affect business continuity, customer satisfaction, downtime, financial loss, compliance.

| Provider | Services with SLA | Typical commitment | Features |
|---|---|---|---|
| **AWS** | EC2, S3, RDS, DynamoDB, Lambda | EC2 **Monthly Uptime Percentage (MUP) 99.99 %** | CloudWatch monitoring; credits |
| **Microsoft Azure** | VMs, Azure SQL DB, Storage, App Services | VMs **up to 99.99 %** (depends on deployment configuration) | automatic failover, backup, monitoring, HA |
| **Google Cloud** | Compute Engine, Cloud Storage, BigQuery, GKE | Compute Engine **99.95 % or higher** (depends on deployment) | live migration, global load balancing, auto-scaling |

**AWS EC2 credit table (notes):**
| Monthly Uptime | Service Credit |
|---|---|
| ≥ 99.99 % | No credit |
| < 99.99 % | 10 % credit |
| < 99.0 % | 30 % credit |

*(In the notes' tiers: 99.0 ≤ uptime < 99.99 → 10 %; uptime < 99.0 → 30 %.)*
🟡 *Outside notes — verify on AWS site: the real EC2 SLA has a further tier (< 95 % → 100 % credit); use the table above in exam as given in notes.*

**Comparison (notes):**
| Feature | AWS | Azure | Google Cloud |
|---|---|---|---|
| Availability | up to 99.99 % | up to 99.99 % | 99.95 % or higher |
| Monitoring | CloudWatch | Azure Monitor | Cloud Monitoring |
| Auto scaling | Yes | Yes | Yes |
| Load balancing | Yes | Yes | Yes |
| Service credits | Yes | Yes | Yes |

**Real-life example:** online shopping company on AWS: availability 99.99 %, response 200 ms, daily backup; miss uptime ⇒ service credits.

🟡 **Numerical using the credit table:** *EC2 bill ₹1,00,000; measured monthly uptime 99.5 %. Credit?* → 99.0 ≤ 99.5 < 99.99 ⇒ 10 % ⇒ **₹10,000**. If uptime was 98.7 % ⇒ 30 % ⇒ ₹30,000.

---

## 3.11 T11 — Limitations of SLA 📘

**Definition:** drawbacks/restrictions that reduce the effectiveness of an SLA.

### (A) Seven limitations (slides 151–153) — use as a 5 M list
1. **Difficult to measure** – metrics such as user experience are hard to quantify
2. **Complex agreements** – long technical + legal language
3. **Service credits instead of cash** – most providers give credits, not refunds
4. **Exclusions** – natural disasters, war, internet failures outside provider control, customer configuration errors
5. **No guarantee against all downtime** – even 99.99 % allows ~52.56 min/year
6. **Monitoring challenges** – customers need their own tools to verify
7. **Vendor dependency** – each provider has its own terms; hard to compare
*(Despite limitations: defines responsibilities, improves quality, transparency, trust.)*

### (B) Five disadvantages explained in depth (slides 23–53) — use for 10 M
1. **Complex to prepare** – must define: service requirements (services, scope, availability, response time, recovery time, backup policies incl. RPO) · SLA metrics · roles & responsibilities · security & compliance (encryption, authentication, access control, GDPR/HIPAA/ISO 27001) · penalty clauses · legal (duration, termination, liability, IP, jurisdiction, force majeure) · dynamic cloud environment (frequent revisions). *Example:* hospital migrating patient system — 99.999 %, encryption, DR in 30 min, daily backups, healthcare compliance, 2 s response, penalties → takes weeks; needs technical + security + legal + business + provider.
2. **Difficult to monitor** – geographically distributed DCs, thousands of VMs, no direct access for customers, different tools give different values, external network latency. *Eg:* app slow — provider, customer's ISP or the app itself?
3. **May not cover all situations** – natural disasters, DDoS, ISP failures, government regulation, software bugs, pandemics, third-party failures. Provider invokes **Force Majeure** (earthquake, 99.95 % SLA ⇒ no penalty).
4. **Negotiation takes time** – customers ask for 99.999 %, stronger security, faster response, DR, data residency, compliance; provider checks feasibility, cost, pricing ⇒ weeks. Impact: delayed deployment, longer procurement, higher legal/admin cost.
5. **Penalties may not fully compensate losses** – forms: *service credits* ($1,000 bill, 10 % → $100), *subscription discounts* ($500/month, 20 % for 3 months), *refund* ($2,000, 25 % → $500), *free extension* (+1 month on a 1-year plan). Providers limit liability to reduce risk.

### Numerical (notes, slide 52) 📘
*Shopping site down 4 h during festival; sales loss ₹50,00,000; SLA = 10 % credit; monthly bill ₹2,00,000.*
Compensation = 10 % × 2,00,000 = **₹20,000** ≪ ₹50 lakh loss ⇒ customers may need insurance, backup providers or **multi-cloud**.
(Loss unrecovered = 50,00,000 − 20,000 = **₹49,80,000**.)

---

## 3.12 T12 — NUMERICALS ON SERVICE AVAILABILITY 📘 (+ 🟡 extensions)

### A. Concept
**Service availability** = % of time a cloud service is operational and accessible during an agreed period. Importance: Internet banking – very high; hospital info system – very high; cloud storage – high; email – high; social media – moderate.

### B. Formulas (write these first in every answer)
```
(1)  Availability (%) = (Total Time − Downtime) / Total Time × 100
(2)  Availability (%) = Uptime / (Uptime + Downtime) × 100        [Uptime = Total − Downtime]
(3)  Downtime allowed = (100 − Availability) × Total Time / 100    [derived from (1)]
(4)  SLA violated  ⇔  Actual availability < SLA availability   (equivalently: actual downtime > allowed downtime)
(5)  Penalty / Credit = Monthly service cost × Penalty % / 100
```
**Derivation of (3):** From (1): A = (T − D)/T × 100 ⇒ A·T/100 = T − D ⇒ **D = T − A·T/100 = (100 − A) × T/100**.

**Unit conversions to remember:** 1 day = 24 h = 1440 min = 86,400 s · **30-day month = 720 h = 43,200 min** (use 30 days unless told otherwise) · **1 year = 365 d = 8,760 h = 5,25,600 min** · 31-day month = 744 h = 44,640 min.

### C. "Number of nines" tables 📘 (verified ✔)
| Availability | Downtime / year | Downtime / month (30 d) | Typical application |
|---|---|---|---|
| 99 % | 3.65 days | 7.2 hours | Small business websites |
| 99.5 % | 1.83 days | 3.6 hours | Internal business systems |
| 99.9 % | 8.76 hours | 43.2 minutes | Cloud storage, email |
| 99.95 % | 4.38 hours | 21.6 minutes | Virtual machines, databases |
| 99.99 % | 52.56 minutes | 4.32 minutes | Banking, healthcare |
| 99.999 % | 5.26 minutes | 25.92 seconds | Mission-critical systems |

🟡 *Extra column (self-computed): downtime/day:* 99 % = 14.4 min · 99.9 % = 86.4 s · 99.99 % = 8.64 s · 99.999 % = 0.864 s.
**More nines ⇒ higher availability ⇒ lower allowable downtime** (each extra nine = 10× less downtime).

### D. Solved numericals from the notes 📘

**N1.** Service runs 30 days, downtime = 2 h. Availability?
Total = 30×24 = 720 h. A = (720 − 2)/720 × 100 = 718/720 × 100 = **99.72 %**.

**N2.** SLA = 99.9 %. Max downtime in 30 days?
D = (100 − 99.9) × 720/100 = 0.1 × 720/100 = 0.72 h = 0.72 × 60 = **43.2 min**.

**N3.** Provider promises 99.99 %. Max downtime in 1 year?
Total = 365×24 = 8760 h. D = (100 − 99.99) × 8760/100 = 0.01 × 8760/100 = 0.876 h = **52.56 min**.

**N4 (violation).** SLA = 99.95 %, actual = 99.80 %. Violated? 99.80 < 99.95 ⇒ **Yes, violated.**

**N5 (no violation).** SLA = 99.5 %, actual = 99.7 %. 99.7 > 99.5 ⇒ **No violation.**

**N6 (KPI example).** 43,200 min month, downtime 30 min ⇒ (43,200 − 30)/43,200 × 100 = **99.93 %**.

**N7 (Buyya deck).** 719 h uptime, 1 h downtime ⇒ 719/(719+1) × 100 = **99.86 %**.

**N8 (banking).** 99.99 % promised; unavailable 2 h in one month. Allowed = 4.32 min; actual = 120 min ⇒ 120 > 4.32 ⇒ **SLA violated**, compensation as per agreement.

**N9 (full problem – slide 167–169).** 30 days, SLA = 99.9 %, actual downtime = 2 h, monthly charge = ₹1,20,000, penalty = 20 %. Find availability, violation?, penalty.
1) Total = 720 h 2) A = 718/720 × 100 = **99.72 %** 3) 99.72 < 99.9 ⇒ **violated** 4) Penalty = 1,20,000 × 20/100 = **₹24,000**.

**N10 (Problem 4, slide 200).** 99.99 %, one month, actual downtime = 30 min. Allowed = 4.32 min; 30 > 4.32 ⇒ **violated**.

### E. Factors affecting availability & techniques to improve 📘
| Factors that reduce availability | Techniques to improve |
|---|---|
| Hardware failures, software bugs, network failures, power outages, cyber-attacks, scheduled maintenance, natural disasters, human errors | Redundant servers, load balancing, data replication, automatic failover, regular backups, DR plans, monitoring & alerting, geographically distributed data centres |

### F. 🟡 SELF-MADE EXTENSIONS (not in notes – practise these as likely "twist" questions)

**F1. Availability from MTBF/MTTR.** `A = MTBF / (MTBF + MTTR)`.
*Q:* MTBF = 500 h, MTTR = 2 h. → A = 500/502 = 0.99602 ⇒ **99.60 %**.

**F2. Series (all components needed) and parallel (redundant) availability.**
- Series: `A = A₁ × A₂ × …`
- Parallel (redundant, any one enough): `A = 1 − (1 − A₁)(1 − A₂)…`
*Q:* App server 99.9 %, DB 99.95 %, load balancer 99.99 % in series. A = 0.999 × 0.9995 × 0.9999 = 0.998401 ⇒ **99.84 %**; downtime/month = (1 − 0.998401) × 43,200 ≈ **69 min** → fails a 99.9 % SLA (43.2 min).
*Q:* Two servers, each 99 %, in parallel (redundancy): A = 1 − (0.01)(0.01) = 0.9999 ⇒ **99.99 %** — redundancy (a listed technique) buys two extra nines.

**F3. Planned-maintenance exclusion** (many SLAs exclude scheduled maintenance).
`A = (T − planned − unplanned) / (T − planned) × 100`
*Q:* T = 720 h, planned maintenance 4 h, unplanned outage 1 h. A = (720 − 4 − 1)/(720 − 4) = 715/716 = **99.86 %**.

**F4. Multiple outages.** 3 outages of 12, 18, 30 min in a 30-day month. Total = 60 min. A = (43,200 − 60)/43,200 = 43,140/43,200 = **99.861 %**. Against 99.95 % (allowed 21.6 min): violated by 38.4 min.

**F5. Reverse problem – required availability.** Business tolerates ≤ 10 min downtime per 30-day month → A = (43,200 − 10)/43,200 × 100 = **99.977 %** ⇒ needs "three-and-a-half nines" (≥ 99.99 % tier to be safe).

**F6. Exam presentation template (use for every numerical):**
`Given → Formula → Substitution → Answer (with unit) → Conclusion (violated / not violated / penalty)`

---

## 3.13 T13 — SLA Violation & Penalty Computation 📘

**Definition:** An SLA violation occurs when the provider fails to meet one or more service commitments (availability, response time, throughput, latency, data durability, recovery time, support response). *Example:* SLA 99.95 %, actual 99.80 % ⇒ violated.

**Causes of violations (6, with examples)**
| Cause | Examples | Impact |
|---|---|---|
| Hardware failures | server crash, disk/memory/power-supply failure | downtime ↑ |
| Network failures | internet outage, router/switch failure, sub-sea cable damage | users can't reach service |
| Software bugs | app crash, OS failure, DB errors, memory leaks | degraded performance |
| Human errors | wrong server config, accidental deletion, wrong firewall, misconfigured VMs | outages |
| Cyber attacks | DDoS, ransomware, malware, breaches | unavailable/degraded |
| Natural disasters | floods, earthquakes, fires, storms | DC outage |

**Detection methods (5):** performance monitoring (CPU, memory, traffic, disk; CloudWatch/Azure Monitor/GCM) · availability monitoring (HTTP checks, ping, health checks) · log analysis · alert systems (email, SMS, dashboard) · auditing (security, compliance, performance audits).

**Violation detection process (diagram – redraw)** 📘
```
 Cloud Service
      |
      v
 Continuous Monitoring
      |
      v
 Performance Metrics Collected
      |
      v
 Compare with SLA Targets
      |
      v
  Violation? ──No──> Continue Monitoring
      |
     Yes
      v
 Generate Alert
      |
      v
 Calculate Penalty
```

**Penalty models (4)** 📘
| Model | Meaning | Example |
|---|---|---|
| Service credit | credit usable on future bills | bill ₹20,000, 10 % ⇒ ₹2,000 credit |
| Refund | part of fee returned | ₹50,000, 15 % ⇒ ₹7,500 |
| Free service extension | extra subscription time free | 1 month free storage |
| Discount on future billing | reduced next invoices | 20 % off next month |

**Penalty formula:** `Penalty = Monthly Service Cost × Penalty % / 100`

**Best practices to avoid violations:** HA architecture, redundant servers, data replication, automatic failover, load balancing, continuous monitoring, auto scaling, DR plans, regular backups, preventive maintenance.

### Solved penalty numericals 📘
| # | Question | Solution |
|---|---|---|
| P1 | Bill ₹50,000, penalty 10 % | 50,000 × 10/100 = **₹5,000** |
| P2 | Cost ₹80,000, penalty 15 % | **₹12,000** |
| P3 | Bill ₹15,000, credit 25 % | **₹3,750** |
| P4 | Pays ₹60,000/month, 10 % penalty | 60,000 × 10/100 = **₹6,000** |
| P5 | Subscription ₹40,000, 15 % refund | 40,000 × 15/100 = **₹6,000** |
| P6 | Bill ₹20,000, 10 % service credit | **₹2,000** |
| P7 | Charge ₹50,000, 15 % refund | **₹7,500** |
| P8 | SLA 99.95 %, actual 99.70 % violated? | 99.70 < 99.95 ⇒ **Violated** |

### Tiered (slab) penalty — Problem 5 of notes 📘 (typo corrected)
*Monthly bill ₹80,000. Policy: availability ≥ 99.95 % → no penalty; 99.90–99.95 % → 10 % credit; < 99.90 % → 25 % credit. Actual availability = 99.88 %.*
99.88 < 99.90 ⇒ slab "< 99.90 %" ⇒ 25 % ⇒ Credit = 80,000 × 25/100 = **₹20,000**.
*(Slide wrote `80,000×100/25` – wrong order; the value ₹20,000 is right.)*

### 🟡 Self-made penalty problems
**Q-A (per-hour credit model, as in Deck 4 "10 % credit per hour of downtime").** Bill ₹1,00,000; downtime 3 h. Credit = 3 × 10 % = 30 % ⇒ **₹30,000**. (Credits are normally capped at 100 % of bill; 10 h downtime ⇒ 100 % ⇒ ₹1,00,000.)

**Q-B (tier problem with computed availability).** 30-day month, bill ₹80,000, single outage 50 min; policy as in notes' Problem 5.
A = (43,200 − 50)/43,200 × 100 = 43,150/43,200 × 100 = **99.884 %** < 99.90 ⇒ 25 % ⇒ **₹20,000**.

**Q-C (case study from Buyya deck, slide 19 – bank app, 4 h downtime; assumptions mine).** Assume SLA 99.9 %, 30 days, bill ₹5,00,000, tiers as per AWS table (< 99.99 → 10 %, < 99 → 30 %).
- Downtime = 240 min; A = (43,200 − 240)/43,200 × 100 = **99.444 %**.
- Allowed downtime at 99.9 % = 43.2 min; 240 > 43.2 ⇒ **SLA violated**.
- 99.0 ≤ 99.444 < 99.99 ⇒ 10 % credit = **₹50,000** (only a fraction of a bank's real losses – see T11).
- Corrective actions: root-cause analysis, redundancy + automatic failover, load balancing, auto-scaling, DR drills, better monitoring/alerts, geo-distribution.

---

## 3.14 T14 — Cloud Economics: Economic Viewpoint 📘

**Definition:** Cloud economics = study of the financial benefits, costs and business value of adopting cloud computing — whether moving to cloud beats maintaining on-premises IT. The *economic viewpoint* focuses on **minimising cost, maximising ROI, improving utilisation, achieving agility**.

**Why:** traditional IT spends on servers, networking, storage, licences, data centres, cooling, electricity, IT staff, maintenance contracts — cloud cuts many of these.

**Example 1:** Traditional – buy 10 servers + storage + network + UPS + cooling = **₹50 lakh**; even if only 20 % used, full cost paid. Cloud – rent VMs ≈ **₹50,000/month**: no upfront, easy scaling, lower maintenance, pay for use.

### The 6 objectives (the 10 M answer skeleton) 📘
1. **Reduce IT infrastructure cost** – no purchase of servers/storage/network; lower DC, cooling, power, space; maintenance shifted to provider; pay only for use. *Benefits:* lower upfront, less maintenance, cheaper power/cooling, predictability.
2. **Convert CapEx into OpEx**

| CapEx (traditional) | OpEx (cloud) |
|---|---|
| Buy servers, storage, build DC, networking hardware | Monthly subscription, VM usage, storage fees |
| Large initial investment | No large upfront investment |
| Assets depreciate | Expenses spread over time |
| *Eg:* ₹1 crore for DC | *Eg:* ₹5 lakh/month cloud |
Why important: preserves cash flow, reduces financial risk, easier budgeting, capital freed for core business; spending flexes with demand.

3. **Improve resource utilisation** – traditional servers often run at only 10–20 %. Cloud: virtualisation (share hardware), dynamic allocation, immediate release, auto-scaling. *Eg:* 50 servers in a sale, 5 normally. Benefits: less waste, lower cost per transaction, efficiency, better ROI on assets.
4. **Increase business agility & scalability** – agility = respond quickly; scalability = grow/shrink resources. Traditional: weeks/months to order hardware, overprovisioning. Cloud: minutes to deploy, instant storage, auto-scaling, global. *Eg:* app grows 1,000 → 10 lakh users with no new hardware. Benefits: faster time-to-market, customer experience, handle spikes, growth.
5. **Reduce operational complexity** – provider handles DC management, hardware maintenance, power/cooling, monitoring, much security/compliance. Benefits: smaller ops team, less admin, fewer config errors, higher reliability, focus on innovation.
6. **Optimise IT spending** – spend *efficiently*, not just less: right-size VMs, reserved instances for predictable load, **spot/preemptible instances for non-critical tasks**, remove idle resources, continuous usage monitoring, automated cost governance. *Eg:* 30 % VMs idle at night → auto-shutdown cuts bill. Benefits: budget control, higher ROI, lower waste, accountability, spend aligned with business value.

**How they work together:** ↓infra cost → ↓IT expenditure; CapEx→OpEx → cash flow; utilisation → no waste; agility → market response; ↓complexity → staff freed; optimisation → every rupee delivers value.

**What the economic viewpoint evaluates:** cost savings · revenue growth · business flexibility · risk reduction · productivity.

**Factors considered (traditional vs cloud)**
| Factor | Traditional | Cloud |
|---|---|---|
| Initial investment | Very high | Almost zero |
| Maintenance cost | Repairs, updates, cooling, power | Managed by provider |
| Scalability | Buy more hardware | Minutes |
| Resource utilisation | Servers idle | Dynamic allocation |
| Risk | Own DR/backup | Provider gives DR, backup, HA |

**Benefits graphic (slide 24):** cost savings · boost efficiency · agile adaptability · resilient robustness · financial flexibility · scalable growth.

**Diagram suggestion for exam:** the auto-scaling figure from slide 13 — *without* auto-scaling, fixed capacity vs fluctuating utilisation (waste/shortage); *with* auto-scaling, capacity tracks utilisation. 📘
```
 Without auto-scaling              With auto-scaling
 util ~~/\~~/\~~                   util ~~~~~~~~~~~~
 cap  ______________ (flat)        cap  _/‾\_/‾‾\_  (follows load)
```
(Also *vertical scaling* = bigger machine (more CPU/RAM); *horizontal scaling* = more instances — slide 16 figure.) 📘

🟡 **Break-even numerical (self-made, 5 M):**
*Own server: CapEx ₹3,00,000 + running cost ₹1,00,000 over 3 years = ₹4,00,000 (3 yrs = 26,280 h). Cloud VM = ₹20/h. When is cloud cheaper?*
Break-even hours = 4,00,000/20 = **20,000 h** = 20,000/26,280 = **76 % utilisation**. If the VM would be used < 76 % of the time, cloud is cheaper; for always-on loads, owning (or reserved instances) may win.

🟡 **Effective cost of idle capacity (extends slide 43):** ₹80 lakh data centre used 30 % ⇒ cost per *used* unit = 80/0.30 = **₹266.7 lakh** for the same useful work (≈ 3.33× the sticker price).

🟡 **Armbrust et al. break-even rule (literature, beyond notes):** cloud wins when `Cloud cost per hour < Datacenter cost per hour ÷ Utilisation`. Eg: own = ₹8/h at 30 % utilisation ⇒ effective ₹26.67/h; cloud at ₹20/h is cheaper.

**Exam tip:** 5 M → define + CapEx vs OpEx table + 3–4 objectives. 10 M → all 6 objectives + traditional-vs-cloud table + example.

---

## 3.15 T15 — Utility Pricing in Detail 📘

**Idea:** Like electricity — you pay for **units consumed**, not for owning the power plant.

**Definition:** Utility pricing is a consumption-based pricing model where customers pay only for the cloud resources they use (CPU time, storage, bandwidth, memory), eliminating large upfront investments. Also called **Pay-As-You-Go (PAYG)** / usage-based pricing.

**Why "utility"?** Same concept as public utilities:
| Utility service | Payment based on |
|---|---|
| Electricity | Units (kWh) consumed |
| Water | Litres / cubic metres |
| Gas | Cubic metres |
| Telephone | Minutes or data used |
| **Cloud computing** | **CPU hours, storage, bandwidth, API requests …** |

**How it works (5 steps):** user requests resources → provider allocates → usage monitored continuously (CPU-hours, storage, bandwidth) → billing computed from rates × consumption → customer pays only for actual use.

**Architecture diagram (redraw)** 📘
```
   User / Application
          |
 Request Cloud Resources
          |
  Cloud Service Provider
          |
   Resource Allocation
          |
 Usage Monitoring & Metering
          |
 Billing & Cost Calculation
          |
 Monthly / Usage Invoice
```

**Resources charged & units** 📘
| Resource | Charging unit |
|---|---|
| Virtual machines | per second / minute / hour |
| Storage | GB per month |
| Network bandwidth | GB transferred |
| Databases | instance-hours or transactions |
| Object storage | GB stored + API requests |
| Load balancer | hours + data processed |
| Serverless functions | number of executions + execution time |
| AI/ML services | API calls or compute time |

**5 Characteristics** 📘
1. **PAYG** – VM ₹10/h: 5 h → ₹50; 20 h → ₹200
2. **No upfront investment** – rent, don't buy
3. **Flexible pricing** – scale up/down; bill auto-adjusts
4. **Measured service** – metering of CPU, memory, storage, network traffic, API requests
5. **Elasticity** – auto scale; sale: 10 → 100 VMs, then back to 10; pay extra only during sale

**Advantages (7):** cost savings · better utilisation · easy scalability · financial flexibility (OpEx not CapEx) · faster deployment · suits SMEs/start-ups · supports innovation (experiment without permanent hardware).
**Economic-benefit table (Mod 2.2 slide 60, on-demand section – reusable here):** lower capital cost · operational efficiency · reduced wastage · better cash flow · improved ROI · better resource allocation.

**Disadvantages (5):** unpredictable costs (spikes → bigger bill) · continuous monitoring needed · **idle resources still cost** (running VM billed until stopped) · data-transfer (egress) charges · vendor dependency (different pricing models).

**Real-life example:** Traditional: 20 servers + storage + network + UPS/cooling = **₹80 lakh**, paid in full even if used only 30 %. Cloud: rent 20 VMs + 2 TB storage + 500 GB bandwidth; if demand falls ⇒ 10 VMs + 1 TB ⇒ bill falls automatically.

**Major platforms** 📘
| Provider | Pay for … |
|---|---|
| AWS | EC2 instances, S3 storage, Lambda executions, data transfer |
| Azure | VMs, Azure Storage, SQL Database, Functions, networking |
| GCP | Compute Engine, Cloud Storage, BigQuery queries, Cloud Functions |

### 🟡 Utility-pricing numericals (self-made; follow the notes' ₹10/hour style)
**Formula:** Bill = Rate × Quantity used. (30-day month = 720 h.)

**U1 (basic usage)** 📘 *(notes)*
VM = ₹10/h.
- Used 5 h → 5 × 10 = **₹50**
- Used 20 h → 20 × 10 = **₹200**

**U2 (multi-resource bill)**

| Resource | Calculation | Cost |
|---|---|---|
| VM | ₹10/h × 200 h | ₹2,000 |
| Storage | ₹2/GB-month × 500 GB | ₹1,000 |
| Bandwidth | ₹5/GB × 100 GB | ₹500 |
| **Total** | | **₹3,500** |

**U3 (elasticity bill)**
*Online store: 10 VMs normally, 100 VMs for a 3-day sale (3 × 24 = 72 h), VM = ₹10/h, 30-day month (720 h).*
1. Baseline (10 VMs all month) = 10 × 720 × 10 = ₹72,000
2. Sale extra (90 extra VMs for 72 h) = 90 × 72 × 10 = ₹64,800
3. **Cloud bill = 72,000 + 64,800 = ₹1,36,800**
4. Without elasticity (100 VMs all month) = 100 × 720 × 10 = ₹7,20,000
5. **Saving = 7,20,000 − 1,36,800 = ₹5,83,200 (≈ 81 %)**

**U4 (break-even)** — see §3.14. Own server ₹4,00,000 over 3 yrs (26,280 h) vs cloud ₹20/h → 4,00,000 / 20 = 20,000 h → 20,000 / 26,280 ≈ **76 % utilisation**. Below 76 % use, cloud is cheaper.

**Exam tip:** 5 M → definition + electricity analogy + how it works + 4 characteristics + 2 pros/2 cons. 10 M → add architecture diagram + resource-unit table + all pros/cons + example.

---

## 3.16 T16 — Value of On-Demand Services 📘

**Definition:** Economic and business benefit of using cloud resources **only when needed**. *On-demand service* = a cloud characteristic where users **automatically provision and release** resources whenever required, **without human interaction** with the provider. *Eg:* e-commerce site gets extra servers during festival sale, releases after.

### 10 advantages (the 10 M skeleton) 📘
| # | Advantage | Key points / example |
|---|---|---|
| 1 | **Cost savings** | no upfront HW; traditional buys in advance & idle; startup avoids ₹15 lakh hardware ⇒ lower CapEx |
| 2 | **Pay-as-you-go** | per VM hour, GB, DB request, API call; eg 100 GB + 20 compute-hours ⇒ pay only that |
| 3 | **Elastic scalability** | high demand: add servers/storage/bandwidth; low: remove. Eg 5 servers normal → 50 on Diwali → 5 |
| 4 | **Faster time-to-market** | minutes vs weeks (buy, install OS, configure network, test) |
| 5 | **Improved utilisation** | CPU shared, memory efficient, storage grows only as needed |
| 6 | **Business agility** | launch app, new regional service, seasonal demand, test ideas |
| 7 | **High availability** | multi-DC; if one server fails another serves |
| 8 | **Global accessibility** | internet access, work from home, global collaboration |
| 9 | **Reduced IT management** | provider handles HW, updates, patches, backup, DR |
| 10 | **Supports innovation** | spin up test VM in minutes, test, delete |

**Economic benefits summary:** no upfront investment · pay for actual usage · instant provisioning · automatic scaling · less maintenance · HA & reliability · faster deployment · better utilisation · growth · global access.

**Real-life example (video streaming company):**
| Without on-demand | With on-demand |
|---|---|
| Buy servers for peak demand | Rent extra servers during release |
| Most idle after the event | Auto scale-down afterwards |
| High capital investment | Pay only for the extra used |
Result: lower cost, better performance, efficient utilisation.

**Limitations (slide 64):** unmanaged usage inflates cost · needs reliable internet · vendor lock-in · security/compliance concerns for sensitive workloads · performance varies with network latency.

**When demand outgrows provisioning (slide 63) → problems:** increased latency, request failures, timeouts, DB throttling, queue build-up, service degradation, higher cost, potential outages ⇒ providers need **capacity planning** *in addition to* automatic scaling. When demand grows exponentially, infrastructure must scale **horizontally**, distribute data/requests across many resources, replicate data for availability and auto-scale up/down to hold performance while controlling cost. *(This leads directly into T17.)*

🟡 **Scalability vs Elasticity (adjacent PYQ ◐ – full answer in §4 PYQ-A4).**

---

## 3.17 T17 — Penalty Costs for Exponential Demand 📘

### Concept
**Penalty cost** = cost incurred when available computing resources don't match actual user demand. If demand grows **exponentially**, fixed/delayed provisioning can't keep up ⇒ penalty cost rises rapidly.

### General formula (slide 66) 📘
```
Penalty Cost  ∝  ∫ | D(t) − R(t) | dt
D(t) = demand at time t,  R(t) = resources available at time t
```
If D = R at all times ⇒ penalty = 0. (Shortage = under-provisioning ⇒ lost customers/SLA penalties; excess = over-provisioning ⇒ wasted money. Both are "mismatch" costs.)

### Derivation for exponential demand (slides 67–68 — **likely 10 M derivation**) 📘
1. Demand grows exponentially: **D(t) = eᵗ**
2. Resources are provisioned after a fixed delay **tₚ** (they only ever catch up to what demand *was* tₚ ago): **R(t) = e^(t − tₚ)**
3. Shortage: D(t) − R(t) = eᵗ − e^(t−tₚ) = eᵗ(1 − e^(−tₚ))
4. Let **k₁ = (1 − e^(−tₚ))** (constant depending only on provisioning delay)
   ⇒ **D(t) − R(t) = k₁ eᵗ**
5. With **c** = cost per unit shortage ⇒ **Penalty Cost ∝ c · k₁ · eᵗ**

So the penalty cost itself grows **exponentially** with time. Symbols: *c* = cost per unit shortage; *k₁* = constant dependent on provisioning delay; *eᵗ* = exponential demand growth.

**Why does the gap keep growing?** Provider provisions based on *current* demand; by the time resources arrive demand has grown further; gap widens ⇒ penalty explodes.

**Typical situations:** viral social-media events · flash sales · online ticket booking · Black-Friday / festive shopping · breaking-news websites · sudden streaming-traffic spikes.

### 🟡 Extra insights & numerical (self-made — verify with your faculty's convention)
**Note on the final line:** the shortage *rate* is `k₁eᵗ`; integrating (∫k₁eᵗ dt = k₁eᵗ + const) gives cumulative penalty ∝ `c·k₁·eᵗ`, same exponential form — consistent with the slide. Over [0, T]: cumulative = c·k₁·(e^T − 1).

**Effect of delay tₚ on k₁ = 1 − e^(−tₚ):**
| tₚ | k₁ | Meaning |
|---|---|---|
| 0 (instant provisioning) | 0 | no shortage, zero penalty |
| 0.5 | 0.393 | |
| 1 | 0.632 | resources always ≈ 36.8 % of demand (R/D = e^(−tₚ)) |
| 2 | 0.865 | |
| → ∞ (never provisioned) | → 1 | all demand unmet |
**Key insight:** R(t)/D(t) = e^(−tₚ) is constant ⇒ with delay tₚ resources *permanently* lag by the same fraction while absolute shortage explodes. The only fixes: **reduce tₚ** (faster provisioning/auto-scaling, pre-warmed capacity, predictive scaling) or **provision ahead of demand** (capacity planning).

**Numerical X1.** tₚ = 1 unit, c = ₹1,000 per unit shortage. Find shortage and penalty rate at t = 3 and t = 5.
k₁ = 1 − e^(−1) = 1 − 0.3679 = **0.6321**.
- t = 3: D = e³ = 20.09; R = e² = 7.39; shortage = 12.70 (= 0.6321 × 20.09 ✔) ⇒ penalty rate = 1,000 × 12.70 = **≈ ₹12,700 per unit time**.
- t = 5: D = e⁵ = 148.41; shortage = 0.6321 × 148.41 = **93.81** ⇒ **≈ ₹93,810 per unit time**.
- Growth from t = 3 to t = 5 is e² ≈ **7.39 ×**.

**Numerical X2 (cumulative).** Same data, total penalty over t = 0 → 3: c·k₁(e³ − 1) = 1,000 × 0.6321 × 19.0855 = **≈ ₹12,065**.

**Real-world anchor (literature, beyond notes):** Animoto scaled from ~50 to ~3,500 servers in about 3 days — no fixed data centre could be planned for this; elasticity avoids the exponential penalty.

🟡 **Diagram to draw (D vs R curves):**
```
 Demand/
 Resources
   |                          D(t)=e^t  /
   |                                  /
   |                    R(t)=e^(t-tp)/ /
   |                              /  /
   |                          ..'  ,'     <- shaded gap = shortage = k1*e^t
   |                      ..''  ,'            (penalty ∝ area of gap)
   |               ..-''   ,-'
   |        ..--''  ,--''
   +--------------------------------------> time t
```
(R is the same curve as D shifted right by tₚ.)

**Exam tip:** 10 M = definition + integral formula + the 5-step derivation + causes + diagram. Always define k₁, c, tₚ.

---

# 4. PYQ SOLUTIONS

## 4.0 Honest summary of the PYQ scan (read first)

I read every page/screenshot of all available papers. **No question directly tests Module 2** (SLA/SLO/KPI/availability/penalty/cloud economics/pricing/penalty-cost). Likely reason: Module 2 (CO2) is new in the 2023 syllabus; older papers were Mod-1/Aneka/virtualisation/microservices/AWS heavy. So:
- **§4.1** solves the **6 adjacent PYQs** closest to Module 2 — tagged **◐**.
- **§4.2** is a table of PYQ-looking items I screened **out** (they belong to Module 1/other modules) — so you can verify my judgement.
- **§4.3** is a **🟡 self-made predicted question bank** with pointers/answers for Module 2 (not from official PYQ).

| Paper | Date | Marks | Mod-2 question? |
|---|---|---|---|
| ESE (Programme: Minors in Comp Eng, SVU 2020, Course 116m75E702) | Jan–Apr 2025 (dated 23-05-2025) | 100 | ❌ none (Q1 characteristics/virtualisation/XaaS/Aneka/microservices; Q2 SOA/MapReduce/deployment models/VM files & migration; Q3 Aneka fabric, microservices vs monolith, Docker; Q4 Aneka scheduling, EC2 instance types, Google AppEngine; Q5 Aneka, VM migration, S3, DC environment impact, AWS architecture, MBaaS) |
| ESE Dec 2022 (2UCE713) | Dec 2022 | 100 | ◐ adjacent only (see below) |
| ESE Nov–Dec 2021 (2UCE713) | Nov–Dec 2021 | 50 | ❌ none |
| ESE May–Jun 2021 (UCEC801 Distributed & Cloud Computing) | May–Jun 2021 | 50 | ◐ adjacent (availability MCQ, provisioning) |

## 4.1 Adjacent PYQs, grouped by topic, solved exam-style

---
### ▸ Topic T12 (Availability) — ◐ adjacent

#### PYQ-A1 — *May–June 2021 ESE, Q1(A)(V), 2 M (match the following)*
> Match: 1) Reliability — A) How easy it is to service the system; 2) Availability — B) How long a system can operate without a breakdown; 3) Serviceability — C) The percentage of system uptime. Options: a) 1-A,2-C,3-B  b) 1-B,2-A,3-C  c) 1-A,2-B,3-C  d) 1-B,2-C,3-A

**Solution**
- Reliability = how long a system can operate **without breakdown** → **B**
- Availability = **percentage of system uptime** → **C** (this is exactly the SLA availability formula `Uptime/(Uptime+Downtime) × 100`)
- Serviceability = **how easy it is to service** the system → **A**

**Correct option: (d) 1-B, 2-C, 3-A.** *(Note: options a/b/c are all wrong.)*
(Link to Module 2: reliability ↔ MTBF; serviceability ↔ MTTR; availability = MTBF/(MTBF+MTTR).)

---
### ▸ Topic T14 (Economic viewpoint) — ◐ adjacent

#### PYQ-A3 — *Dec 2022 ESE, Q2(A)(ii), 5 M*
> What is the major advantage of cloud computing?

**Solution (5 M)**
The **major advantage** is **cost-efficient, on-demand access to IT resources — converting upfront capital expenditure into pay-per-use operating expenditure** (the economic viewpoint of cloud).
Explanation points:
1. **No upfront investment (CapEx → OpEx):** no purchase of servers, storage, network, DC; pay monthly for what is used. *Eg:* ₹50 lakh DC vs ≈ ₹50,000/month VMs.
2. **Pay-as-you-go (utility) billing** – 5 h VM @ ₹10/h = ₹50.
3. **Elasticity / scalability** – scale 10 → 100 VMs for a sale and back; no over-provisioning.
4. **Better utilisation** – virtualisation shares hardware; traditional servers idle at 10–20 %.
5. **Faster time-to-market and agility** – VMs in minutes instead of weeks.
6. **Reduced management burden, high availability, global access.**
Conclusion: these together lower cost and increase business agility, which is why cloud adoption is chosen over on-premise IT.
*(Answer constructed from Module 2.2 notes; the paper doesn't give a key — if the faculty expects "scalability/elasticity" or "reduced cost", the above covers all.)*

---
### ▸ Topic T15 (Utility pricing) — ◐ adjacent

#### PYQ-A2 — *Dec 2022 ESE, Q2(A)(i), 5 M*
> What is utility computing? Describe the vision introduced by cloud computing.

**Solution (5 M)**
**Utility computing:** a service-provisioning model in which computing resources (compute, storage, applications) are supplied **on demand** and **billed according to usage**, exactly like public utilities (electricity, water, gas, telephone). Users **don't own infrastructure**; they pay for CPU-hours, storage, bandwidth etc. (= **utility pricing / pay-as-you-go**).

| Utility | Paid by |
|---|---|
| Electricity | kWh |
| Water | litres |
| Cloud | CPU hours, GB, bandwidth, API calls |

**Vision introduced by cloud computing:**
1. **Computing as a utility** – IT delivered as a service over the Internet, "plug in and pay" (computing as the 5th utility after water, electricity, gas, telephone — Buyya's wording 🟡 not on the slides).
2. **Everything as a service** – infrastructure (IaaS), platform (PaaS), software (SaaS) available on demand.
3. **Elastic, virtually infinite resources** – scale up/down automatically.
4. **No upfront cost** – CapEx → OpEx; pay only for actual use; small start-ups can use enterprise-grade infrastructure.
5. **Ubiquitous access** – anywhere, any device; the user focuses on business, provider handles operation.
Diagram: *User → Request resources → Provider allocates → Metering → Billing → Invoice* (the utility-pricing architecture of §3.15).

---
#### PYQ-A6 — *Dec 2022 ESE, Q5(v), 5 M (write notes on any four)*
> Spot Cloud

**Solution (5 M)** — 🟡 *The notes mention spot/preemptible instances (Mod 2.2 slide 22) but do not define "SpotCloud"; the answer below combines notes + general knowledge. Cover both senses to be safe.*
1. **SpotCloud** – an online **marketplace for buying/selling unused cloud capacity** (providers sell spare VMs; buyers purchase cheap capacity), i.e., a cloud-capacity clearing house.
2. **Spot (preemptible) instances** – unused capacity offered at a **large discount** (AWS Spot, Azure Spot, GCP Preemptible/Spot) — the provider can reclaim it with short notice.
3. **Economics (Mod 2.2):** *optimise IT spend* → use spot instances for **non-critical, fault-tolerant** jobs (batch, rendering, testing); reserved instances for predictable load; on-demand for the rest.
4. **Pros:** much cheaper, uses idle capacity (better utilisation for provider), fits utility pricing. **Cons:** can be interrupted; unsuitable for mission-critical or low-latency services; price/availability varies.
5. **Link to SLA:** spot capacity generally carries no availability guarantee, so it does not suit applications that need a 99.9 %+ SLA.

---
### ▸ Topic T16 (Value of on-demand services) — ◐ adjacent

#### PYQ-A4 — *Dec 2022 ESE, Q1(ii), 5 M (solve any four)*
> Compare Scalability and Elasticity.

**Solution (5 M)**
| Basis | Scalability | Elasticity |
|---|---|---|
| Meaning | Ability of a system to **handle growing workload** by adding resources (long-term capacity growth) | Ability to **automatically add AND remove** resources to match **current** demand (short-term, dynamic) |
| Direction | Mostly scale-**up/out** | Scale **out and in** (both) |
| Time scale | Planned, long-term | Real-time / rapid |
| Automation | Often manual/planned | Automatic (auto-scaling) |
| Goal | Support growth | Avoid over- and under-provisioning, save cost |
| Cost link | Capacity increase | Pay only for what's used (utility pricing) |
| Example | Moving app from 10,000 to 1,00,000 users by adding servers | Online store: 5 servers normally → 50 on Diwali → back to 5 |
Types of scaling: **vertical** (bigger machine: CPU/RAM) vs **horizontal** (more instances) — fig. in Mod 2.2 slide 16.
Conclusion: scalability is the *capability to grow*; elasticity is *dynamically matching resources to demand*, which is what creates the economic value of on-demand services.

---
#### PYQ-A5 — *May–June 2021 ESE, Q1(B)(vii), 2 M*
> Compare demand-driven resource provisioning and event-driven resource provisioning.

**Solution (2 M)** 🟡 *(standard Hwang/Jin definitions; not in the Module 2 notes)*
| Demand-driven | Event-driven |
|---|---|
| Resources added/removed **dynamically when measured load crosses a threshold** (reactive, e.g. CPU > 80 % ⇒ add VM) | Resources provisioned **in advance for a known/expected event or time** (proactive, e.g. festival sale, scheduled campaign) |
| Based on **current utilisation** | Based on **calendar/predicted workload** |
| Risk: provisioning delay ⇒ shortage during sudden spikes (→ the penalty-cost problem of §3.17) | Risk: over-provisioning if the event is smaller than predicted |

---

## 4.2 Screened-out PYQ items (looked related, but belong elsewhere — for transparency)
| PYQ | Paper | Why excluded |
|---|---|---|
| Essential characteristics of cloud computing (5 M) | Jan–Apr 2025 Q1(i) | Module 1 fundamentals (on-demand self-service/measured service are *mentioned* in Mod 2.2 but question is Mod 1) |
| XaaS (5 M); Compare Private vs Public cloud; SaaS benefits business | Jan 2025 / Dec 2022 | Module 1 service/deployment models |
| Impact of cloud data centre on environment (5 M) | Jan 2025 Q5(iv) | Data-centre/green topic, not SLA/economics |
| Power management techniques, DVFS, server consolidation, hardware vs software power management | Dec 2022 Q4(ii); Nov–Dec 2021 | Power/energy topic (not cost-modelling in syllabus) |
| Hybrid deployment of Aneka – dynamic provisioning | Nov–Dec 2021 Q4 | Aneka framework |
| Cloud federation (legal issues, InterCloud levels) | Dec 2022; Nov–Dec 2021 | Not in Mod 2 syllabus |
| Amazon SimpleDB vs RDS; EC2 instance types; S3 | 2021/2025 | AWS service details, not SLA |
| Public vs private clouds compile table | May–Jun 2021 Q3 OR | Module 1 deployment models |

---

## 4.3 🟡 SELF-MADE PREDICTED QUESTION BANK FOR MODULE 2 (NOT from official PYQ)

**How to use:** Theory answers are in §3 (section number shown). Numericals are solved fully below. Marks are my estimate.

### Theory — 5 M
| # | Question | Answer in |
|---|---|---|
| 1 | Define SLA. Explain need and characteristics of a good SLA. | §3.1 |
| 2 | Explain advantages of SLA (any 5). | §3.1 |
| 3 | Explain SLA lifecycle with diagram. *(deck's own exam Q)* | §3.2 |
| 4 | Differentiate SLA, SLI and SLO. *(deck's own exam Q)* | §3.5 |
| 5 | Discuss SLA monitoring. *(deck's own exam Q)* | §3.8, §3.13 |
| 6 | Explain types of SLA with example/diagram. | §3.4 |
| 7 | Differentiate functional and non-functional SLA requirements. | §3.6 |
| 8 | What are KPIs? Explain any four cloud performance metrics with formulae. | §3.7 |
| 9 | Explain types of audit / audit logs. | §3.8 |
| 10 | SLA requirements for IaaS (or PaaS or SaaS). | §3.9 |
| 11 | Explain limitations of SLA. | §3.11 |
| 12 | Explain penalty models for SLA violation. | §3.13 |
| 13 | What is the "number of nines"? Tabulate downtime. | §3.12 |
| 14 | CapEx vs OpEx in cloud. | §3.14 |
| 15 | Explain utility pricing with example. | §3.15 |
| 16 | List advantages & disadvantages of pay-as-you-go. | §3.15 |
| 17 | Explain the value of on-demand services. | §3.16 |
| 18 | What is penalty cost in cloud? When does it occur? | §3.17 |
| 19 | Why does SLA not fully compensate customer losses? Give example. | §3.11 |

### Theory — 10 M
| # | Question | Answer in |
|---|---|---|
| 20 | Explain SLA contents with diagram. | §3.3 |
| 21 | Explain SLA requirements w.r.t. IaaS, PaaS and SaaS; give comparison table and shared-responsibility model. | §3.9 |
| 22 | Explain the five phases of cloud SLA lifecycle. | §3.2 |
| 23 | Discuss in detail the objectives of cloud economics from the economic viewpoint. | §3.14 |
| 24 | Explain utility pricing: working, characteristics, advantages, disadvantages, examples in AWS/Azure/GCP. | §3.15 |
| 25 | Derive the penalty cost for exponentially growing demand with provisioning delay. | §3.17 |
| 26 | Explain SLA violation: causes, detection, penalty models, best practices. | §3.13 |
| 27 | Compare cloud SLAs of AWS, Azure and GCP. | §3.10 |

### Numericals (full solutions)

**Q28 (5 M).** A cloud service ran for a 31-day month with a total outage of 90 minutes. Find availability. If the SLA promised 99.95 %, is it violated?
Total = 31 × 24 × 60 = 44,640 min. A = (44,640 − 90)/44,640 × 100 = 44,550/44,640 × 100 = **99.798 %**. Allowed downtime at 99.95 % = 0.0005 × 44,640 = 22.32 min. 99.798 < 99.95 (90 > 22.32) ⇒ **Violated.**

**Q29 (5 M).** Find the maximum permitted downtime per year for 99.5 %, 99.9 %, 99.99 % and 99.999 %.
T = 8,760 h. D = (100 − A)/100 × 8,760 h:
99.5 % → 43.8 h (1.825 d) | 99.9 % → 8.76 h | 99.99 % → 0.876 h = 52.56 min | 99.999 % → 0.0876 h = 5.256 min.

**Q30 (10 M, mixed).** Monthly bill ₹2,50,000 (30 days). SLA: ≥ 99.9 % → no credit; 99.0–99.9 % → 10 % credit; < 99.0 % → 30 % credit. Measured downtime = 6 hours.
- T = 720 h; A = (720 − 6)/720 × 100 = 714/720 × 100 = **99.167 %**.
- Allowed = 0.72 h = 43.2 min; actual 360 min ⇒ **violated**.
- 99.0 ≤ 99.167 < 99.9 ⇒ **10 % credit** = 2,50,000 × 10/100 = **₹25,000**.
- Comment: if the loss from the outage was ₹10 lakh, the credit covers only 2.5 % (limitation T11).

**Q31 (5 M).** A web service handles 5,00,000 requests, of which 1,250 fail. Error rate? If the SLO is < 0.2 %, is it met?
Error rate = 1,250/5,00,000 × 100 = **0.25 %** > 0.2 % ⇒ **SLO not met.**

**Q32 (5 M).** A server transfers 12 GB in 4 minutes. Throughput in MB/s and Mbps? (1 GB = 1000 MB)
12 GB = 12,000 MB; 4 min = 240 s ⇒ 12,000/240 = **50 MB/s** = 50 × 8 = **400 Mbps**.

**Q33 (5 M).** SLA availability 99.99 % for a service costing ₹8,00,000/month. Customer suffers 12 min downtime in a 30-day month; policy: each full minute above allowed downtime ⇒ 0.5 % credit (cap 100 %).
Allowed = 4.32 min; excess = 12 − 4.32 = 7.68 min ⇒ 7 full minutes ⇒ 3.5 % ⇒ 8,00,000 × 3.5/100 = **₹28,000**. *(Policy invented for practice.)*

**Q34 (5 M, series/parallel).** Three-tier app: web 99.9 %, app 99.9 %, DB 99.9 % in series. (a) Availability? (b) If web tier is duplicated (parallel pair) what is the new availability?
(a) 0.999³ = 0.997003 ⇒ **99.70 %**.
(b) Web pair = 1 − (0.001)² = 0.999999. Total = 0.999999 × 0.999 × 0.999 = 0.998001 ⇒ **99.80 %** — redundancy helps, but the remaining single points of failure limit gains.

**Q35 (5 M, break-even).** Cloud VM ₹12/h; own server total cost ₹2,40,000 over 3 years. Break-even utilisation?
3 yrs = 26,280 h. Break-even hours = 2,40,000/12 = 20,000 h ⇒ 20,000/26,280 = **76.1 %**. Cloud wins below 76 %.

**Q36 (5 M, elasticity saving).** Normal load 5 VMs, sale (4 days) 40 VMs, VM = ₹8/h, month = 30 days. Cost with elastic cloud vs fixed 40 VMs.
Elastic: base 5 × 8 × 720 = ₹28,800; extra 35 × 8 × 96 h = ₹26,880 ⇒ **₹55,680**. Fixed 40 VMs: 40 × 8 × 720 = **₹2,30,400**. Saving = ₹1,74,720 (**75.8 %**).

**Q37 (10 M, exponential penalty).** Demand D(t) = e^t, provisioning delay tₚ = 2, penalty c = ₹500 per unit shortage per unit time. (a) k₁ (b) shortage and penalty rate at t = 4 (c) fraction of demand unmet.
(a) k₁ = 1 − e^(−2) = 1 − 0.1353 = **0.8647**.
(b) D(4) = e⁴ = 54.60; R(4) = e² = 7.389; shortage = 47.21 (= 0.8647 × 54.60 ✔) ⇒ penalty rate = 500 × 47.21 = **≈ ₹23,605 per unit time**.
(c) Unmet fraction = (D−R)/D = k₁ = **86.5 %** (resources are only e^(−2) = 13.5 % of demand at all times).

---

## 4.4 Last-minute revision sheet (one page)

```
SLA  = contract: quality + responsibilities + penalties          SLI = measure | SLO = target | SLA = contract
TYPES: Customer-based (1 cust, all svcs) | Service-based (1 svc, all cust) | Multi-level (Corporate>Customer>Service)
CONTENTS (15): Svc desc, Scope, Availability, Metrics, Roles, SLOs, Monitoring, Security, Backup/DR,
               Incident, Change, Violations/Penalties, Exclusions, Review, Termination
LIFECYCLE (5): Definition → Publishing/Discovery → Negotiation → Operation(monitor+enforce) → De-commission
KPIs: Availability, Response time, Latency, Throughput, Error rate, Utilisation, Reliability(MTBF), Scalability, Bandwidth, CSAT

A(%)      = (T − D)/T × 100  = Up/(Up+Down) × 100
D allowed = (100 − A) × T / 100            30d = 720 h = 43,200 min | 1 yr = 8,760 h = 5,25,600 min
Penalty   = Bill × % / 100                 Violated if actual A < SLA A (or actual D > allowed D)
Nines:  99% 7.2h/mo, 3.65d/yr | 99.9% 43.2m/mo, 8.76h/yr | 99.95% 21.6m, 4.38h | 99.99% 4.32m, 52.56m | 99.999% 25.92s, 5.26m
Penalty models: Credit | Refund | Free extension | Discount on future bill

ECONOMICS: 6 objectives = ↓cost | CapEx→OpEx | ↑utilisation | agility+scalability | ↓complexity | optimise spend
UTILITY PRICING = PAYG; 5 chars = PAYG, no upfront, flexible, measured, elastic; cons = unpredictable bill, idle cost, egress, lock-in
ON-DEMAND: self-provision/release, no human interaction; 10 advantages; needs capacity planning
EXPONENTIAL PENALTY: Penalty ∝ ∫|D−R|dt ; D=e^t, R=e^(t−tp) ; D−R = e^t(1−e^(−tp)) = k1 e^t ; Penalty ∝ c·k1·e^t
```

---
*End of file. Tags: 📘 = from notes · ★ = direct PYQ (none exist for Mod 2) · ◐ = adjacent PYQ · 🟡 = self-made/predicted.*
