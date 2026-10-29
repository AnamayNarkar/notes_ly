# Advanced Cloud Computing (216U01E731) — Module 1: Introduction to Cloud Computing (6 hrs, CO1)

> **Syllabus 1.1** – Introduction to cloud computing, Computing platforms and technologies, Types of clouds, Cloud service models, Cloud applications, Virtualization concepts, Types of virtualization.
> **Syllabus 1.2** – *#Self-learning:* Hardware support for Processor, Memory, I/O virtualization at Intel.
> **CO1** – Describe basics of cloud computing and its fundamentals.
> **Marks context** – ESE = 50 marks (IA 20 + ISE 30 are internal). Books: Buyya *Mastering Cloud Computing* (Ch 1, 3, 9), Buyya–Broberg–Goscinski *Cloud Computing: Principles & Paradigms*, Vette *Cloud Computing: A Practical Approach*.

---

## 0. HOW TO READ THIS FILE (legend)

| Tag | Meaning |
|---|---|
| **[N]** | Taken from your notes (`Chapter 1.pptx`, 74 slides) |
| **[P]** | Taken from a previous-year question paper (PYQ) |
| **[★]** | **My addition** – NOT in your notes / NOT in an official PYQ. Added from the textbooks (Buyya / Hwang) or my own prediction. Verify against your textbook if your teacher is strict. |
| 🔴 | This question type **has appeared** in a PYQ for this topic |
| 🟡 | Has **not** appeared, but I judge it plausible (my prediction → [★]) |

**PYQ codes used everywhere**

| Code | Paper | Marks | Note |
|---|---|---|---|
| **P25** | SVU Jan–Apr 2025 (ESE, 23-05-2025) – *Cloud Computing*, Minors, 116m75E702 | 100 | Old SVU-2020 syllabus |
| **P22** | KJSCE ESE Dec 2022 – *Cloud Computing Emerging Technologies*, 2UCE713 | 100 | |
| **P21N** | KJSCE ESE Nov–Dec 2021 – 2UCE713 | 50 | |
| **P21M** | KJSCE ESE May–Jun 2021 – *Distributed & Cloud Computing*, UCEC801 | 50 | Hwang-textbook style |

> ⚠️ **IMPORTANT SCOPE WARNING.** All four PYQs are from *older* syllabi. Your **new** syllabus (216U01E731, DRAFT) has **no Aneka, no SOA, no cloud federation, no DVFS/power management, no web-services (WS-*/REST)**. About **⅓ of old-paper marks were Aneka**. I have **excluded** those (list in §4.0) and solved only questions that map to Module 1. Module 1 in the PYQs is **100% theory – there are NO numericals** (numericals in this subject come in Module 2: SLA/availability/penalty).

---

## 1. TOPIC MAP (tree)

```
MODULE 1 : INTRODUCTION TO CLOUD COMPUTING
│
├── 1.1  CORE SYLLABUS
│   │
│   ├── A. INTRODUCTION TO CLOUD COMPUTING
│   │   ├── A1  Definition  (utility analogy – electricity)            [N]
│   │   ├── A2  Vision: IT as utility, "Global Cloud Marketplace"      [N][P22]
│   │   │        └─ Utility computing, who benefits (enterprise,
│   │   │           start-ups, developers, end users) + Little Fluffy Toys
│   │   ├── A3  NIST definition + NIST visual model                    [N][P25]
│   │   │        ├─ 5 Essential characteristics (on-demand, broad net,
│   │   │        │   pooling, rapid elasticity, measured service)
│   │   │        ├─ 3 Service models
│   │   │        └─ 4 Deployment models
│   │   ├── A4  Cloud Reference Model (layers)                         [P21N][★ book]
│   │   ├── A5  Core benefits (cost/CapEx→OpEx, speed, scale,
│   │   │       productivity, reliability); scalability vs elasticity  [N][P22]
│   │   └── A6  Evolution: Web 1.0 → 2.0 → 3.0                         [P22][P21N]
│   │
│   ├── B. COMPUTING PLATFORMS AND TECHNOLOGIES
│   │   ├── B1  PLATFORMS  (hyperscalers)                              [N]
│   │   │   ├─ AWS   : EC2, S3, RDS, DynamoDB, Lambda, VPC, CloudFront,
│   │   │   │          CloudWatch, IAM, ELB  → EC2 instance types, S3,
│   │   │   │          AWS architecture, SimpleDB vs RDS               [P25][P21N]
│   │   │   ├─ Azure : VMs, Blob, SQL DB, Cosmos DB, Functions, VNet,
│   │   │   │          LB, Azure AD, Monitor, App Service  (+ Hyper-V) [P22][P21M]
│   │   │   ├─ GCP   : Compute Engine, GKE, Cloud Storage, Cloud SQL,
│   │   │   │          BigQuery, Functions, VPC, LB, Vertex AI
│   │   │   │          → Google App Engine (arch + components)         [P25][P22][P21N]
│   │   │   └─ Others: IBM Cloud, Oracle OCI, Alibaba Cloud
│   │   └── B2  TECHNOLOGIES  (12 in notes)                            [N]
│   │       ├─ 1 Virtualization (VMware, Hyper-V, KVM)                 [P21M]
│   │       ├─ 2 Containerization (Docker, Podman)  → Docker cmds      [P25][P22]
│   │       ├─ 3 Orchestration (Kubernetes)
│   │       ├─ 4 Cloud storage (object / block / file)
│   │       ├─ 5 Serverless (Lambda, Functions)
│   │       ├─ 6 Microservices  (vs Monolith)                          [P25]
│   │       ├─ 7 DevOps & CI/CD (Jenkins, GitHub Actions, GitLab CI)   [P22]
│   │       ├─ 8 SDN
│   │       ├─ 9 AI / ML
│   │       ├─ 10 Big-data analytics (Hadoop, Spark, BigQuery)
│   │       ├─ 11 Edge computing
│   │       └─ 12 IoT
│   │
│   ├── C. TYPES OF CLOUDS
│   │   ├── C1  DEPLOYMENT MODELS                                      [N]
│   │   │   ├─ Public   ├─ Private   ├─ Hybrid   ├─ Multi-cloud   └─ Community
│   │   │   └─ Compare public vs private; hybrid vs multi-cloud        [P25][P22][P21M]
│   │   └── C2  SERVICE MODELS ("as-a-service stack")                  [N]
│   │       ├─ IaaS   (analogy: empty plot of land)
│   │       ├─ PaaS   (unfurnished apartment) → PaaS categories        [P22][P21N]
│   │       ├─ SaaS   (hotel room)             → SaaS business benefits[P22]
│   │       └─ XaaS   (Everything-as-a-Service) → MBaaS, MaaS          [P25][P22][P21N]
│   │
│   ├── D. CLOUD APPLICATIONS                                          [N]
│   │   ├─ Examples (email, storage, office, video-conf, CRM, streaming)
│   │   ├─ Characteristics ─ Advantages ─ Disadvantages
│   │   ├─ Cloud-native architecture (microservices, containers, APIs)
│   │   ├─ Trends (Gen-AI hybrid, edge integration)
│   │   └─ Related: impact of cloud data centres on environment; SpotCloud [P25][P22] (borderline)
│   │
│   ├── E. VIRTUALIZATION CONCEPTS                                     [N]
│   │   ├─ E1  Definition + Need (without vs with)
│   │   ├─ E2  Host / Guest (VM) / Hypervisor (VMM)
│   │   ├─ E3  Machine reference model of execution virtualization     [P22][★ book]
│   │   │        (ISA – ABI – API, privilege rings)
│   │   ├─ E4  Levels of virtualization (ISA, HAL, OS, Library, App)   [P25][★ book]
│   │   ├─ E5  Implementation styles: full / para / hardware-assisted  [P21M][P22]
│   │   ├─ E6  HYPERVISORS
│   │   │   ├─ Type 1 bare-metal (ESXi, Hyper-V, KVM, Xen)             [P22][P21M]
│   │   │   └─ Type 2 hosted (VirtualBox, VMware Workstation, Parallels)
│   │   ├─ E7  VM files (.vmx, .vmdk…) and VM migration (cold/live)    [P25][P21M]
│   │   ├─ E8  Advantages / Disadvantages of virtualization            [N]
│   │   └─ E9  Applications of virtualization                          [N]
│   │
│   └── F. TYPES OF VIRTUALIZATION                                     [N]
│       ├─ 1 Server  (server sprawl → consolidation)                   [P21N]
│       ├─ 2 Desktop (VDI)
│       ├─ 3 Network
│       ├─ 4 Storage (SAN vs NAS)                                      [P22][P21M]
│       ├─ 5 Application (App-V, ThinApp)
│       └─ 6 OS-level / Containers (Docker, LXC, Podman)               [P25][P22]
│
└── 1.2  SELF-LEARNING : HARDWARE SUPPORT FOR VIRTUALIZATION AT INTEL  [P21N]
    ├─ Processor  → Intel VT-x (and VT-i for Itanium)
    ├─ Memory     → EPT (Extended Page Tables)
    ├─ I/O        → VT-d (DMA remap + interrupt remap)
    └─ I/O sharing→ VT-c (VMDq, SR-IOV)   + physical vs logical core
```

---

## 2. TOPIC-WISE QUESTION TYPES  (🔴 = appeared in PYQ, 🟡 = my prediction [★])

Columns: **S** = short note (2–5 marks) · **L** = long answer (10 marks) · **Dg** = diagram-based · **Cmp** = compare/differentiate · **Num** = numerical · **Obj** = MCQ / match / fill-blank (1–2 marks) · **Ex** = list/examples · **Pr** = practical/commands

| # | Topic | S | L | Dg | Cmp | Num | Obj | Ex | Pr |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Definition / utility computing / vision | 🔴 P22 (×2) | 🟡 | 🟡 | – | – | 🟡 | – | – |
| 2 | NIST model & essential characteristics | 🔴 P25 | 🟡 | 🟡 | – | – | 🟡 | – | – |
| 3 | Cloud reference model | 🔴 P21N | 🟡 | 🔴 (implied) | – | – | – | – | – |
| 4 | Benefits; scalability vs elasticity | 🔴 P22 (×2) | – | – | 🔴 P22 | 🟡 [★] | – | – | – |
| 5 | Web 1.0/2.0/3.0 | 🔴 P22 | – | – | 🔴 P21N | – | – | 🔴 P22 (examples) | – |
| 6 | AWS (EC2, S3, architecture, SimpleDB/RDS) | 🔴 P25 (×2) | 🔴 P25 | 🔴 P25 | 🔴 P21N | – | – | 🔴 P25 | – |
| 7 | Google App Engine / GCP | – | 🔴 P25, P22, P21N | 🔴 P25 | – | – | 🔴 P21N (2m) | 🔴 P25 (list GCP svcs) | – |
| 8 | Azure / Microsoft / Hyper-V | – | 🔴 P22 | 🔴 P22 | – | – | 🔴 P21M | – | – |
| 9 | Technologies: Microservices | 🔴 P25 | 🔴 P25 | 🟡 | 🔴 P25 (vs monolith) | – | – | – | – |
| 10 | Technologies: Docker / containers | 🔴 P22 | 🔴 P25 | 🟡 | 🟡 (vs VM) | – | – | – | 🔴 **P25 (5 Docker cmds)** |
| 11 | Technologies: Jenkins / CI-CD | 🔴 P22 | – | 🟡 | – | – | – | – | – |
| 12 | Key enabling technologies | 🔴 P21M (2m) | – | – | – | – | – | – | – |
| 13 | Deployment models | – | 🔴 P25 | 🟡 | 🔴 P22, P21M(10m) | – | – | 🔴 P25 | – |
| 14 | Service models IaaS/PaaS/SaaS | 🔴 P22 (SaaS), P21N | 🔴 P22 (PaaS) | 🟡 | 🟡 | – | – | 🔴 | – |
| 15 | XaaS, MBaaS, MaaS | 🔴 P25, P22 (×2) | 🔴 P21N | – | – | – | – | – | – |
| 16 | Cloud applications / env. impact / SpotCloud | 🔴 P25, P22 (borderline) | – | – | – | – | – | – | – |
| 17 | Virtualization basics, reference model, levels | 🔴 P25, P21M(2m), P21N(1m) | 🔴 P22, P21M | 🔴 P22 | 🔴 P21M | – | 🔴 P21N | – | – |
| 18 | Hypervisors: Xen, VMware, Hyper-V | 🔴 P22 (×2) | 🔴 P22 | 🔴 P22 | – | – | – | – | – |
| 19 | VM files (.vmx) & VM migration | 🔴 P25 | 🔴 **P25 (×2)** | 🟡 | – | – | 🔴 P21M | – | – |
| 20 | Types of virtualization (SAN/NAS, server consolidation) | 🔴 P22, P21N | – | 🟡 | 🔴 P22 | 🟡 [★] | 🔴 P21M | – | – |
| 21 | Intel VT-x / EPT / VT-d / VT-c | 🟡 | 🟡 | 🟡 | 🔴 P21N (physical vs actual core) | – | 🔴 **P21N (match)** | – | – |

**Key patterns to notice**
1. **Cloud platforms & virtualization are the heavy hitters** (10-mark questions). Every paper has a Google AppEngine or AWS question and a virtualization question.
2. **Compare/differentiate** is very common (public vs private appeared in *3 different papers*). Always prepare tables.
3. **Diagrams are mandatory** ("Draw neat diagrams" is in every instruction box).
4. **No numericals** in Module 1. I still added 3 practice numericals [★] in §3.20/§3.4 because "server consolidation" and "CapEx vs OpEx" are natural numerical hooks.
5. **Self-learning (Intel VT)** was examined as a 2-mark *Match the following* in P21N → cheap marks, learn the 4 pairs.

---

## 3. TOPIC-BY-TOPIC DETAILED BREAKDOWN

### 3.1 Introduction & Definition  [N]
**Explain simply.** Cloud computing = renting computing (servers, storage, databases, networking, software) over the Internet, paying only for what you use — **like electricity**: you plug in, you don't own the power plant.

- Anyone with a credit card can provision virtual hardware, runtime environments and services. [N]
- The whole stack becomes a set of *utilities* that can be composed → systems deployed in **hours, not days**, near-zero maintenance. [N]
- **Long-term vision**: IT services traded as utilities in an **open market, without technological and legal barriers**. [N]
- Providers: AWS, Azure, Google Cloud.

**Exam format (5 marks):** definition (2 lines) → electricity analogy → 4 bullets (on-demand, pay-as-you-go, no CapEx, internet-accessible) → small cloud diagram.

```
                   Internet cloud
        ┌─────────────────────────────────────┐
 User ──┼─►  Hardware   Software   Network    │
 (pays) │    Storage    Service               │
   ▲    └─────────────────────────────────────┘
   └────── paid services / submit requests ───────  (Fig 1.18 in notes)
```

### 3.2 Cloud vision, Utility computing, Global Cloud Marketplace  [N][P22]
**Utility computing**: computing resources are *metered* and billed like water/electricity; the user pays per use, the provider manages everything.

**The vision (Fig 1.1 in slide 9)** – a **Global Cloud Marketplace** where:
- Consumers: "I need to grow my infrastructure but don't know for how long", "I can't invest in infrastructure, just started my business", "I want to focus on application logic, not maintenance/scalability", "I want to access/edit my documents from everywhere".
- Providers: "I have lots of infrastructure to rent", "I have surplus infrastructure to make use of", "I have infrastructure & middleware and can host applications", "I provide application services".
- All meet in the marketplace, trade IT as utility.

**Who benefits [N]:** large enterprises (offload activities) · start-ups (ideas → business quickly, no up-front cost) · developers (business logic, not infrastructure) · end users (documents anywhere, any device).
**Example [N]:** *Little Fluffy Toys* (London) built a bicycle-rental info widget on **Google AppEngine** and reached the market in **one week**.

### 3.3 NIST definition, Essential characteristics, NIST model  [N][P25]
**NIST definition [N]:** *"Cloud computing is a model for enabling ubiquitous, convenient, on-demand network access to a shared pool of configurable computing resources (networks, servers, storage, applications, services) that can be rapidly provisioned and released with minimal management effort or service provider interaction."*

**5 Essential characteristics** (slide 13 diagram shows these; names from NIST) :

| Characteristic | Meaning (write 1–2 lines) |
|---|---|
| **On-demand self-service** | User provisions servers/storage automatically via portal/API, no human at the provider |
| **Broad network access** | Resources available over the network via standard mechanisms (phones, laptops, tablets) |
| **Resource pooling** | Provider's resources serve many tenants (multi-tenant) using virtualization; location is abstracted |
| **Rapid elasticity** | Scale out/in quickly, often automatically; capacity appears unlimited |
| **Measured service** | Usage metered (storage, CPU hrs, bandwidth) → pay-per-use, transparency |

```
┌──────────────────────────────────────────────────────────────────┐
│ ESSENTIAL   [Broad Network][Rapid Elasticity][Measured][On-Demand]│
│ CHARACTER-  [                 Resource Pooling                  ] │
├──────────────────────────────────────────────────────────────────┤
│ SERVICE     [   SaaS   ]      [   PaaS   ]      [   IaaS   ]      │
│ MODELS                                                           │
├──────────────────────────────────────────────────────────────────┤
│ DEPLOYMENT  (Public)    (Private)    (Hybrid)    (Community)     │
│ MODELS                                                           │
└──────────────────────────────────────────────────────────────────┘
```
**Exam format (5 marks, P25):** one-line intro → table/bullets of 5 characteristics with 1 line each → NIST layered diagram. Marks mostly for naming all five + meaning.

**Cube view [N slide 14]:** Service-delivery models (SaaS/PaaS/IaaS) on one axis × deployment models (Public/Hybrid/Private) on another × application domains (HPC, analytics, finance, web, other). Examples on cube: *SaaS-Public-CRM*, *PaaS-Public-Web*, *IaaS-Hybrid-Analytics*.

### 3.4 Benefits, Scalability vs Elasticity  [N][P22]
**Core benefits [N]:** Cost efficiency (CapEx→OpEx) · Speed & agility (minutes) · Global scale · Productivity (no racking and stacking, patching) · Reliability (backup, DR, business continuity).

**Scalability vs Elasticity (P22 Q1ii – 5 marks)** — write as table:

| Aspect | Scalability | Elasticity |
|---|---|---|
| Meaning | Ability to handle *growing* workload by adding resources | Ability to *automatically add and remove* resources to match the *current* demand |
| Time-scale | Long-term, planned growth | Short-term, real-time fluctuations |
| Direction | Mostly increasing (up/out) | Both increase **and** decrease |
| Mechanism | Manual or planned (vertical/horizontal) | Automatic (auto-scaling policies) |
| Cost aspect | Capacity ready for growth | Pay only for what is used → avoids over/under-provisioning |
| Example | Adding more DB servers as the company grows over years | E-commerce site scaling to 100 servers during a flash sale, back to 10 afterwards |

**[★] Practice numerical (elasticity):** Base load = 10 servers; a 2-hr/day peak needs 100 servers.
Fixed provisioning for peak: 100 × 24 = **2400 server-hr/day**. Elastic: 10×22 + 100×2 = **420 server-hr/day**. Saving = (2400−420)/2400 = **82.5 %**.

**[★] Practice numerical (CapEx vs OpEx):** Own server ₹6,00,000 upfront + ₹10,000/month running; cloud VM ₹25,000/month. Break-even: 6,00,000 + 10,000m = 25,000m → **m = 40 months**. Needing it < 40 months ⇒ cloud cheaper (ignoring resale, elasticity, staff).

### 3.5 Web 1.0 / 2.0 / 3.0  [P22][P21N]
**Web 2.0 (Buyya Ch.1):** brings interactivity and flexibility into web pages, giving web access to functions normally found in desktop applications, using **XML, AJAX, Web Services**, etc. *Major revolution:* from static **read-only** pages to a **dynamic, participative, user-generated, "web as a platform"** — it is the foundation that made SaaS/cloud (Google Docs, Gmail) possible.
Examples of Web 2.0: Google Docs/Maps, Facebook, Twitter, YouTube, Flickr, Wikipedia, blogs, Gmail, Google Calendar. [★ book-based]

| | Web 1.0 | Web 2.0 | Web 3.0 |
|---|---|---|---|
| Era | ~1990–2004 | ~2004–now | emerging |
| Nature | Static, **read-only** | **Read-write**, social, interactive | **Read-write-own**, semantic, intelligent |
| Content | Webmasters publish | **User-generated** | Machine-understandable data, AI-personalised |
| Tech | HTML, HTTP, CGI | AJAX, XML, JS, web services, APIs | Semantic web (RDF/OWL), AI/ML, blockchain, decentralised apps |
| Examples | Early company sites, Britannica Online | Facebook, YouTube, Wikipedia, Google Docs | Voice assistants, smart contracts/dApps, Web3 [★] |

### 3.6 Cloud Reference Model  [P21N][★ textbook – not in slides]
Layered view of cloud (Buyya Fig 1.5). Bottom-up:

```
┌─────────────────────────────────────────────────────────────┐
│ SaaS │ END-USER APPLICATIONS: social networks, enterprise,  │
│      │ scientific apps, Web 2.0 interfaces (browser)        │
├──────┼──────────────────────────────────────────────────────┤
│ PaaS │ USER-LEVEL MIDDLEWARE: programming environments &    │
│      │ tools, mashups, workflows, libraries (cloud runtime) │
├──────┼──────────────────────────────────────────────────────┤
│      │ CORE MIDDLEWARE: VM management & deployment, QoS     │
│      │ negotiation, admission control, pricing & billing,   │
│ IaaS │ SLA management, monitoring, execution mgmt & metering│
│      ├──────────────────────────────────────────────────────┤
│      │ SYSTEM LEVEL: physical infrastructure — data centres,│
│      │ clusters, desktop grids                              │
└──────┴──────────────────────────────────────────────────────┘
```
**One-line each:** *System level* = hardware; *Core middleware* = virtualization + management (the "brain"); *User-level middleware* = APIs/runtimes for developers; *Application level* = what the end user sees.

### 3.7 Cloud computing platforms (AWS, Azure, GCP + others)  [N]
**What a platform is [N]:** on-demand access to servers, storage, databases, networking, software, analytics over the Internet; rent and pay as you use. **AWS, Azure, GCP = "Big Three hyperscalers".**

| Platform | Best known for | Common services |
|---|---|---|
| **AWS** | Largest provider, widest portfolio | VMs, storage, DBs, AI/ML, serverless |
| **Microsoft Azure** | Enterprise & Windows integration | VMs, cloud DBs, Active Directory, AI, DevOps |
| **Google Cloud (GCP)** | Data analytics, AI, Kubernetes | Compute Engine, BigQuery, Vertex AI, Cloud Storage |
| IBM Cloud | Hybrid cloud, enterprise | Virtual servers, AI, Kubernetes, DBs |
| Oracle OCI | Enterprise databases/business apps | DB services, compute, networking, analytics |
| Alibaba Cloud | Leading in Asia | Compute, storage, DBs, AI, security |

#### AWS  [N]
Key features: scalability, reliability (multiple global data centres), security (IAM, encryption), cost-effective (pay-go), global infrastructure (regions).

| Category | Services | Purpose (from slide 24 table) |
|---|---|---|
| Compute | **EC2**, Lambda, Elastic Beanstalk | EC2 = virtual servers; Lambda = serverless |
| Storage | **S3**, EBS, Glacier | S3 = object storage for files/backups/media |
| Databases | **RDS**, DynamoDB, Aurora | RDS = managed relational (MySQL, PostgreSQL); DynamoDB = managed NoSQL |
| Networking | VPC, Route 53, CloudFront | VPC = isolated virtual network; CloudFront = CDN |
| Security | IAM, Shield, WAF | access control |
| Analytics / ML | Redshift, Athena, EMR / SageMaker | |
| Monitoring | CloudWatch, CloudTrail | |
| Load balancing | ELB | spreads traffic over servers |

Use cases: web/mobile hosting, backup & DR, big-data, AI/ML, IoT, media streaming, enterprise apps. Certifications: Cloud Practitioner, Solutions Architect, Developer, SysOps.

#### Azure  [N]
Features: scalability, high availability, security, **hybrid-cloud support**, pay-as-you-go. Services: **VMs, Blob Storage, SQL Database, Cosmos DB (global NoSQL), Functions (serverless), Virtual Network, Load Balancer, Azure AD / Entra ID (identity), Azure Monitor, App Service (PaaS web hosting)**. Strength: Windows Server/Microsoft 365/Active Directory integration. Certifications AZ-900/104/204/305.

#### GCP  [N]
Runs on the same infrastructure as Google Search/Gmail/YouTube. Services: **Compute Engine (VMs), App Engine (PaaS), GKE (managed Kubernetes), Cloud Functions, Cloud Storage, Cloud SQL, Firestore, Bigtable, Spanner, BigQuery (serverless data warehouse), Vertex AI, VPC, Cloud Load Balancing, Cloud Monitoring**. Strengths: high-speed network, AI/ML/data analytics, GKE, sustained-use discounts.

**Exam format:** *"Write a note on AWS/Azure/GCP"* → intro (2 lines) → key features → table of services by category → advantages → use cases. *"Compare AWS, Azure, GCP"* → table with rows (provider, strength, compute svc, storage svc, DB, serverless, best for) [🟡★].

### 3.8 Google App Engine & AWS deep-dive (asked repeatedly)  [P25][P22][P21N] — see solved answers in §4.2–4.4.

### 3.9 Cloud computing technologies (12)  [N]
| # | Technology | One-liner | Examples |
|---|---|---|---|
| 1 | Virtualization | Many VMs on one physical server | VMware, Hyper-V, KVM |
| 2 | Containerization | Package app + dependencies in lightweight container; runs identically everywhere | Docker, Podman |
| 3 | Orchestration | Automates deploy/scale/manage of containers | Kubernetes |
| 4 | Cloud storage | Remote storage: **object, block, file** | S3, Azure Blob, Cloud Storage |
| 5 | Serverless | Run code w/o managing servers; auto-allocated & scaled | Lambda, Azure Functions, Cloud Functions |
| 6 | Microservices | App = small independent services → scalability, maintainability, fault isolation | – |
| 7 | DevOps & CI/CD | Dev+Ops integration; CI/CD automates build–test–deploy | Jenkins, GitHub Actions, GitLab CI |
| 8 | SDN | Separates network control plane from hardware; programmable | – |
| 9 | AI / ML | Cloud AI services: prediction, automation, analytics (image recognition, chatbots, recommenders) | – |
| 10 | Big-data analytics | Process huge data sets with cloud tools | Hadoop, Spark, BigQuery |
| 11 | Edge computing | Process data near source → lower latency, real-time | – |
| 12 | IoT | Connect smart devices to cloud for collection, monitoring, control | – |

**[★] Extra for "Key enabling technologies in cloud computing" (P21M, Hwang-style):** hardware virtualization & multi-core chips · utility & grid computing · SOA, Web 2.0, mashups · autonomic computing & data-centre automation · broadband networks · (and the 12 above in the modern view).

**Microservices vs Monolith, Docker, CI/CD → fully solved in §4.5.**

### 3.10 Types of clouds — Deployment models  [N]
| Model | Meaning | Pros | Cons | Examples |
|---|---|---|---|---|
| **Public** | Owned/operated by third party; resources shared among tenants via Internet | Low cost (pay-use), zero maintenance, near-infinite scale | Less hardware control, data-residency issues | AWS, Azure, GCP |
| **Private** | Used exclusively by one organisation; on-site or third-party hosted | Highest security, customisation, compliance control | Very expensive; own IT team must maintain | OpenStack, VMware Cloud, HPE GreenLake |
| **Hybrid** | Public + private (or on-prem) bound by technology allowing data/app portability | Flexibility: sensitive data private, high-traffic apps on public | Complex to set up, manage, secure | Banking: core DB private + web front-end on public |
| **Multi-cloud** | Using **two or more public** providers simultaneously (≠ hybrid) | Avoids vendor lock-in, resilience to single provider outage | Many dashboards/tools → operational complexity | AWS for hosting + GCP for AI |
| **Community** | Shared by several orgs with common concerns (security, jurisdiction, mission) | Cost sharing + compliance | Limited scale, shared governance | Govt. agencies cloud, network of hospitals |

```
 HYBRID CLOUD
 ┌── Private cloud / On-prem ──┐   secure link    ┌──── Public cloud ────┐
 │ sensitive data, core DB     │◄══(VPN/Direct)══►│ web front-end, burst │
 └─────────────────────────────┘  data+app move   │ capacity, analytics  │
                                                  └──────────────────────┘
```
**Hybrid vs Multi-cloud [★ prediction]:** hybrid = public **+** private; multi-cloud = **≥2 public** providers.

### 3.11 Types of clouds — Service models  [N]
```
 ┌───────────────────────────────────────────────┐
 │ SaaS  Software as a Service  – just use the app│   Gmail, Netflix, M365, Salesforce
 ├───────────────────────────────────────────────┤
 │ PaaS  Platform as a Service  – just bring code │   Heroku, Elastic Beanstalk, App Engine
 ├───────────────────────────────────────────────┤
 │ IaaS  Infrastructure as a Service – manage OS  │   EC2, Azure VMs, Compute Engine
 └───────────────────────────────────────────────┘     & network
```
| | IaaS | PaaS | SaaS |
|---|---|---|---|
| You get | Virtual servers, storage, network | Environment to build/test/deploy apps | Finished application |
| Analogy [N] | Empty plot of land (build the house) | Unfurnished apartment (bring your stuff) | Hotel room (everything provided) |
| Target user | Sysadmins | **Developers** | End users |
| Provider manages | Hardware + virtualization | + OS, middleware, runtime | Everything |
| You manage | OS, middleware, runtime, app, data | App + data | Only usage/config |
| Examples | AWS EC2, Azure VMs, Google Compute Engine | Heroku, AWS Elastic Beanstalk, Google App Engine | Netflix, Gmail/Docs, Microsoft 365, Salesforce |

**Responsibility matrix [★ very common diagram]:**
```
Layer           On-Prem   IaaS     PaaS     SaaS
Application      YOU      YOU      YOU      provider
Data             YOU      YOU      YOU      provider
Runtime          YOU      YOU      provider provider
Middleware       YOU      YOU      provider provider
OS               YOU      YOU      provider provider
Virtualization   YOU      provider provider provider
Servers          YOU      provider provider provider
Storage          YOU      provider provider provider
Networking       YOU      provider provider provider
```

### 3.12 Cloud applications  [N]
Software that runs on cloud platforms rather than entirely on a local PC; uses remote servers via Internet.
- **Examples:** Email (Gmail, Outlook.com) · Storage (Drive, Dropbox, OneDrive) · Office (Google Docs, M365) · Video conferencing (Zoom, Teams) · CRM (Salesforce) · Streaming (Netflix, Spotify).
- **Characteristics:** accessible anywhere · data on remote servers · auto-updated by provider · scalable · real-time collaboration.
- **Advantages:** lower infra/maintenance cost, easy scalability, high availability, automatic backup/DR, multi-device access.
- **Disadvantages:** needs stable Internet, security/privacy concerns, limited control over infrastructure, downtime if provider has outage.
- **Cloud-native architecture:** *microservices* (small independent services, e.g. login service, payment service), *containerization* (Docker), *API-driven integration* (e-commerce app calls FedEx API for shipping cost). A real cloud app ≠ old desktop app hosted online.
- **Trends:** Gen-AI in SaaS → hybrid architectures (sensitive/massive data local or on special hardware, cloud for scale); **edge computing** for zero-delay apps (autonomous driving, smart factories, gaming).
- Used in education, business, healthcare, banking, entertainment, government.

### 3.13 Virtualization concepts  [N]
**Definition:** creating a software-based (virtual) representation of something physical — servers, storage, networks, desktops. It is the *engine* of cloud computing: one physical machine is split into multiple isolated, secure environments.

**Need [N]** –
| Without virtualization | With virtualization |
|---|---|
| One server = one OS | Multiple OSs simultaneously |
| Hardware under-utilised | Better CPU/memory/storage utilisation |
| High infrastructure cost | Lower hardware & maintenance cost |
| Hard to manage many apps | Easy resource allocation |

**Three core components [N]:** **Host** (physical hardware) · **Guest** (VM – thinks it is a real computer) · **Hypervisor / VMM** (software layer between hardware and VMs; intercepts VM requests and safely allocates CPU, memory, storage).

```
 (a) Traditional computer          (b) After virtualization  (Fig 3.1)
 ┌──────────────────────┐     ┌─────────────┐ ┌─────────────┐
 │     Application      │     │ Application │ │ Application │   ← Virtual
 │  Host operating sys  │     │  Guest OS   │ │  Guest OS   │     Machines
 │      Hardware        │     │ virt.HW     │ │ virt.HW     │
 └──────────────────────┘     ├─────────────┴─┴─────────────┤
                              │ Virtualization layer (VMM)  │
                              │ Hardware (running Host OS)  │
                              └─────────────────────────────┘
```

**Type 1 vs Type 2 hypervisors [N]**
```
 TYPE 1 (bare metal / native)        TYPE 2 (hosted)
 [GuestOS][GuestOS][GuestOS]         [GuestOS][GuestOS][GuestOS]
 ─────── Hypervisor ───────          ─────── Hypervisor ───────
        Hardware                            Host OS
                                            Hardware
```
| | Type 1 | Type 2 |
|---|---|---|
| Sits on | Directly on hardware | On top of a host OS (Windows/macOS/Linux) |
| Performance | Very fast, secure, efficient | Penalty – all passes through host OS |
| Use | Data centres, cloud providers (AWS, Azure) | Desktop/regular users, testing |
| Setup | Harder | Easy |
| Examples | VMware ESXi, Microsoft Hyper-V, KVM (+ Xen) | VirtualBox, VMware Workstation, Parallels |

**Machine reference model of execution virtualization**, **Levels of virtualization**, **Full/Para/Hardware-assisted**, **Xen / VMware / Hyper-V**, **VM files**, **VM migration** → asked as 5–10 marks; fully solved in §4.7–4.9 (textbook based [★]).

**Advantages [N]:** better resource utilisation · cost reduction · scalability · high availability · disaster recovery · faster deployment · easy backup/restore · workload isolation · live migration of VMs · energy efficiency.
**Disadvantages [N]:** performance overhead vs bare-metal · single point of failure if host fails (w/o redundancy) · licensing cost · management complexity · resource contention among VMs · security risk if hypervisor compromised.
**Applications [N]:** cloud platforms · data centres · software testing/development · disaster recovery · server consolidation · web hosting · education labs · enterprise IT.

### 3.14 Types of virtualization  [N]
| # | Type | Explanation | Examples / notes |
|---|---|---|---|
| 1 | **Server** | One physical server masked into many virtual servers; solves **server sprawl** (one server per app → wasted power) | VMware ESXi, Hyper-V, KVM |
| 2 | **Desktop (VDI)** | Desktop OS lives on a remote server; user logs in from browser/thin client; IT manages thousands of desktops centrally | VMware Horizon, Citrix [★] |
| 3 | **Network** | Decouples network software from physical switches/routers; create virtual subnets, firewalls, VPNs in software | VLAN, VPN, SDN [★] |
| 4 | **Storage** | Pools many physical drives from different arrays into one logical storage device | SAN, NAS [P22] |
| 5 | **Application** | Apps run in isolated environments without full installation on client. + No install conflicts, easy deploy, simple updates | Microsoft App-V, VMware ThinApp |
| 6 | **OS-level (containers)** | Many isolated environments share the **same host OS kernel**. + Fast start, lightweight, low resource use | Docker, LXC, Podman |

**VM vs Container [N slide 39 diagrams + ★ detail]**
```
 VIRTUAL MACHINE                     CONTAINER
 ┌───────────────────────┐          ┌───────────────────────┐
 │ Application           │          │ Applications          │
 │ Guest Operating System│          │ Container Runtime     │
 │ Virtual Machine       │          │ Host Operating System │
 │ Hypervisor            │          │ Physical Hardware     │
 │ Host Operating System │          └───────────────────────┘
 │ Physical Hardware     │
 └───────────────────────┘
```
| | VM | Container |
|---|---|---|
| Isolation | Full (own OS) | Process-level (shared kernel) |
| Size / boot | GBs / minutes | MBs / seconds |
| Overhead | High | Low |
| Portability | Heavier | Very portable |

**[★] Practice numerical – Server consolidation:** 20 physical servers, each ~10 % CPU. A virtualization host is safely run at ≤ 70 % utilisation. Total load = 20 × 10 % = 200 % of one server → hosts needed = 200/70 = 2.86 → **3 hosts** (+1 spare for HA = **4**, N+1). Servers reduced 20 → 3 (**85 % fewer**), cutting power, cooling, space.

### 3.15 Self-learning: Hardware support for virtualization at Intel  [P21N][★ textbook/Intel docs — NOT in slides]
**Why hardware support?** Classic x86 has *sensitive but non-privileged* instructions → couldn't be trapped by a VMM → software tricks (binary translation, para-virtualization) were slow/complex. Intel added hardware features (Intel **VT**).

| Resource | Intel technology | What it does |
|---|---|---|
| **Processor** | **VT-x** (x86) / **VT-i** (Itanium) | Adds **VMX root** (hypervisor) and **VMX non-root** (guest) modes, each with rings 0–3. Sensitive instructions automatically cause **VM-exit** to the hypervisor; **VM-entry** resumes the guest. State kept in **VMCS** (Virtual Machine Control Structure). No binary translation needed. |
| **Memory** | **EPT** (Extended Page Tables) | Hardware does 2-level translation: guest-virtual → guest-physical (guest page tables) → host-physical (EPT). Removes software *shadow page tables* and many VM-exits; (VPID tags TLB entries per VM). |
| **I/O – isolation** | **VT-d** (Virtualization Technology for Directed I/O) | **DMA remapping** (IOMMU: device can only DMA into its VM's memory) + **interrupt remapping** → safe direct device assignment (pass-through) |
| **I/O – sharing** | **VT-c** (Virtualization Tech for Connectivity) | Network I/O sharing: **VMDq** (per-VM queues in NIC), **SR-IOV** (one physical NIC shows up as many virtual functions) |

```
 Guest app → guest virtual addr ──(guest page table)──► guest physical addr
                                           ──(EPT, hardware)──► HOST physical addr
 Device  ──DMA──► [VT-d remap table] ──► only that VM's memory   (isolation)
 NIC ──SR-IOV──► VF1→VM1, VF2→VM2, VF3→VM3                       (sharing, VT-c)
```
**Memory trick:** *VT-x = eXecution (CPU), EPT = memory, VT-d = Directed I/O (DMA & interrupt), VT-c = Connectivity (sharable I/O).*

**Physical core vs logical (virtual/“actual”) core** (P21N Q1B-i; wording in paper is "physical core with actual core" — I read it as *physical vs logical core*) [★]:
| | Physical core | Logical core |
|---|---|---|
| What | Real hardware execution unit with its own ALUs, L1/L2 cache | A hardware thread presented to the OS via **Hyper-Threading / SMT** |
| Count | e.g. 4 cores | 8 logical for 4 physical (2 per core) |
| Performance | Full resources | Shares the physical core's resources; ~20-30 % gain only |
| Link to virtualization | Hypervisor schedules vCPUs onto them | vCPUs map to logical cores |

---

## 4. PYQ SOLUTIONS  (only Module-1 questions; grouped by topic; written as you'd write in the exam)

### 4.0 Questions I EXCLUDED (not in Module 1 of the new syllabus)
| Paper | Question | Why excluded |
|---|---|---|
| P25 | Q1 iv, vi; Q3 i; Q4 i; Q5 i – **Aneka** framework / foundation / fabric / scheduling | Aneka not in new syllabus |
| P25 | Q2A i SOA; Q2A ii MapReduce | SOA not in syllabus; MapReduce = **Module 3.3** |
| P22 | Q3 i, ii, iii – Aneka | Aneka |
| P22 | Q4 ii DVFS/power management; Q4 iii cloud federation | Not in syllabus |
| P21N | Q1A iii, iv, v, vi, viii; Q4 – Aneka / federation | Aneka / federation |
| P21N | Q1B vii hardware vs software power mgmt; Q2 federation legal issues / MOCC | Not in syllabus |
| P21M | Q1A I, II, V, VI; Q1B i-(1) Top-500, iv-vii (service registry, stateless WS, WS-*/REST, provisioning); Q2-OR GPU vs CPU; Q3 cluster jobs; Q4 GAE/HUBzero/OGCE gateways | Distributed-computing / web-services / science-gateway topics, outside Module 1 |
| Borderline *included* | Impact of data centre on environment; SpotCloud; Web 2.0; Amazon SimpleDB vs RDS; VM migration; MBaaS/MaaS | Not literally named in syllabus but sit under "intro / platforms / service models / virtualization" → included with **[borderline]** tag |

---

### GROUP A — Introduction, characteristics, vision, benefits

#### A-1. [P25 Q1(i), 5 marks] Give the various essential characteristics of Cloud Computing.
**Ans.** NIST defines cloud computing as a model for ubiquitous, convenient, on-demand network access to a shared pool of configurable resources that can be rapidly provisioned and released with minimal management effort. Its **five essential characteristics** are:
1. **On-demand self-service** – consumer provisions compute/storage automatically via a portal/API without human interaction with the provider.
2. **Broad network access** – services reachable over the network through standard mechanisms from heterogeneous clients (mobile, laptop, thin client).
3. **Resource pooling** – the provider's physical/virtual resources are pooled to serve many tenants (multi-tenancy) and dynamically assigned; the customer generally doesn't know the exact location.
4. **Rapid elasticity** – capabilities scale out and in quickly (often automatically); to the consumer they appear unlimited.
5. **Measured service** – usage is metered and monitored, giving pay-per-use billing and transparency for both sides.
```
 ┌ Broad Network Access │ Rapid Elasticity │ Measured Service │ On-Demand Self-Service ┐
 └──────────────────────────── Resource Pooling ─────────────────────────────────────────┘
        SaaS            PaaS             IaaS                  ← Service models
   Public    Private    Hybrid    Community                    ← Deployment models
```

#### A-2. [P22 Q2A(i), 5 marks] What is utility computing? Describe the vision introduced by cloud computing.
**Ans.** *Utility computing*: a model in which computing resources (CPU, storage, applications) are provided **as a metered service, like electricity or water** – the user pays only for what is consumed and does not own/maintain the infrastructure. Cloud computing realises this.
**Vision (Buyya):** IT services will be **traded as utilities in an open market, without technological and legal barriers** – a **Global Cloud Marketplace**.
- Consumers (start-ups lacking capital, enterprises with uncertain demand, developers wanting to focus on business logic, users wanting documents everywhere) *rent* what they need.
- Providers with surplus infrastructure, platforms, or application services *publish* them to the marketplace.
- Entire stack (hardware, runtime, services) becomes composable utilities → deployments in hours instead of days, with virtually no maintenance cost.
- Example: *Little Fluffy Toys* launched a bicycle-rental widget on Google App Engine in one week.
```
 Consumers ──┐                             ┌── Providers
 (startups,  ├──►  GLOBAL CLOUD MARKETPLACE ◄──┤ (rent infra / host apps /
 developers, │      (trade IT as utility)     │  provide app services)
 end users) ─┘                             └──
```

#### A-3. [P22 Q2A(ii), 5 marks] What is the major advantage of cloud computing?
**Ans.** The **major advantage is cost-efficient, on-demand elasticity**: it converts large up-front **CapEx** (buying hardware/software) into pay-as-you-go **OpEx**, and capacity can be scaled up or down in minutes, so you never over- or under-provision. Supporting advantages: speed & agility (provision in minutes), global scale, higher productivity (no racking/stacking/patching), reliability (backup, DR, business continuity), access from any device. *(Add the elasticity numerical of §3.4 as example to score extra.)*

#### A-4. [P22 Q1(ii), 5 marks] Compare Scalability and Elasticity.
**Ans.** Use the table in §3.4 (meaning, time-scale, direction, automation, cost, example). Conclude: *scalability = ability to grow; elasticity = ability to grow and shrink automatically with demand.*

#### A-5. [P22 Q1(vi), 5 marks] Major revolution introduced by Web 2.0; examples. — and [P21N Q1B(ii)] Compare Web 1.0, 2.0 and 3.0.
**Ans.** See §3.5 for the definition, revolution and the Web 1.0/2.0/3.0 table. Key sentence for P22: *Web 2.0 turned the web from a static, read-only medium into an interactive, user-participative platform with rich desktop-like applications (AJAX, XML, web services) – enabling social media, user-generated content, and the SaaS/cloud model.* Examples: Facebook, Twitter, YouTube, Wikipedia, Flickr, Google Docs/Maps, blogs.

#### A-6. [P21N Q1B(iii), part of 10] Briefly summarize cloud computing reference model.
**Ans.** Draw the layered figure from §3.6 and write: *The reference model organises cloud into **System level** (physical infra – data centres/clusters), **Core middleware** (VM management/deployment, SLA & QoS negotiation, admission control, pricing & billing, monitoring, metering – forms IaaS), **User-level middleware** (programming environments, mashups, workflows, libraries – forms PaaS) and **Application level** (end-user web apps – SaaS).* Each upper layer builds on and hides complexity of the one below.

---

### GROUP B — Deployment models, service models, XaaS

#### B-1. [P25 Q2A-OR, 10 marks] Explain different deployment models of Cloud with an example of each.
**Ans.** *Intro:* A deployment model defines **where the cloud infrastructure is located, who owns/operates it and who can access it.**
Explain the 5 models using §3.10 table, 2–3 lines each:
1. **Public** – owned by third-party provider, shared with many tenants over Internet; pay-per-use; zero maintenance, high scalability; less control. *e.g. AWS, Azure, GCP.*
2. **Private** – exclusively for one organisation (on-site or hosted); highest security/control/compliance; expensive. *e.g. OpenStack, VMware Cloud, HPE GreenLake; a bank's internal cloud.*
3. **Hybrid** – public + private bound by technology permitting data/application portability; keep sensitive data private, run bursty web loads on public. *e.g. hospital keeps patient records privately, uses AWS for the portal.*
4. **Community** – shared by organisations with common concerns (compliance, mission). *e.g. cloud shared by government agencies or a network of hospitals.*
5. **Multi-cloud** – ≥ 2 public providers at once to avoid vendor lock-in. *e.g. AWS hosting + Google Cloud AI.*
Draw the NIST deployment layer + hybrid diagram (§3.3, §3.10). End with a one-line comparison.

#### B-2. [P22 Q1(iii), 5 marks] Compare Private Cloud and Public Cloud. (also P21M Q3-OR, 10 marks — four aspects)
**5-mark answer:**
| Aspect | Public cloud | Private cloud |
|---|---|---|
| Ownership | Third-party provider | Single organisation (own or hosted) |
| Tenancy | Shared (multi-tenant) | Dedicated (single-tenant) |
| Cost | Pay-as-you-go, no CapEx | High CapEx + maintenance |
| Scalability | Virtually unlimited | Limited by owned capacity |
| Security/Control | Shared responsibility, less control | Highest control, compliance |
| Maintenance | Provider | Own IT team |
| Examples | AWS, Azure, GCP | OpenStack, VMware Cloud, HPE GreenLake |

**10-mark version [P21M Q3-OR]** — "compare in 4 aspects; give differences, advantages, shortcomings; examples" (textbook-style [★]):
| Aspect | Public cloud | Private cloud |
|---|---|---|
| **a. Technology & IT resource ownership** | Built on large, standardised, virtualized data centres owned by provider (e.g. AWS, Azure); customer owns nothing | Built on organisation's own (or dedicated hosted) hardware using OpenStack/VMware/Eucalyptus; organisation owns resources |
| **b. Provisioning of resources (data, VMs) & management** | Self-service portal/API, VMs/storage in minutes; provider manages | Provisioned by internal IT through a private portal; managed by organisation, slower, finite pool |
| **c. Workload distribution & loading policies** | Provider-level auto-scaling & load balancers across regions; policies chosen by customer within provider's options | Internal schedulers/load balancers; policies fully customisable, but limited by capacity (may *cloud-burst* to public) |
| **d. Security & data privacy enforcement** | Shared-responsibility; encryption, IAM, compliance certifications; data residency concerns | Strong physical & network control, easier regulatory compliance, data stays on-site |
| **Advantages** | Low cost, elasticity, no maintenance, global reach | Security, control, customisation |
| **Shortcomings** | Less control, security/privacy worries, vendor lock-in | Expensive, limited scalability, maintenance burden |
| **Examples** | AWS, Azure, GCP, Salesforce | OpenStack, VMware vCloud, HPE GreenLake |

#### B-3. [P25 Q1(iii), 5 marks] Explain XaaS.  
**Ans.** **XaaS = "Anything / Everything as a Service"** – umbrella term for delivering any IT capability over the Internet on subscription/pay-per-use basis. The three core models are **IaaS, PaaS, SaaS** (draw stack of §3.11); the "X" generalises to many more:
| X | Meaning | Example |
|---|---|---|
| IaaS | Infrastructure | AWS EC2 |
| PaaS | Platform | Google App Engine |
| SaaS | Software | Gmail, Salesforce |
| DaaS | Data / Desktop | Virtual desktops, data feeds [★] |
| CaaS | Containers | Google GKE [★] |
| FaaS | Functions (serverless) | AWS Lambda [★] |
| DBaaS | Database | Amazon RDS [★] |
| MBaaS | Mobile backend | Firebase [★] |
| NaaS / SECaaS / DRaaS / AIaaS / MaaS | Network / Security / Disaster-recovery / AI / Mobility | – [★] |
**Benefits:** pay-per-use, no upfront cost, rapid deployment, scalability, provider-managed.

#### B-4. [P22 Q1(i), 5 marks] How Software as a Service benefits business?
**Ans.** SaaS = provider hosts & manages the application and infrastructure; users access via browser on subscription (Gmail, Microsoft 365, Salesforce, Netflix).
Business benefits:
1. **No upfront cost** – subscription replaces licence/hardware purchase (CapEx→OpEx).
2. **Fast deployment** – ready to use within minutes; no installation.
3. **Automatic updates & maintenance** by vendor – always latest version, less IT staff.
4. **Scalability** – add/remove users/features on demand.
5. **Accessibility & collaboration** – any device, anywhere, real-time teamwork.
6. **Predictable cost** and integration via APIs; better focus on core business.
*(Caveats: dependence on Internet, vendor lock-in, data privacy.)* Analogy: staying in a hotel room – everything is provided.

#### B-5. [P22 Q2A-OR, 10 marks] What are the main characteristics of a PaaS solution? Describe the different categories of options available in a PaaS market. — also [P21N Q1B(iv)] Describe different categories of options available in PaaS market.
**Ans.**
**PaaS** provides an environment to **build, test, deploy and manage applications** without managing servers/storage/DB. (Analogy: unfurnished apartment; examples Heroku, AWS Elastic Beanstalk, Google App Engine.)
**Main characteristics:**
1. Provider manages hardware, OS, middleware and runtime; developer supplies only code & data.
2. **Web-based/ API-based development & deployment** – IDE/SDK, one-click deploy.
3. **Built-in services** – databases, queues, caching, authentication, monitoring.
4. **Automatic scalability & load balancing** of the application.
5. **Multi-tenant** architecture; shared runtime across users.
6. **Pay-per-use** pricing; faster time-to-market; supports team collaboration & multiple languages.
7. Limitations: vendor lock-in, restricted runtime (sandbox), limited OS control.

**Categories of options in the PaaS market** (Buyya's classification by what the platform offers) [★ textbook – exact labels vary by edition; learn the idea, check your Buyya Ch.1/Ch.9]:
| Category | What it offers | Examples |
|---|---|---|
| **PaaS-I – Runtime environment / web-hosting platforms** | Scalable runtime in which you deploy web applications in a provider-specific language/SDK | Google App Engine, Microsoft Azure (web/worker roles), Heroku, Elastic Beanstalk |
| **PaaS-II – Rapid application / web-based development platforms** | Browser-based tools to design & run business apps with minimal coding | Force.com (Salesforce), Zoho Creator |
| **PaaS-III – Middleware / generic distributed-application frameworks** | Open frameworks to build & run distributed (parallel, data-intensive) apps over any infrastructure (public/private) | Aneka, Hadoop-based services, Cloud Foundry/OpenShift |
*Also describe alternative view:* **public PaaS**, **private PaaS**, **open-source PaaS**.

#### B-6. [P22 Q5(ii) MBaaS ‒ 5 marks; P22 Q5(vi) MAAS; P25 Q5(vi) Mobility as a Service; P21N Q3-OR What is MaaS? Describe components — 10 marks]  [borderline, ★ textbook/own]
**MBaaS – Mobile Backend as a Service:** provider supplies ready-made **backend** for mobile/web apps through SDKs/APIs, so developers write only front-end: user authentication, cloud database/storage, push notifications, social-network integration, analytics, server-side code. Examples: Firebase, AWS Amplify, Parse, Kinvey. Benefits: faster development, no server management, auto-scaling, pay-per-use.
```
 Mobile App ──SDK/API──► [ Auth │ DB │ Storage │ Push │ Analytics │ Cloud code ] (MBaaS)
```
**MaaS (as asked in P25 – Mobility as a Service):** integration of **all transport options** (bus, metro, taxi/Uber/Ola, bike, car-share) into **one digital, on-demand service** – user plans, books and pays through a single app, often via subscription.
**Components:** (1) **User app/interface** (journey planning); (2) **Transport operators** (public & private); (3) **MaaS integrator/platform** (aggregates, API integration, booking & ticketing); (4) **Payment & billing system**; (5) **Data & analytics / real-time information** (GPS, traffic); (6) **Regulators/city authority & policy**; (7) cloud infrastructure underneath (scalable servers, storage).
*Note: in some papers MaaS may mean **Metal-as-a-Service** (Ubuntu MAAS – provisions physical servers like cloud VMs) or **Monitoring-as-a-Service**. Since P25 explicitly says "Mobility as a Service", write that; add one line about the other meaning if the paper doesn't clarify.*

---

### GROUP C — Cloud platforms (AWS, Google, Azure)

#### C-1. [P25 Q4(ii), 10 marks] With respect to the Compute services provided by AWS, discuss the six types of EC2 instances.
**Ans.** **Amazon EC2 (Elastic Compute Cloud)** is IaaS: resizable virtual servers launched from an **AMI** (Amazon Machine Image), with chosen instance type, storage (EBS/instance store), security groups and key pairs. EC2 instance types (Buyya, 6 types):
| # | Instance type | Characteristics | Typical use |
|---|---|---|---|
| 1 | **Standard** | Balanced CPU/memory; general purpose (small→extra large) | Web servers, small DBs, general apps |
| 2 | **Micro** | Very small; low sustained CPU but short **bursts** | Low-traffic sites, tests, light utilities |
| 3 | **High-Memory** | Large RAM | Databases, in-memory caches, memory-intensive analytics |
| 4 | **High-CPU** | More compute units than memory | CPU-bound: media encoding, batch, scientific |
| 5 | **Cluster Compute** | High CPU + **10 Gb Ethernet** low-latency interconnect | HPC, tightly coupled parallel jobs |
| 6 | **Cluster GPU** | GPUs (NVIDIA Tesla) attached | GPGPU, graphics rendering, ML |
*Modern AWS family names* (mention if teacher uses current AWS docs): General purpose (T, M), Compute-optimised (C), Memory-optimised (R, X), Storage-optimised (I, D), Accelerated computing (P, G – GPU), HPC-optimised (Hpc).
**Also mention:** pricing – **On-Demand, Reserved, Spot**; placement in **Regions / Availability Zones**; **Auto Scaling + ELB**; other compute: **Lambda** (serverless), **Elastic Beanstalk** (PaaS).
```
 AMI ──launch──► EC2 instance (type = CPU+RAM) ◄── EBS volume
        security group (firewall) · key pair · Elastic IP · placed in an Availability Zone
```

#### C-2. [P25 Q5(iii), 5 marks] Amazon Simple Storage Service (S3)
**Ans.** S3 is AWS's **object-storage** service for storing and retrieving any amount of data (files, backups, media, static websites) over web/REST APIs [N: "object storage for files, backups, and media"].
- **Structure:** **buckets** (globally unique names, region-specific) containing **objects** (data + metadata + unique key); flat namespace; object up to 5 TB.
- **Storage classes:** Standard, Infrequent-Access, Glacier (archive) – cost vs access speed. [★]
- **Features:** 99.999999999 % (11 nines) durability, replication across AZs, **versioning**, lifecycle rules, encryption, access control (IAM, bucket policy), pay-per-GB + requests.
- **Uses:** backup & DR, big-data lake, content for CloudFront CDN, static web hosting, media streaming.
```
 Client ──HTTP/REST(PUT/GET)──► S3 ──► Bucket "photos" ──► Object key "2025/img1.jpg" (+metadata)
```

#### C-3. [P25 Q5(v), 5 marks] AWS Architecture
**Ans.** AWS is built on **global infrastructure**: **Regions** (geographic areas) → each has multiple isolated **Availability Zones** (data centres) → plus **Edge locations** for CloudFront CDN. On top sit service layers (compute, storage, database, networking, security, analytics, monitoring). Typical **three-tier web architecture** on AWS:
```
 Users ─► Route 53 (DNS) ─► CloudFront (CDN) ─► Elastic Load Balancer
                                   ┌──────────────── VPC (private network) ───────────────┐
                                   │  AZ-1: EC2 web/app (Auto Scaling)   AZ-2: EC2 (Auto Scaling)│
                                   │            └────────► RDS (primary)  ⇄  RDS (standby) │
                                   └───────────────────────────────────────────────────────┘
        S3 (static files/backups) · DynamoDB (NoSQL) · IAM (access) · CloudWatch (monitoring)
```
Key ideas: high availability via multi-AZ, elasticity via Auto Scaling, security via IAM + VPC + security groups, pay-as-you-go.

#### C-4. [P25 Q4(iii), 10 marks] Architecture of Google AppEngine with diagrams; list services offered by Google Cloud Platform.
**Ans.** **Google App Engine (GAE)** is a **PaaS**: a scalable runtime environment for executing web applications on Google's infrastructure; developers upload code and Google handles servers, scaling and load balancing. (Little Fluffy Toys launched on it in one week [N].)
**Architecture – 4 parts** (Buyya):
1. **Infrastructure** – Google's data centres; **front-end/load balancer** routes requests; **application servers** start/stop instances automatically with load; a *scheduler* decides placement; static content served from separate file servers.
2. **Runtime environment** – a **sandbox** in which the app executes: supports **Java, Python, Go** (newer: PHP, Node.js, Ruby); restrictions for safety/scale: no arbitrary file writes, limited outbound network (only via URL Fetch), request time limits, no long-running threads.
3. **Storage** – **Datastore** (schemaless, entity-based NoSQL built over **BigTable**; GQL query; transactions), **Memcache** (in-memory cache), **Blobstore/Cloud Storage** for large files, **static file servers**.
4. **Application services** – **URL Fetch** (HTTP calls), **Mail**, **XMPP**, **Memcache**, **Image manipulation**, **Task queues/Cron** (background & scheduled jobs), **user authentication (Google accounts)**.
Plus **SDK/dev server** for local testing and **Admin console** for deployment, monitoring, quotas & billing.
```
 Internet ──► Front-end / Load Balancer ──► App Server instances (auto scale)
                                              │  RUNTIME SANDBOX (Java/Python/Go)
                                              ├─► Datastore (BigTable) ── Memcache ── Blobstore
                                              └─► App services: URLFetch│Mail│XMPP│TaskQueue│Image│Cron
 Developer ──SDK/Admin console──► deploy, monitor, billing
```
**Services offered by Google Cloud Platform [N]:**
| Category | Services |
|---|---|
| Compute | Compute Engine, App Engine, Cloud Functions, GKE |
| Storage | Cloud Storage, Persistent Disk |
| Databases | Cloud SQL, Firestore, Bigtable, Spanner |
| Networking | VPC, Cloud Load Balancing, Cloud DNS |
| Security | IAM, Cloud Armor, Secret Manager |
| Analytics | BigQuery, Dataflow, Dataproc |
| AI/ML | Vertex AI, Vision AI, Speech-to-Text |
| Monitoring | Cloud Monitoring, Cloud Logging |

#### C-5. [P22 Q4(i), 10 marks] What type of service is AppEngine? Describe the core components of AppEngine. — also [P21N Q3-A, 10 marks] Describe the core components of Google AppEngine; [P21N Q1A(ii), 2 marks] development technologies supported.
**Ans.**
- **Type:** **PaaS** (public cloud, runtime for web apps).
- **Core components:** answer = the 4 parts of C-4: **(1) Infrastructure** (front-end, app servers, scheduler), **(2) Runtime environment** (sandbox; Java/Python/Go), **(3) Storage** (Datastore on BigTable, Memcache, static file servers, Blobstore), **(4) Application services** (URL Fetch, Mail, XMPP, Memcache, Image, Task queue, Cron, accounts) — plus SDK and Admin console. Draw the same diagram. Elaborate each for 10 marks.
- **2-mark answer (P21N): development technologies** – **Java** (servlets/JSP, any JVM language), **Python** (frameworks like Django/webapp2), and **Go**; data via Datastore/GQL (newer: Node.js, PHP, Ruby).

#### C-6. [P21N Q1B(v), part of 10] Difference between Amazon SimpleDB and Amazon RDS.  [borderline]
| | **Amazon SimpleDB** | **Amazon RDS** |
|---|---|---|
| Model | NoSQL, schema-less (domains → items → attributes) | **Relational** (tables, rows, schema) |
| Query | Simple SELECT-like; no joins | Full **SQL**, joins, transactions (ACID) |
| Engines | Proprietary | MySQL, PostgreSQL, Oracle, SQL Server, MariaDB, Aurora |
| Consistency | Eventual (optional consistent read) | Strong (ACID) |
| Scaling | Auto-scales small data sets (domain size limits) | Scale by instance size, read replicas, Multi-AZ |
| Best for | Light, flexible metadata/lookup | Business apps needing structured data & relations |
| Status | Legacy [★] | Actively used |

#### C-7. [P22 Q2B(ii), 10 marks] Discuss the architecture of Hyper-V. Discuss its use in cloud computing.
**Ans.** **Hyper-V** is Microsoft's **Type-1 (bare-metal) hypervisor** [N lists it as Type 1]. It installs directly on hardware and divides it into isolated **partitions**.
**Architecture:**
```
 ┌──────────── Parent (Root) Partition ───┐ ┌── Child Partition ──┐ ┌── Child Partition ───┐
 │ Windows Server (host OS)               │ │ Enlightened guest   │ │ Un-enlightened guest │
 │  • Virtualization stack (VMMS, WMI)    │ │ (Linux/Win)         │ │ (legacy OS)          │
 │  • VM worker processes (1 per VM)      │ │  • apps             │ │  • apps              │
 │  • Device drivers                      │ │  • VSC (virt.       │ │  • emulated devices  │
 │  • VSP (Virtualization Service Provider)│ │   service client)   │ │    (slower)          │
 └───────────────────▲────────────────────┘ └─────────▲───────────┘ └──────────────────────┘
                     └──────── VMBus (fast in-memory channel) ────┘
 ┌──────────────────────────────────────────────────────────────────────────────────────────┐
 │               HYPERVISOR (Microsoft Hyper-V)  – CPU scheduling, memory, interrupts        │
 └──────────────────────────────────────────────────────────────────────────────────────────┘
 ┌──────────────────────────────────────────────────────────────────────────────────────────┐
 │  Physical hardware (CPU with VT-x/AMD-V, RAM, disks, NICs)                                │
 └──────────────────────────────────────────────────────────────────────────────────────────┘
```
- **Hypervisor layer:** thin micro-kernel; schedules CPUs, manages memory & interrupts; needs hardware virtualization (Intel VT-x / AMD-V).
- **Parent (root) partition:** first partition; runs Windows Server; owns physical **device drivers**; hosts the **virtualization stack** (VM management service, worker processes) and **VSPs** that serve I/O to children.
- **Child partitions:** guest VMs. **Enlightened** guests know they're virtualized; use **VSC → VMBus → VSP** for fast I/O. **Un-enlightened** guests use emulated devices (slower).
- **VMBus:** high-speed, in-memory inter-partition channel. **Hypercalls** provide the interface between guests and hypervisor.
**Use in cloud computing:** forms the virtualization base of **Microsoft Azure** (IaaS VMs) and **private clouds** (Windows Server/System Center); supports **server consolidation**, **live migration**, **dynamic memory**, **snapshots**, **Hyper-V Replica for disaster recovery**, **VM isolation** for multi-tenancy, **hybrid cloud** with Azure, and VDI hosting. Gives better resource utilisation and lower cost.

#### C-8. [P21M Q1A(VII), 2 marks] Match Microsoft service offerings.
Virtualization → **B** (OS level / Hyper-V); Security features → **C** (Replicated data, rule-based access control); SaaS → **A** (.NET service, Dynamic CRM).
**Answer: option (a) 1-B, 2-C, 3-A.**

---

### GROUP D — Cloud technologies (Microservices, Docker, CI/CD)

#### D-1. [P25 Q1(v), 5 marks] Various benefits of Microservices.
**Ans.** Microservices = application built as a **collection of small, independent services**, each doing one business function, with its own data store, communicating via APIs. **Benefits:**
1. **Independent deployment** – update one service without redeploying whole app.
2. **Scalability** – scale only the busy services (e.g. payment) – cost-efficient.
3. **Fault isolation** – failure of one service doesn't bring the whole system down.
4. **Technology flexibility** – each service can use its own language/DB.
5. **Faster development & CI/CD** – small teams work in parallel; frequent releases.
6. **Maintainability & reusability** – small code bases, easier to understand/test; services reused across apps.

#### D-2. [P25 Q3(ii), 10 marks] Explain Microservices Architecture and its Benefits. Compare with Monolithic Architecture.
**Ans.**
```
 MONOLITH                                   MICROSERVICES
 ┌─────────────────────────┐        Client ─► API Gateway
 │ UI │ Users │ Orders │Pay │              ┌──────┬──────┬───────┬───────┐
 │   single codebase        │              │ User │Order │Payment│Catalog│  (independent
 │   single DB              │              │ svc  │ svc  │ svc   │ svc   │   services,
 └─────────────────────────┘              └──┬───┴──┬───┴───┬───┴───┬───┘   each in a
        one deployable unit                  DB1    DB2     DB3     DB4     container)
```
**Architecture components:** (i) **Services** – small, single-responsibility; (ii) **API Gateway** – single entry, routing, auth; (iii) **Service discovery & load balancer**; (iv) **Own database per service** (decentralised data); (v) **Inter-service communication** – REST/gRPC or message queues; (vi) **Containers + orchestration** (Docker + Kubernetes) and **CI/CD**; (vii) monitoring/logging. (Example in notes: one service handles logins, another payments; e-commerce calling FedEx API.)
**Benefits:** as in D-1.
**Comparison:**
| Aspect | Monolithic | Microservices |
|---|---|---|
| Structure | One tightly-coupled code base | Many small loosely-coupled services |
| Deployment | Whole app redeployed for any change | Each service deployed independently |
| Scaling | Scale entire app | Scale individual services |
| Fault tolerance | One bug can crash all | Failure isolated |
| Technology | Single stack | Polyglot (any language per service) |
| Development | Slower as team/code grows; large team conflicts | Small autonomous teams, faster releases |
| Data | One shared DB | DB per service |
| Complexity | Simple initially; hard to maintain later | Complex ops (network, distributed debugging) |
| Best for | Small/simple apps | Large, evolving, cloud-native apps |

#### D-3. [P25 Q3(iii), 10 marks] Discuss any five Docker commands with examples for each.
**Ans.** *Intro:* **Docker** packages an application and its dependencies into a lightweight **container** (OS-level virtualization sharing the host kernel); built from an **image** (read-only template, defined by **Dockerfile**), pulled from a **registry** (Docker Hub), run by the **Docker daemon** via **Docker client (CLI)**.
```
 Docker client ──(docker cmds)──► Docker daemon (dockerd) ──► Containers
                                        ▲  pull/push
                                  Registry (Docker Hub) ── Images
```
| # | Command | Purpose | Example |
|---|---|---|---|
| 1 | `docker pull <image>` | Download image from registry | `docker pull nginx` |
| 2 | `docker images` | List local images | `docker images` |
| 3 | `docker run [opts] <image>` | Create + start a container (`-d` detached, `-p host:cont` port map, `--name`) | `docker run -d -p 8080:80 --name web nginx` |
| 4 | `docker ps [-a]` | List running (all) containers | `docker ps -a` |
| 5 | `docker stop <name>` / `docker start` | Stop / start a container | `docker stop web` |
| 6 | `docker rm <name>` / `docker rmi <image>` | Remove container / image | `docker rm web` ; `docker rmi nginx` |
| 7 | `docker build -t <tag> .` | Build image from Dockerfile | `docker build -t myapp:1.0 .` |
| 8 | `docker exec -it <name> bash` | Open shell inside running container | `docker exec -it web bash` |
| 9 | `docker logs <name>` | View container output | `docker logs web` |
| 10 | `docker push <image>` | Upload image to registry | `docker push anamay/myapp:1.0` |
Write any 5 (e.g. pull, run, ps, stop, build) with a one-line explanation + sample output. Sample Dockerfile [★]:
```
FROM python:3.11
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
CMD ["python","app.py"]
```

#### D-4. [P22 Q5(i), 5 marks] Dockers and Containers
**Ans.** A **container** is a lightweight, isolated runtime that packages app + libraries + config and shares the host OS kernel (**OS-level virtualization** – examples Docker, LXC, Podman). **Docker** is the most popular container platform (engine + image format + Docker Hub). Ensures the app runs **consistently across environments** (laptop → cloud). Orchestrated at scale by **Kubernetes**.
Diagram: container stack vs VM stack of §3.14. Advantages: fast start (seconds), low resource usage, portability, density, fits microservices & CI/CD. Differences vs VM: no guest OS → smaller, faster, but weaker isolation (shared kernel).

#### D-5. [P22 Q1(v), 5 marks] What is Jenkins? What is Continuous Integration?
**Ans.** **Continuous Integration (CI):** developers frequently (several times a day) merge code into a shared repository; each commit **automatically triggers build + automated tests**, so integration bugs are caught early. **CD** (Continuous Delivery/Deployment) automatically releases the tested build to staging/production. **Jenkins** is an open-source, Java-based **automation server** that implements CI/CD pipelines using plugins (Git, Maven, Docker, Kubernetes) and a *Jenkinsfile*. (Others: GitHub Actions, GitLab CI [N].)
```
 Developer ─► Git repo ─(webhook)─► JENKINS: [Build] → [Unit tests] → [Package/Docker image]
                                                   │ pass                       │ fail → notify dev
                                                   ▼
                                       [Deploy to staging] → [Deploy to production]
```
Benefits: early bug detection, faster releases, less manual work, consistent builds.

#### D-6. [P21M Q1B(ii), 2 marks] Key enabling technologies in cloud computing systems.
**Ans.** (i) **Virtualization** (hardware, OS-level, containers) – resource pooling & isolation; (ii) **Multi-core processors & high-speed networks/broadband**; (iii) **Web 2.0 / web services / SOA** (service interfaces); (iv) **Utility & grid/distributed computing**; (v) **Data-centre automation / autonomic computing**; (vi) **Orchestration, serverless, microservices, DevOps/CI-CD, SDN, big-data & AI/ML, edge & IoT** [N list].

---

### GROUP E — Virtualization

#### E-1. [P25 Q1(ii), 5 marks] Explain various levels of virtualization.
**Ans.** Virtualization can be implemented at **five levels** of the computer stack (Hwang) [★ textbook]:
```
   ┌─────────────────────────────────────────┐
 5 │ User-application level (JVM, .NET CLR)  │  higher level = less overhead but
 4 │ Library support level (WINE, vCUDA)     │  less flexibility/ isolation
 3 │ Operating-system level (Docker, LXC)    │
 2 │ Hardware abstraction level (VMware, Xen)│
 1 │ Instruction Set Architecture (QEMU)     │
   │            Hardware                      │
   └─────────────────────────────────────────┘
```
1. **ISA level** – host ISA emulated in software (instruction-by-instruction or dynamic binary translation) → run binaries of one ISA on another (QEMU, Bochs). Flexible but slowest.
2. **Hardware abstraction level (HAL)** – hypervisor virtualizes CPU, memory, I/O directly over hardware; many OSs run as guests; best performance for full-OS VMs (VMware ESXi, Xen, KVM, Hyper-V).
3. **Operating-system level** – OS kernel creates isolated containers sharing one kernel; very low overhead; same-OS only (Docker, LXC, OpenVZ) [N: "OS-level virtualization (containers)"].
4. **Library (API) support level** – virtualizes API/library interface through API hooks, so apps of one OS run on another (WINE for Windows apps on Linux; vCUDA).
5. **User-application (process) level** – application runs in a high-level-language VM or isolated sandbox (JVM, .NET CLR); also application virtualization (App-V, ThinApp) [N].
Plus, virtualization *of resources*: server, desktop, network, storage (§3.14).

#### E-2. [P22 Q2B(i), 10 marks] Discuss the machine reference model of execution virtualization. What are the benefits of virtualization in the context of cloud computing?
**Ans.** [★ Buyya Ch.3]
**Machine reference model.** Virtualization works by **replacing one of the interfaces** between layers of a computer system and imitating it. The layers and their interfaces:
```
   ┌─────────────────────────────┐
   │      Applications           │
   ├──────────── API ────────────┤  ← interface: applications ↔ libraries/OS
   │  Libraries / Runtime        │
   ├──────────── ABI ────────────┤  ← interface: application binaries ↔ OS (system calls, binary format)
   │  Operating System           │
   ├──────────── ISA ────────────┤  ← interface: software ↔ hardware (machine instructions)
   │  Hardware                   │      user ISA (non-privileged) + system ISA (privileged)
   └─────────────────────────────┘
```
- **ISA** – instruction set of the processor, registers, memory & interrupt management; the boundary between hardware and software. Split into **privileged instructions** (only OS/kernel) and **non-privileged** (user apps).
- **ABI** – separates OS from applications/libraries; covers system calls, calling conventions, binary formats. Provides portability across systems with same OS & ISA.
- **API** – interface between application and libraries/OS (source-level portability).
- **Privilege rings:** Ring 0 (supervisor/kernel – most privileged), Rings 1–2 (device drivers), Ring 3 (user mode). A **hypervisor runs in supervisor mode** and guest OS runs de-privileged; sensitive instructions are trapped/handled by VMM. **Hardware-assisted virtualization** (Intel VT-x/AMD-V) adds a *root mode* below ring 0 (see §3.15).
- Execution virtualization is divided into **process-level** (VM created for one application – e.g. JVM, emulators; ABI/API virtualized) and **system-level** (VM for an entire OS – hypervisors; ISA virtualized).

**Benefits of virtualization in cloud computing:**
1. **Resource utilisation & server consolidation** – many VMs on one host; fewer servers, lower power/space (§3.14 numerical).
2. **Isolation & security** – each VM sandboxed; faults/malware don't spread; managed execution.
3. **Resource pooling & multi-tenancy** – the technical basis of cloud's "resource pooling".
4. **Elasticity & fast provisioning** – VMs created/cloned in minutes from templates.
5. **Portability & live migration** – VMs move between hosts without downtime (load balancing, maintenance).
6. **High availability & DR** – snapshots, backups, replication, restart on another host.
7. **Cost reduction** – pay-per-use, less hardware & admin.
8. **Performance tuning / QoS** – CPU/memory caps and sharing, aggregation of hosts.
9. **Testing & legacy support** – run different OSs; sandboxes.
*(Disadvantages for a balanced answer [N]: overhead, single point of failure, licence cost, complexity, contention, hypervisor security.)*

#### E-3. [P21N Q1A(vii), 1 mark] Define process-level virtualization.
**Ans.** A form of execution virtualization in which a **virtual environment is created for a single application/process** on top of the host OS (the ABI/API is virtualized), so the program runs in an emulated or managed runtime without a full guest OS – e.g. **JVM, .NET CLR, emulators, application sandboxes** (cf. system-level virtualization, which virtualizes a whole OS/hardware).

#### E-4. [P21M Q1B(iii), 2 marks] Differences between hypervisor and para-virtualization; give one example VMM built in each category.
**Ans.** [★ Hwang]
| | Hypervisor (full virtualization) | Para-virtualization |
|---|---|---|
| Guest OS | **Unmodified** | **Modified** (kernel changed to make *hypercalls*) |
| How privileged instructions handled | Trapped / **binary translation** by VMM | Replaced by explicit hypercalls to the hypervisor |
| Performance | Slightly lower (translation overhead) | Higher |
| Compatibility | Any OS | Only OSs that can be modified |
| Example VMM | **VMware ESX / ESXi** | **Xen** |

#### E-5. [P22 Q5(iii), 5 marks] Xen Hypervisor
**Ans.** **Xen** is an open-source **Type-1 (bare-metal) hypervisor** (University of Cambridge), classically implementing **para-virtualization** (also supports hardware-assisted full virtualization using VT-x/AMD-V). It runs in the most privileged mode (ring 0); guest OS kernels run in ring 1; apps in ring 3.
```
 ┌───────────┐ ┌───────────┐ ┌───────────┐
 │ Domain 0  │ │ Domain U1 │ │ Domain U2 │
 │ (Dom0)    │ │ guest OS  │ │ guest OS  │
 │ control   │ │ + apps    │ │ + apps    │
 │ domain,   │ │ (PV/HVM)  │ │           │
 │ drivers,  │ └─────┬─────┘ └─────┬─────┘
 │ toolstack │       │ hypercalls / event channels
 └─────┬─────┘       │
 ┌─────▼─────────────▼──────────────────┐
 │        XEN HYPERVISOR                │  (CPU scheduling, memory, interrupts)
 └──────────────────────────────────────┘
 │             Hardware                 │
```
- **Domain 0:** privileged control domain (modified Linux); has real device drivers; creates/destroys/migrates guests via toolstack.
- **Domain U:** unprivileged guests; use **split (front-end/back-end) drivers** with Dom0 for I/O; communicate via **hypercalls** and **event channels**, shared-memory rings.
- **Advantages:** near-native performance, small trusted code base, live migration, strong isolation; used by early AWS EC2 and many clouds.

#### E-6. [P22 Q5(iv), 5 marks] VMware – Full Virtualization
**Ans.** **Full virtualization** = complete simulation of the underlying hardware so an **unmodified guest OS** runs in a VM, unaware it's virtualized. VMware achieves it by **binary translation + direct execution**:
```
   Ring 3 : User apps ───────── direct execution on CPU (fast)
   Ring 1 : Guest OS kernel  ── privileged/sensitive instr. → binary-translated by VMM
   Ring 0 : VMware VMM / hypervisor (virtual HW: CPU, memory, devices emulated) ─ Hardware
```
- User-mode code runs directly on the CPU; kernel-mode code containing non-virtualizable instructions is **translated on the fly** into safe sequences.
- VMM emulates virtual BIOS, devices, memory (shadow page tables, or EPT with hardware assist).
- **Products:** VMware **ESXi** (Type 1, data centre), **Workstation/Fusion** (Type 2, desktop), vSphere/vCenter with **vMotion** (live migration).
- **Pros:** no guest OS modification, complete isolation, wide OS support. **Cons:** translation overhead, complexity (reduced by Intel VT-x/AMD-V).

#### E-7. [P25 Q2B(i), 10 marks] Illustrate the concept of a Virtual Machine with its various files. Further list the content of the .VMX file.
**Ans.** A **VM** is a software-defined computer (virtual CPU, memory, disk, NIC) running a guest OS and apps on top of a hypervisor, **completely isolated** and **encapsulated as a set of files** – making it easy to copy, back-up, move and clone. (Fig 3.1 diagram of §3.13.)
**VM files (VMware):**
| File | Purpose |
|---|---|
| **.vmx** | **Configuration file** – the VM's hardware definition |
| **.vmdk** (and -flat.vmdk) | **Virtual disk** – descriptor + data of the guest's hard drive |
| **.nvram** | BIOS/firmware (NVRAM) state |
| **.vmem** | Backup of the VM's **memory (paging)** file |
| **.vswp** | Swap file for VM memory |
| **.vmss** | **Suspended-state** file |
| **.vmsd** / **.vmsn** | **Snapshot** metadata / snapshot state |
| **.log** | VM activity log files |
| **.vmxf** | Supplemental config (for teams) |
**Contents of .VMX file** – a plain-text list of `key = "value"` entries:
```
.encoding            = "UTF-8"
config.version       = "8"                     # config file format
virtualHW.version    = "14"                    # virtual hardware version
displayName          = "Ubuntu-VM"             # VM name
guestOS              = "ubuntu-64"             # guest OS type
memsize              = "4096"                  # RAM in MB
numvcpus             = "2"                     # virtual CPUs
scsi0.present        = "TRUE"
scsi0.virtualDev     = "lsilogic"              # disk controller type
scsi0:0.present      = "TRUE"
scsi0:0.fileName     = "Ubuntu-VM.vmdk"        # virtual disk used
ethernet0.present    = "TRUE"
ethernet0.connectionType = "nat"               # NIC mode (nat/bridged/host-only)
ethernet0.virtualDev = "e1000"                 # NIC model
ide1:0.deviceType    = "cdrom-image"           # CD/DVD (ISO)
floppy0.present      = "FALSE"
uuid.bios            = "56 4d ..."             # unique id
nvram                = "Ubuntu-VM.nvram"       # NVRAM file name
```
i.e. it holds: **VM name, guest OS, hardware version, RAM size, no. of vCPUs, disk controller + virtual-disk file names, network adapter type/mode, CD/floppy devices, UUID, and paths of the other files.**
*(If the examiner expects Hyper-V/VirtualBox: .vhd/.vhdx, .vmcx, .vbox, same idea.)*

#### E-8. [P25 Q2B(ii), 10 marks] Describe Migration in Virtual Machine with its types in detail.
**Ans.** **VM migration** = moving a VM (its memory, CPU state, storage and network identity) from one physical host to another – for load balancing, maintenance, power saving, fault tolerance.
**Types:**
1. **Cold migration (non-live)** – VM is **powered off**, files (and config) moved/registered on the new host, then powered on. Simple; longest downtime; no shared storage needed.
2. **Suspend (warm) migration** – VM is **suspended** (state saved to disk), moved, then **resumed** on destination. Downtime = copy time; apps continue where they left.
3. **Live (hot) migration** – VM keeps **running** while migrating (e.g. VMware **vMotion**, Xen live migration, Hyper-V Live Migration); downtime only milliseconds–seconds. Requires shared storage/fast network. Methods:
   - **Pre-copy** – copy memory pages iteratively while VM runs, re-copy dirtied pages, then short stop-and-copy.
   - **Post-copy** – move CPU state first, resume at target, fetch pages on demand.
   - **Hybrid** – a bit of pre-copy then post-copy.
4. **Storage migration** (Storage vMotion) – move VM disk files between datastores while VM runs.
5. **P2V / V2V / V2P** conversions – physical→virtual, virtual→virtual, virtual→physical (workload moves between platforms). [★]
**Live-migration stages (pre-copy)**
```
 Stage 0 Pre-migration  : VM active on host A; choose destination B
 Stage 1 Reservation    : initialise a container (resources) on target B
 Stage 2 Iterative pre-copy : copy memory pages round by round while VM runs on A
 Stage 3 Stop & copy    : suspend VM on A; copy remaining dirty pages + CPU state (downtime)
 Stage 4 Commitment     : B confirms it has a consistent copy; A releases VM
 Stage 5 Activation     : VM resumes on B; network redirected (ARP update)
```
**Benefits/Issues:** consistency, minimal downtime, network/shared-storage need, performance impact during copying.

#### E-9. [P25 Q5(ii), 5 marks] Applications of VM migration.
**Ans.** (1) **Load balancing** – move VMs from overloaded hosts to under-used ones; (2) **Server consolidation & power saving** – pack VMs onto few hosts, switch off idle hosts; (3) **Hardware maintenance/upgrade** with zero downtime; (4) **Fault tolerance & disaster recovery** – evacuate VMs from failing hosts / to remote sites; (5) **Cloud bursting / hybrid cloud** – shift workloads between private and public clouds; (6) **Performance & data locality** – bring VM nearer users/data; (7) **Resource optimisation & SLA compliance** – dynamic reallocation.

#### E-10. [P21M Q1A(III), 1 mark] In live migration of a VM from one host to another, Stage 1 is used for ___ 
**Ans.** **(b) Reservation – initialize a container on the target host.** (Stage 0 = Pre-migration, Stage 2 = iterative pre-copy, Stage 4 = commitment.) [borderline]

#### E-11. [P21M Q2 (first option), 10 marks] Why are virtual machines and virtual clusters suggested in cloud computing systems? What breakthroughs are required to build virtualized cloud systems cost-effectively? What are the impacts of cloud platforms on the future of HPC and HTC industry?  [★ Hwang-style, borderline]
**(a) Why VMs and virtual clusters**
- **Advantages:** flexible resource sharing/server consolidation (higher utilisation); isolation & security between tenants; on-demand dynamic provisioning/elasticity; portability & live migration; fast fault recovery (snapshots, restart); legacy OS/software support; **virtual clusters** let users get an entire custom cluster (own OS, software stack) that can grow/shrink and be moved/cloned – easier than physical clusters; good for both HPC (batch) and HTC (many tasks).
- **Disadvantages:** performance overhead (esp. I/O, network, HPC tightly-coupled jobs); resource contention ("noisy neighbours"); more complex management; security of hypervisor; licensing; VM sprawl & migration costs.
**(b) Breakthroughs needed for cost-effective virtualized clouds**
Low-overhead virtualization (hardware assist – VT-x/EPT/VT-d/SR-IOV, near-native I/O); efficient VM provisioning, image distribution and fast live migration; automatic resource management/scheduling & power-aware consolidation; scalable virtual networking/storage (SDN, storage virtualization); strong multi-tenant security/isolation; standard interfaces (to avoid lock-in) and SLA-aware pricing/metering.
**(c) Impact on HPC/HTC**
Clouds give **pay-as-you-go, elastic access** to massive HPC/HTC capacity without owning supercomputers → democratises HPC; HTC workloads (embarrassingly parallel, big data) fit well; cost shifts from CapEx to OpEx; limits: network latency & virtualization overhead for tightly-coupled MPI jobs, data-transfer cost → leads to specialised HPC cloud instances (cluster compute/GPU – see C-1), hybrid HPC-cloud bursting. *Net effect:* cloud complements and gradually blends with traditional HPC/HTC centres.

---

### GROUP F — Types of virtualization (storage, server)

#### F-1. [P22 Q1(iv), 5 marks] Compare SAN and NAS storage virtualization.
**Ans.** Storage virtualization pools many physical drives into one logical storage device (§3.14). Two common storage architectures:
```
 SAN                                             NAS
 Servers ══(Fibre Channel/iSCSI network)══ Disk arrays      Clients ──LAN/IP──► NAS device (file server + disks)
 (block-level; server sees "local disk")                    (file-level; shared folders via NFS/SMB)
```
| Aspect | **SAN** (Storage Area Network) | **NAS** (Network Attached Storage) |
|---|---|---|
| Access level | **Block-level** | **File-level** |
| Network | Dedicated high-speed network (Fibre Channel, iSCSI) | Ordinary Ethernet LAN/IP |
| Protocols | FC, iSCSI, FCoE | NFS, SMB/CIFS, FTP |
| How seen by server | As raw local disk (server formats it) | As a network share/folder (NAS has its own OS & file system) |
| Performance | Very high, low latency | Moderate |
| Cost/complexity | High, specialised admin | Low, simple |
| Use cases | Databases, VMs/virtualization, ERP | File sharing, backups, home dirs, media |
| Virtualization | Virtual LUNs pooled across arrays | Virtual file systems/ global namespace |

#### F-2. [P21M Q1A(IV), 2 marks] Match SAN / LAN / NAS.
SAN → **C** (connects servers to network storage such as disk arrays); LAN → **A** (connect client hosts to big servers); NAS → **B** (connects client hosts directly to the disk arrays).
**Answer: option (d) 1-C, 2-A, 3-B.**

#### F-3. [P21N Q1B(vi), part of 10] What is server consolidation? How can it be considered a power-management strategy?
**Ans.** **Server consolidation** = migrating workloads from many under-utilised physical servers onto fewer, well-utilised physical servers using **server virtualization** (each old server becomes a VM) [N: solves "server sprawl"; application: server consolidation].
**As power management:** idle/under-utilised servers still draw 50–60 % of peak power. Consolidation lets us **switch off or put to sleep surplus servers**, cutting electricity for **servers and cooling**, shrinking floor space and carbon footprint, while raising utilisation of active servers (e.g. 20 servers at 10 % → 3 at ~67 %, §3.14 numerical). Combined with **live migration** for dynamic (day/night) consolidation. Risks: hotspots, single point of failure, performance interference.

---

### GROUP G — Intel hardware support (self-learning 1.2)

#### G-1. [P21N Q1A(i), 2 marks] Match: a) Processor virtualization, b) I/O virtualization – DMA and interrupt remap, c) I/O virtualization – Sharable, d) Memory virtualization with I) VT-d II) VT-c III) EPT IV) VT-x or VT-i.
a (Processor) → **IV** VT-x/VT-i; b (DMA & interrupt remap) → **I** VT-d; c (Sharable I/O) → **II** VT-c; d (Memory) → **III** EPT.
**Answer: option A) a-IV, b-I, c-II, d-III.**

#### G-2. [P21N Q1B(i), part of 10] Compare physical core with actual core. → see §3.15 table (physical vs logical/virtual core, Hyper-Threading).

---

### GROUP H — Borderline / general (marked)

#### H-1. [P25 Q5(iv), 5 marks] Impact of Cloud Data Centre on Environment  [borderline ★]
**Ans.** Cloud data centres host millions of servers and consume **~1–2 % of global electricity**, mostly for servers and **cooling**.
**Negative impacts:** high energy use & **CO₂ emissions** (if powered by fossil fuels); large **water** use for cooling; **e-waste** from hardware refresh; land use; heat and noise.
**Positive/mitigating:** shared, virtualized infrastructure is **more efficient than many small private server rooms** (higher utilisation, consolidation); providers use **renewable energy**, efficient design (low **PUE** – Power Usage Effectiveness), free-air/liquid cooling, ARM/efficient chips, AI-optimised cooling, hardware recycling; **dematerialisation** (less travel, paper).
**Green-cloud measures:** server consolidation/live migration (§F-3), power-aware scheduling, renewable-powered regions, carbon-aware workload placement.

#### H-2. [P22 Q5(v), 5 marks] Spot Cloud  [borderline ★]
**Ans.** **SpotCloud** is an online **marketplace for buying and selling spare cloud capacity** (launched by Enomaly): providers with **surplus** infrastructure list it with price/location/quality; buyers pick capacity by price, location and performance – a concrete realisation of the **"Global Cloud Marketplace"** vision (§3.2). Benefits: providers monetise idle capacity, buyers get cheap compute, no lock-in. (Don't confuse with **AWS Spot Instances** – unused EC2 capacity at discount that can be reclaimed with short notice.)

---

## 5. [★] PREDICTED QUESTIONS (NOT in notes or official PYQ — my own prediction from the syllabus)

| # | Likely question | Marks | Where to find the answer |
|---|---|---|---|
| 1 | Compare IaaS, PaaS, SaaS (with diagram & examples) | 5/10 | §3.11 tables + responsibility matrix |
| 2 | Compare Type-1 and Type-2 hypervisors | 5 | §3.13 |
| 3 | VM vs Container | 5 | §3.14 |
| 4 | Hybrid cloud vs Multi-cloud; Public/Private/Hybrid/Community | 5/10 | §3.10 |
| 5 | Advantages & disadvantages of virtualization | 5 | §3.13 |
| 6 | Applications of virtualization | 3-5 | §3.13 |
| 7 | Types of virtualization – explain any four (server, desktop, network, storage, application, OS-level) | 10 | §3.14 |
| 8 | Intel VT-x / EPT / VT-d note; "Hardware support for processor, memory, I/O virtualization" | 10 | §3.15 |
| 9 | Compare AWS, Azure and GCP | 10 | §3.7 – make a table: strength, compute, storage, DB, serverless, best for |
| 10 | Write notes: Serverless computing, Edge computing, SDN, Kubernetes | 5 | §3.9 – expand each: definition, how it works, example, advantage |
| 11 | Cloud applications – characteristics, advantages, disadvantages | 5 | §3.12 |
| 12 | NIST definition + draw NIST cloud model | 5 | §3.3 |
| 13 | Benefits of cloud (CapEx→OpEx etc.) / Challenges of cloud | 5 | §3.4 (challenges: security, privacy, vendor lock-in, downtime, compliance, latency) |
| 14 | Numerical: server consolidation; CapEx vs OpEx break-even; elasticity savings | 5 | §3.14, §3.4 (solved) |
| 15 | Cloud-native architecture: microservices + containers + APIs | 5 | §3.12, §D-2 |

**Quick-fire 1-mark facts to memorise:** NIST = 5 characteristics, 3 service models, 4 deployment models · IaaS = EC2/VMs · PaaS = App Engine/Heroku/Beanstalk · SaaS = Gmail/Netflix/M365/Salesforce · Type 1 = ESXi/Hyper-V/KVM/Xen · Type 2 = VirtualBox/Workstation/Parallels · OS-level = Docker/LXC/Podman · Orchestration = Kubernetes · Intel: VT-x (CPU), EPT (memory), VT-d (DMA+interrupt remap), VT-c (sharable I/O) · GAE = PaaS with Java/Python/Go + Datastore on BigTable · S3 = object storage (buckets/objects) · EC2 types = Standard, Micro, High-Memory, High-CPU, Cluster Compute, Cluster GPU · VM migration stage 1 = Reservation · SAN = block-level, NAS = file-level.

---

## 6. LAST-MINUTE REVISION CHECKLIST
- [ ] Draw from memory: NIST layered model · hybrid cloud · IaaS/PaaS/SaaS stack + responsibility matrix · Type-1/Type-2 hypervisor · VM vs container · virtualization before/after · levels of virtualization · machine reference model (ISA/ABI/API) · Xen · Hyper-V · GAE architecture · AWS 3-tier · microservices vs monolith · CI/CD pipeline · live-migration stages
- [ ] Tables ready: Public vs Private · Scalability vs Elasticity · Web 1/2/3 · SAN vs NAS · Microservices vs Monolith · Hypervisor vs Para-virtualization · SimpleDB vs RDS · IaaS vs PaaS vs SaaS
- [ ] Lists ready: 5 characteristics · 5 deployment models · 6 EC2 types · 5 Docker commands · VM file extensions · .vmx contents · 12 cloud technologies · Intel VT quartet
- [ ] Remember: **no numericals in Module 1**; Aneka is *not* in the new syllabus (but watch your teacher's guidance since all old papers had it).
