# SDT_Mod_3 — Software Design Thinking, Module 3: Ideation in Software Design (09 hrs, CO2 / CO3 / CO4)

> **UTMOST IMPORTANT — SOURCES COVERED (carry this through the whole chat):**
> - `SDT Module 3 _ Ideation in Software Design final_V2.pptx.pdf` (160 slides; slides 59-135 are image-only and were read visually: mind-map examples, design-alternatives deck with morphological charts / analogies / 6-3-5 / C-sketch / gallery / expand-contract, Nielsen's 10 heuristics with screenshots, heuristics checklist, RICE/KANO/MoSCoW slides)
> - `SDT Module 3_Ideation in Software Design V1 (1).pptx.pdf` (57 slides; earlier version, same content, 3.3 / 3.4 / 3.5 are only title slides here)
> - `Module 3.2_Morphological Chart.docx.pdf` (Heatwave Monitoring and Heatmap System: 12-row chart, alternatives A-F, evaluation matrix)
> - `Story-boarding-vs-user-journey-mapping-notes.docx` (Smart Teaching-Learning System storyboard + journey-map table)
> - All PYQs in `../question_papers_all_time/`: 10 screenshots (ESE Jul 2024 UXD, Nov 2023 UXD, May 2023 Software Architecture & Design Thinking, Dec 2022 UXD, Nov-Dec 2021 UXD) + `User Experience Design.PDF` (ESE Jul-Nov 2025 UXD, 2 pages).
>
> **Syllabus (Module 3, 09 hrs):** 3.1 Creativity techniques: brainstorming, SCAMPER, mind mapping | 3.2 Generating multiple design alternatives | 3.3 Storyboarding and user journey mapping | 3.4 Design heuristics for software solutions | 3.5 Evaluating idea feasibility and prioritization.
>
> **Honest note on the PYQs:** the old papers are mostly for the course *User Experience Design* (UXD), plus one *Software Architecture and Design Thinking* paper (May 2023, 100% architecture, nothing for this module). Only questions that overlap Module 3 are used: storyboarding, user journey / user flow, "great questions lead to great design" (How Might We), and design heuristics. Nothing about morphological charts, SCAMPER, mind maps, feasibility or prioritization has appeared in any PYQ, so those parts are marked as expected-but-unseen.
>
> **Markers used in this file:**
> - `[PYQ]` = this topic and question type has appeared in a previous year paper (year given).
> - `[OWN]` = not in the notes or PYQs; written by me from the syllabus / general knowledge so you can prepare for questions that might come. Treat as extra, verify with your faculty's slides.
> - `[NOTES]` = taken from the slides/docs (default for anything not marked).
> - `likely` = not yet asked, but the notes give the material and a question is plausible.

---

## 1. TOPIC MAP

```
MODULE 3 : IDEATION IN SOFTWARE DESIGN
|
+-- 0. Ideation (the umbrella concept)
|   +-- Definition : generate / explore / develop MANY possible solutions to a clearly defined user problem
|   +-- Position   : after Empathize + Define (HMW question), before Prototype
|   +-- Bridge     : user needs (stories, personas, pain points)  ->  software concepts (architecture, UI/UX flows, features)
|   +-- Objectives : understand ideation, learn idea-generation methods, apply to software problems, innovate
|   +-- Why        : creativity, solves user problems, better quality, innovation
|   +-- Characteristics of a good design : user-centric, feasible, innovative, valuable, scalable
|   +-- Ideation process : understand problem -> generate -> evaluate -> select -> refine
|   +-- Diverge (many ideas)  ->  Converge (choose best)
|
+-- 3.1 CREATIVITY TECHNIQUES
|   +-- Brainstorming
|   |   +-- 5 principles : defer judgment, quantity, wild ideas, build on others, focus on a clear HMW
|   |   +-- Process : problem -> HMW -> rules -> generate -> record -> group -> evaluate -> select
|   |   +-- Example : hospital appointment system (long waiting)
|   +-- Brainwriting (6-3-5)  [also listed under 3.2 team games]
|   +-- SCAMPER : Substitute | Combine | Adapt | Modify/Magnify/Minify | Put to another use | Eliminate | Reverse/Rearrange
|   |   +-- Examples : food delivery app, college attendance, WhatsApp for students, campus visitor app, online food ordering
|   |   +-- Benefits
|   +-- Crazy 8s (8 sketches, 8 minutes, 2x4 folded A4)
|   +-- Six Thinking Hats (White, Red, Black, Yellow, Green, Blue)
|   +-- Mind Mapping
|       +-- Visual: central problem -> branches -> sub-branches (Smart College App map)
|       +-- DT tool: "yard sale" pattern-finding on exploration data -> insights -> design criteria
|       +-- Mind mapping vs Brainstorming
|
+-- 3.2 GENERATING MULTIPLE DESIGN ALTERNATIVES
|   +-- Design alternative : same components, different arrangement/implementation (REST vs GraphQL vs gRPC)
|   +-- Design space : all potential solutions (large space = many acceptable designs; small = tightly constrained)
|   +-- Morphological chart
|   |   +-- 4 steps : list functions -> list means -> combine (one per row) -> prune
|   |   +-- Number of designs = product of means per row
|   |   +-- Feasible vs infeasible combinations
|   |   +-- Examples : juice container, login feature, user authentication, Heatwave system (alternatives A-F)
|   |   +-- Evaluation matrix -> pick which to prototype
|   +-- Analogical / metaphorical thinking
|   |   +-- Analogy types : Direct | Symbolic | Fantasy
|   |   +-- Metaphors : desktop metaphor, shopping cart, trash can, Material Design
|   |   +-- Solutions : similar | contrasting | contiguous
|   |   +-- Thinking modes : Divergent | Convergent | Hybrid ("outside the box but inside the game")
|   +-- Team ideation games
|   |   +-- 6-3-5 / m-3-(m-1) brainwriting
|   |   +-- C-Sketch method
|   |   +-- Gallery method
|   +-- Design generation (goal-directed creative activity; subsystems & components)
|   +-- Navigating the design space
|       +-- Expand (too small): literature/prior art, patent/open-source search, benchmarking, reverse engineering
|       +-- Contract (too large): constraints, freeze scope, prioritise by impact, "get real" check, divide and conquer
|       +-- Final word : resources are scarce -> pick the winner
|
+-- 3.3 STORYBOARDING AND USER JOURNEY MAPPING
|   +-- Storyboard : visual sequence of scenes showing how a user uses a product / solves a problem
|   |   +-- Elements : character, context, scenes/panels, captions, goal, outcome
|   |   +-- Example : Smart Teaching-Learning System (8 steps)
|   +-- User journey map : complete experience across stages
|   |   +-- Columns : Stage | User action | Thought | Emotion | Pain point (+ opportunity)
|   |   +-- Example : Smart Teaching-Learning (Login -> Search -> Recommendation -> Learning -> Quiz -> Feedback)
|   +-- Related : User flow (screens/decisions), Wireframe vs Storyboard, UX story
|   +-- Storyboard vs Journey map (comparison)
|
+-- 3.4 DESIGN HEURISTICS FOR SOFTWARE SOLUTIONS
|   +-- Definition : rules of thumb for good design when there is no single correct answer
|   +-- Why needed : reduce complexity, usability, maintainability, reliability, decisions, reuse, scalability, consistency
|   +-- Nielsen's 10 usability heuristics
|   |   +-- Visibility of system status | Match system & real world | User control & freedom
|   |   +-- Consistency & standards (internal / external) | Error prevention | Recognition rather than recall
|   |   +-- Flexibility & efficiency of use | Aesthetic & minimalist design
|   |   +-- Help users recognize, diagnose, recover from errors | Help & documentation
|   +-- Software-design heuristics (18 in summary table)
|   |   +-- Simplicity, modularity, high cohesion, low coupling, separation of concerns, DRY, reusability,
|   |       consistency, visibility, feedback, error prevention, abstraction, scalability, security,
|   |       failure handling, design for change, patterns, trade-offs
|   +-- Practical checklist : User | Functionality | Architecture | Maintainability | Quality | Evolution
|   +-- Where used : Problem -> DT -> Ideation -> Alternatives -> HEURISTICS (evaluate) -> Conceptual design -> ... -> Prototype -> Test
|
+-- 3.5 EVALUATING IDEA FEASIBILITY AND PRIORITIZATION
    +-- Desirability (users want) | Feasibility (can build) | Viability (business should build)
    +-- Types of feasibility
    |   +-- Technical (architecture, data/integration, performance/scalability, team skills)
    |   +-- Operational (maintainability/tech debt, observability, DevOps/CI-CD)
    |   +-- Economic / resource (cloud cost, person-months)
    |   +-- Legal, security, regulatory (GDPR/CCPA/HIPAA, PCI-DSS, SOC 2, RBAC, zero-trust)
    +-- 5 feasibility concerns : stack compatibility | data availability | performance & scalability | resource & team capability | security, risk, compliance
    +-- Validation techniques : technical spike | proof of concept | architecture prototype | risk matrix
    +-- Prioritization
        +-- Value vs Effort 2x2 (Quick wins, Major projects, Fill-ins, Thankless tasks)
        +-- MoSCoW (Must, Should, Could, Won't)
        +-- KANO (Must-be, One-dimensional, Attractive, Indifferent, Reverse)
        +-- RICE = (Reach x Impact x Confidence) / Effort
        +-- Approach comparison table (best used for / strength / pitfall)
```

---

## 2. TOPIC-WISE QUESTION TYPES

**Legend:** `[PYQ yyyy]` = appeared in that year's paper. `likely` = not asked yet but the notes clearly support it. `-` = not applicable / very unlikely. Question types: **Short note** (5 M theory) | **Long answer** (10 M theory/explain with example) | **Diagram** (draw/illustrate) | **Compare** (differentiate/table) | **Numerical** (count, score, matrix, formula) | **Case / scenario** (apply to a given app) | **Objective** (MCQ / fill in the blank).

| Topic | Short note | Long answer | Diagram | Compare | Numerical | Case / scenario | Objective |
|---|---|---|---|---|---|---|---|
| Ideation (concept, process, bridge) | likely | likely | likely (process flow) | likely (diverge vs converge) | - | - | likely |
| How Might We / "Great questions lead to great design" | **[PYQ Dec 2022]** | **[PYQ Nov 2023]** (map to research + journey) | - | - | - | **[PYQ Nov 2023]** (with example) | - |
| Brainstorming | likely | likely | likely (process flow) | likely (vs mind map) | - | likely (HMW for a given app) | - |
| Brainwriting 6-3-5 / C-sketch / Gallery | likely | likely | likely (rotation sheet) | likely | likely (ideas count: 6x3x6 = 108) | - | - |
| SCAMPER | likely | likely | - | - | - | likely (apply to food app / LMS / library) | - |
| Crazy 8s | likely | - | likely (2x4 sketch grid) | - | - | likely | - |
| Six Thinking Hats | likely | - | likely (hat table) | - | - | likely | - |
| Mind mapping | likely | likely | likely (draw a map for given app) | likely (vs brainstorming) | - | likely | - |
| Design alternatives / design space | likely | likely | - | likely (alternative vs design space) | - | - | likely |
| Morphological chart | likely | likely | likely (chart) | - | likely (number of designs, evaluation matrix) | likely (login, heatwave, juice container) | likely |
| Analogies / metaphors / divergent-convergent | likely | likely | - | likely (direct vs symbolic vs fantasy) | - | - | likely |
| Expanding / contracting design space | likely | likely | - | likely | - | - | - |
| Storyboarding | **[PYQ Dec 2022]** | **[PYQ Nov 2023]** (UX stories) | **[PYQ Dec 2022]** implied (storyboard panels) | **[PYQ Jul 2025]** (vs wireframing) | - | likely (storyboard for a given app) | **[PYQ Nov-Dec 2021]** (wireframing & storyboard = static & static) |
| User journey mapping | likely | **[PYQ Nov 2023]** (Q2A OR, 10 M) | likely (journey map table / emotion curve) | likely (vs storyboard, vs empathy map) | - | likely (map for given app) | - |
| User flows | - | **[PYQ Nov 2023]** (Q3 ii, 10 M) | **[PYQ Nov 2023]** (flow diagram expected) | likely (vs journey map) | - | likely | - |
| Design heuristics (Nielsen 10) | likely | **[PYQ Dec 2022]** (any 5 with examples, 10 M) | likely | likely (heuristic vs principle) | - | **[PYQ Jul 2025]** (Smart Home App, 10 M) | **[PYQ Nov-Dec 2021]** (heuristic evaluation is a method of ...) |
| Software-design heuristics (cohesion, coupling, DRY ...) | likely | likely | - | likely (cohesion vs coupling) | - | likely | likely |
| Feasibility (technical / operational / economic / legal) | likely | likely | - | likely (types) | - | likely (assess an idea) | likely |
| Validation (spike, PoC, prototype, risk matrix) | likely | likely | - | likely (spike vs PoC) | - | - | likely |
| Prioritization (Value-Effort, MoSCoW, KANO, RICE) | likely | likely | likely (2x2 matrix, KANO curve) | likely (comparison table) | likely (RICE score, rank features) | likely (classify features of app) | likely |

**Pattern the PYQs show (important):**
1. Module-3-type questions appeared in **every UXD paper from Nov 2021 to Jul 2025**, but only for **three families**: (a) storyboard / wireframe / user story / user flow / journey, (b) "great questions lead to great design", (c) **design heuristics** (the most repeated and highest weighted: 10 M in Dec 2022 and 10 M in Jul 2025).
2. Heuristics are asked both **generically** (Dec 2022: "any five with examples") and as a **case study** (Jul 2025: Smart Home App). Practise applying all 10 to any given app.
3. Storyboarding appears as a 5 M question 3 times (Dec 2022 justify, Nov-Dec 2021 MCQ, Jul 2025 vs wireframing). Expect a 5 M short note again.
4. No numericals have appeared. The only numerical-style items are the morphological chart combination count, the 6-3-5 idea count, the weighted evaluation matrix and the RICE score. All four are `likely` for a university paper that has an "ideation" module.
5. Marks pattern: Q1 style 5-mark short notes (attempt 4 of 6), Q2-Q4 10-mark long answers. Module 3 is likely to supply one 10 M and one or two 5 M.

---

## 3. TOPIC-BY-TOPIC DETAILED BREAKDOWN

### 3.0 Ideation (the umbrella concept)

**Easy explanation:** After you understand the user (Empathize) and write the problem as a "How Might We" question (Define), you stop thinking about one perfect answer and instead produce **lots of possible answers**. That stage is ideation. You decide which one to build only afterwards.

**Short note (5 M) — how to write:**
> *Ideation is the process of generating, exploring and developing multiple possible solutions to a clearly identified user problem. In software design it comes after understanding the user and defining the problem, and before prototyping. It acts as a bridge between user needs (user stories, personas, pain points) and concrete software concepts (architecture, UI/UX flows, feature sets, technical implementations), so that abstract problems become high-value, technically sound concepts before costly development begins. The aim is not to find the perfect solution at once but to explore a wide range of possibilities. Ideation process: understand problem, generate ideas, evaluate ideas, select best ideas, refine ideas. Benefits: encourages creativity, solves user problems, improves software quality, promotes innovation.*

**Diagram to draw (ideation process / diverge-converge):**

```
Empathize -> Define (HMW) -> [ IDEATE ] -> Prototype -> Test
                               |
        Understand problem -> Generate ideas -> Evaluate -> Select best -> Refine
                               \___ DIVERGE ___/ \______ CONVERGE ______/
                           many ideas, no judgment    filter with feasibility,
                                                      heuristics, prioritization
```

**Characteristics of a good design [NOTES]:** user-centric, feasible, innovative, valuable, scalable.

**Where each syllabus topic sits (use this as the story of the module):**

```
Generate ideas  : 3.1 brainstorming, SCAMPER, mind map (+ 3.2 morph chart, analogies, 6-3-5)
Shape ideas     : 3.3 storyboard, journey map (make the idea experiential)
Judge ideas     : 3.4 heuristics (is it a good design?)  and  3.5 feasibility + prioritization (can we build it, what first?)
```

---

### 3.1 Creativity techniques: brainstorming, SCAMPER, mind mapping

#### 3.1.1 Brainstorming

**Easy explanation:** A group tries to produce as many ideas as possible about a problem **without criticising any idea** at the start. Quantity first, quality later.

**Short note (5 M):**
> *Brainstorming is a group creativity technique in which participants generate a large number of ideas for a problem without judging or criticising them during the generation phase. Objective: generate quantity first, evaluate quality later.*
>
> **Key principles:** (1) **Defer judgment** - never say "that won't work"; record it and evaluate later. (2) **Encourage quantity** - many ideas rather than one perfect one. (3) **Encourage wild ideas** - unusual ideas lead to practical innovation, e.g. "What if students could talk to the college ERP like ChatGPT?" (4) **Build on others' ideas** - Student A: "Send attendance notifications." Student B: "Add prediction to warn if attendance may fall below 75%." (5) **Keep the problem clearly defined** - focus on one HMW question, e.g. "How might we help students manage academic deadlines?"

**Diagram to draw (process):**

```
Identify problem
      |
Define HMW question
      |
Set rules
      |
Generate ideas
      |
Record ideas
      |
Group similar ideas
      |
Evaluate
      |
Select best ideas
```

**Worked example from the slides - Hospital Appointment System**
- Problem: patients spend too much time waiting.
- HMW: How might we reduce the waiting time of patients at the hospital?
- Ideas: online appointment booking, digital token, live queue tracking, doctor availability indicator, SMS notification, estimated waiting time, video consultation, AI symptom pre-screening, automatic appointment reminders, self-service kiosk.
- Group: *Before arrival* (online booking, reminders, AI pre-screening) | *At the hospital* (digital token, kiosk, live queue, doctor availability, waiting time) | *Alternate channel* (video consultation, SMS).
- Evaluate with feasibility and value, then select (e.g. online booking + digital token + live queue + SMS).

**Activities given in the slides (practise HMW-and-ideas for these):** "How can we improve the college library experience?", "How can I improve the LMS experience?"

#### 3.1.2 Brainwriting (6-3-5)

Covered in detail in 3.2 (team ideation games). One-line summary for this section: *to stop dominant voices from hijacking a brainstorm, 6 people write 3 ideas each on a sheet in 5 minutes, pass the sheet right, and the next person builds on it; after 6 rounds 108 ideas exist in 30 minutes.*

#### 3.1.3 SCAMPER

**Easy explanation:** Instead of "what brand-new software should we make?", ask "how can we **change the existing software**?" using seven prompts. Each letter is a question that pushes you to a new idea.

**Short note (5 M):**
> *SCAMPER is a structured creativity technique used to modify an existing product, service, process or idea to generate new alternatives. Instead of asking "What new software should we create?" we ask "How can we change the existing software?"*

| Letter | Meaning | Question to ask | Example (Food Delivery App - from slides) |
|---|---|---|---|
| S | Substitute | What can be replaced? (technology, interface, process, input, output, interaction) | Replace manual customer support with a 24/7 AI chatbot |
| C | Combine | What can be combined? | Food + grocery + medicine delivery in one app |
| A | Adapt | What idea from another industry can be used? | Adapt ride-sharing live GPS tracking to show the delivery partner's location |
| M | Modify / Magnify / Minify | What can be changed, enlarged, reduced, simplified? | Voice ordering, larger food images, personalised restaurant recommendations |
| P | Put to another use | Can the app serve another purpose / user group? | Book catering or bulk lunch orders for office meetings and events |
| E | Eliminate | What can be removed (features, screens, steps, forms, approvals)? | Remove lengthy registration: login with Google/Apple/phone OTP; one-tap reorder |
| R | Reverse / Rearrange | What if the order or roles were flipped? | Pick the delivery time/location first, or suggest dishes first by preference and budget, then show restaurants offering them |

**More examples from the slides (for variety in exams):**
- *Substitute:* biometric -> QR code -> face recognition -> mobile NFC for attendance; phone call -> AI chatbot for support.
- *Combine:* timetable + attendance + assignments + notifications = "Student Academic Assistant"; maps + food delivery + reviews = location-based restaurant recommendations; fitness tracker + diet planner + doctor consultation = health platform.
- *Adapt:* banking "swipe" -> job app (swipe right = apply, left = skip); Uber live tracking -> school bus, ambulance, college shuttle tracking.
- *Modify:* ERP with 20 menu options -> My Attendance, My Timetable, My Assignments, My Fees, My Exams; e-commerce search "products under Rs 2,000 suitable for a college student".
- *Put to another use:* QR code used for payments -> attendance, library tracking, event registration, visitor management; GPS from food delivery -> college bus tracking.
- *Eliminate:* Cart -> Address -> Delivery option -> Coupon -> Payment -> Confirmation becomes Cart -> One-click checkout -> Payment.
- *Reverse:* normal: search restaurant -> select food -> order. Reversed: AI learns preferences -> suggests food -> customer selects.

**Worked "improve WhatsApp for college students" answer (from slides):**

| SCAMPER | Idea |
|---|---|
| Substitute | Replace text announcements with short voice/video announcements |
| Combine | Combine WhatsApp with the college timetable |
| Adapt | Adapt disappearing messages for temporary assignment reminders |
| Modify | Create a dedicated academic dashboard inside the app |
| Put to another use | Use WhatsApp groups for automated attendance notifications |
| Eliminate | Remove repetitive messages with automated FAQs |
| Reverse | Instead of students asking faculty, an AI bot proactively provides updates |

**Exam template for "apply SCAMPER to app X" (the slides' activity: "Online Food Ordering - provide a new version; mention changes in functionality, appearance, performance"):** draw a 3-column table `Step | Version 1 (Existing) | Version 2 (Suggested)` and fill all seven rows, tagging each as functionality / appearance / performance. See the full worked example in Section 4 (D1).

**Benefits of SCAMPER [NOTES]:** encourages creative thinking, improves UX, increases customer satisfaction, enhances functionality, creates competitive advantage, helps spot business opportunities.

**From many ideas to selected ideas (slide example):**

| Idea | Feasible | User value |
|---|---|---|
| AI recommendations | High | High |
| Voice ordering | Medium | High |
| Live tracking | High | High |
| Drone delivery | Low | High |

Selected: AI recommendations, live order tracking, voice search, one-click reorder. (Drone delivery dropped for low feasibility.) This is a tiny example of ideate -> evaluate -> select.

#### 3.1.4 Crazy 8s

**Easy explanation:** Fold a paper into 8 boxes, set a timer for 8 minutes, sketch one different idea per box (about one minute each). Speed beats polish.

**Short note (5 M):**
> *Crazy 8s is a rapid ideation technique used in the Ideate phase. Participants sketch eight different ideas in eight minutes. "Crazy" = bold, unconventional ideas; "8s" = eight sketches; "8 minutes" = about one minute per sketch. It stresses speed, creativity and quantity over perfection.*
>
> **Materials:** A4 sheet, pencil/pen, timer. **Steps:** (1) define the problem, (2) fold A4 into 8 sections (2 x 4), (3) set timer for 8 minutes, (4) sketch one idea per box (stick figures, icons, arrows), (5) share and discuss, (6) select best ideas on user needs, feasibility, innovation, cost, ease of implementation.
>
> **Advantages:** many ideas quickly, encourages innovation, prevents overthinking, equal participation, multiple solution paths. **Limitations:** time pressure, needs basic sketching (artistic skill not needed), some ideas unrealistic.

**Diagram:**

```
+------+------+------+------+
|  1   |  2   |  3   |  4   |     8 boxes (A4 folded 2 x 4)
+------+------+------+------+     1 idea per box, 1 minute each
|  5   |  6   |  7   |  8   |
+------+------+------+------+
```

**Slide example - university cafeteria food ordering:** 1 voice ordering, 2 AI meal recommendations, 3 one-click reorder, 4 QR-code menu scanning, 5 live kitchen preparation status, 6 group ordering with friends, 7 meal subscription plans, 8 AR view of food before ordering.

#### 3.1.5 Six Thinking Hats

**Easy explanation:** Edward de Bono's method. The whole team puts on **the same colour hat at the same time**, so everyone thinks in one mode instead of arguing from different angles at once.

| Hat | Purpose | Focus questions | Food-delivery example (slides) |
|---|---|---|---|
| White | Facts and information | What do we know? What data is needed? | Users wait an average of 40 minutes |
| Red | Emotions and intuition | How do users feel? What are our instincts? | Users feel frustrated when delivery is delayed |
| Black | Risks and caution | What could go wrong? Limitations? | Heavy traffic may cause late deliveries |
| Yellow | Benefits and optimism | Advantages? Why will it work? | Live order tracking increases satisfaction |
| Green | Creativity and new ideas | What innovative solutions can we generate? | AI route optimisation and voice ordering |
| Blue | Process and control | What is our plan? What next? | Pick best ideas, prototype, test with users |

**Why use:** encourages creative thinking, improves teamwork, reduces conflict, ensures all perspectives are considered, better design decisions. **Limitations:** needs practice, can take more time if poorly managed, needs active participation.

**Mnemonic:** *Wise Red Boys Yell Great Blues* = White, Red, Black, Yellow, Green, Blue. [OWN mnemonic]

#### 3.1.6 Mind Mapping

**Two meanings are in the notes - know both.**

**(a) Mind map as a visual brainstorming tool (slides 49, 53-55)**
> *Mind mapping is a visual technique for organising information and exploring relationships between ideas around a central topic. The core problem or idea is placed in the centre and expands outward into categorised branches and sub-branches of words, themes and user insights. Instead of generating ideas randomly, ideas are organised hierarchically.*

**Diagram to draw (slide example - Smart College App):**

```
                          SMART COLLEGE APP
                                  |
     +------------+-------------+-+-----------+---------------+
     |            |             |             |               |
 Attendance     Exams          Fees         Library       Placement
     |            |             |             |               |
 - Percentage  - Schedule    - Payment     - Search        - Jobs
 - Alerts      - Results     - Receipt     - Issue         - Resume
 - Prediction  - Forms       - History     - Return        - Interview
```

Other slide example: "Content Marketing Ideas" in the centre with branches blog posts, webinars, podcasts, videos, white papers, user-generated content, social media posts, infographics.

**(b) Mind mapping as a Design Thinking tool (slides 50-52, same as Module 1's "What is?" tool)** - generating insights from exploration data and turning them into **design criteria** for the "What if" (idea generation) stage. Steps:
1. **Hold a yard sale** - lay out all collected data for everyone to see.
2. **Invite shoppers** - 10 to 50 thoughtful people lend their intuition for a day/afternoon.
3. **Offer tours** - walk the room, briefly explaining each visual.
4. **Pick out the good stuff** - browse silently, note learnings on Post-its.
5. **Cluster the good stuff** - sort Post-its into themes; unassigned notes go in the margins as "outliers" (do not ignore them).
6. **Identify insights** per cluster and connections between clusters.
7. **Translate into design criteria** - "Based on what you have learned, if anything were possible our design would ..."

**Mind Mapping vs Brainstorming [NOTES] (very likely table question):**

| Brainstorming | Mind Mapping |
|---|---|
| Mainly generates ideas | Organises and connects ideas |
| Individual or group | Usually visual; individual or group |
| Focuses on quantity | Focuses on relationships |
| Ideas initially unstructured | Ideas arranged hierarchically |
| Example: generate 20 app ideas | Example: organise app features into categories |

**Best combination (say this as a closing line):** brainstorm first to get many ideas, then mind-map them to cluster and structure.

---

### 3.2 Generating multiple design alternatives

**Why this topic exists:** the first idea is rarely the best. A team should lay out several complete designs and compare them. The slides explain how to build, shrink and grow that set.

#### 3.2.1 Design alternative and design space

- **Design alternative:** when a system can be built in different ways that all meet the same requirements, using the same kinds of components but arranging or implementing them differently, each build is a design alternative.
  - Example: "let clients fetch and update product data": **REST API** (resource endpoints, wide tooling) vs **GraphQL** (single endpoint, client-shaped queries) vs **gRPC** (binary protocol, fast service-to-service).
- **Design space:** the imaginary region of all potential solutions to the problem (every combination of architecture, stack and interaction pattern that could satisfy the requirements).
  - Large design space = many acceptable designs, often many design variables. Small design space = tightly constrained / limited choices, or not fully explored.
  - Naming the space early gives the team a shared feel for how much room they have.
  - Tools: **morphological chart** (formal tool to generate/define the space) and **analogical thinking** (another approach).

#### 3.2.2 Morphological chart (highest-value topic in 3.2)

**Easy explanation:** A table. **Rows = functions** the system must perform. **Columns = different means** (ways) of doing each function. Choose **one means from each row** and join them: that is one complete design. Do it differently and you get another design. Then cross out combinations that clash.

**Short/long note — how to write:**
> *A morphological chart is a matrix in which the leftmost column lists all principal functions (and key features) that the design must perform, and each row to the right lists the different means of realising that function. A complete design concept is assembled by choosing one means from every row. It is a tool both to develop a design space and to prune it by excluding infeasible or incompatible alternatives.*
>
> **Steps:** (1) **List functions** - every function the system must deliver, one per row; (2) **List the means** - distinct ways to implement each function; (3) **Combine** - pick one means per row, which gives one candidate design; (4) **Prune** - cross out combinations that clash or break constraints (interface constraints, physical/technical principles, security, common sense).
>
> **Guidelines:** keep the list a manageable size; functions and features at the same level of detail; separate functions from key features (the chart can become large, may use two charts); do not develop highly detailed designs at the conceptual stage; every function in the leftmost column must be achieved by the design; some functions may have more means than others; a small number of means signals a small design space / unexplored space; for large systems list principal subsystems first and make charts per subsystem.

**Diagram to draw (blank layout, slide 9):**

```
FUNCTION \ MEANS |   1   |   2   |   3   |   4   |   5   |   6
-----------------+-------+-------+-------+-------+-------+------
Function 1       |  [ ]  |  [x]  |  [ ]  |  [ ]  |  [ ]  |
Function 2       |  [x]  |  [ ]  |  [ ]  |  [ ]  |  [ ]  |
Function 3       |  [ ]  |  [ ]  |  [ ]  |  [x]  |  [ ]  |
Function 4       |  [ ]  |  [x]  |  [ ]  |  [ ]  |       |
(one means chosen per row = one design alternative; join the choices with a line)
```

**Numerical 1 - number of possible designs = product of the number of means in each row**

Slide example: **Juice container design** (functions and means as printed on the slides):

| Function | Means | Count |
|---|---|---|
| Contain liquid | Can, Bottle, Bag, Box | 4 |
| Fill and seal container | Fill-and-heat seal, Sealed cap, Glue container material, Twist top, Bottle cap | 5 |
| Empty container | Pull tab, Inserted straw, Twist top, Tear corner, Unfold container, Zipper | 6 |
| Resist forces | Thick walls, Flexible materials | 2 |
| Identify product | Shape of container, Distinctive label, Color | 3 |

Total designs = 4 x 5 x 6 x 2 x 3 = **720** possible combinations (before pruning). [counts read from the slide; the blank "...." cells were not counted. The calculation method itself is [NOTES] "helps compute the number of potential designs"; the figure 720 is my arithmetic.]

**Feasible vs infeasible (slides):**
- Feasible example: *Bag* + *Fill-and-heat seal* + *Tear corner* + *Flexible materials* + *Distinctive label* (a pouch-type pack). [OWN selection consistent with the slide idea]
- Infeasible example: *Bottle* + *Unfold container* + *Flexible materials* (a rigid bottle cannot unfold and be flexible); *Bottle cap* on a *Bag*. Rule: apply interface constraints, physical principles and plain common sense.

**Slide example 2 - Login feature (software):**

| Function | Means 1 | Means 2 | Means 3 | Means 4 |
|---|---|---|---|---|
| Auth method | Email + password | OAuth (Google/GitHub) | Biometric | Magic link |
| Session handling | JWT (stateless) | Server session + cookie | Token in localStorage | - |
| UI pattern | Modal overlay | Full-page form | Inline embedded | - |
| Password recovery | Email reset link | SMS OTP | Security questions | - |

Highlighted selection: **OAuth + JWT + Modal + Email reset link** (feasible: widely supported, keeps auth stateless for scaling). **Infeasible:** Biometric + localStorage + Security questions (localStorage tokens are XSS-exposed; security questions are a weak recovery path).
Count = 4 x 3 x 3 x 3 = **108** combinations. [OWN arithmetic]

**Slide example 3 - User authentication system:** 5 sub-functions x 3 options (Simple / Standard / Advanced): primary identifier (username/email, phone number, FIDO2 key), verification (static password, 6-digit SMS OTP, biometrics), session state storage (client cookies, server Redis cache, distributed JWT), login UI trigger (page redirect, pop-up modal, magic link / inline), failure handling (simple error text, captcha + lockout, rate limiting + risk-based challenge). Combinations = 3^5 = **243**. [OWN arithmetic]

**Slide/Doc example 4 - Heatwave Monitoring and Heatmap System (Module 3.2 doc)**
Problem (HMW): *How might we identify heat-stressed areas in a city and provide timely information to citizens and authorities?*

| Function | Alt 1 | Alt 2 | Alt 3 | Alt 4 |
|---|---|---|---|---|
| Temperature data collection | IoT sensors | Weather stations | Satellite data | Crowd-sourced data |
| Location tracking | GPS | GIS coordinates | Mobile location | Fixed zones |
| Heat calculation | Threshold rules | Heat index | ML prediction | Spatial analysis |
| Heatmap generation | GIS heatmap | Web map | Raster map | Interactive map |
| Data processing | Cloud | Edge | Local server | Hybrid |
| Prediction | Statistical model | ML | Deep learning | No prediction |
| Alert generation | SMS | Push notification | Email | Voice alert |
| User interface | Mobile app | Web dashboard | GIS dashboard | Chatbot |
| Target user | Citizen | Municipality | Health department | Disaster management |
| Visualization | Color heatmap | Risk zones | Charts | 3D map |
| Historical analysis | Daily | Weekly | Monthly | Seasonal |
| Recommendation | Stay indoors | Cooling center | Route suggestion | Water reminder |

12 functions x 4 means = 4^12 = **16,777,216** theoretical combinations. Key teaching message: *we do not pick randomly; we create meaningful combinations.* A morphological chart does not give you the solution; it gives a structured design space from which several solutions can be constructed.

Design alternatives built from the chart:
- **A - IoT Smart Heatmap:** IoT sensors -> GPS -> heat index -> cloud -> GIS heatmap -> web dashboard -> municipality.
- **B - Satellite-based:** satellite data -> GIS coordinates -> spatial analysis -> cloud -> raster heatmap -> web GIS -> disaster management. Advantage: large geographic coverage.
- **C - Citizen-based:** mobile location + crowdsourced temperature -> ML -> interactive heatmap -> mobile app -> citizen.
- **D - Predictive heatwave:** weather stations + satellite + historical data + IoT -> ML -> prediction -> risk heatmap -> early warning -> citizens + authorities. Answers "which areas will be dangerous tomorrow?" not just "where is it hot now?"
- **E - Smart heatwave + safe route:** heatmap + road network + weather -> route engine -> heat-safe route (e.g. "Route B is 7 minutes longer but has lower heat exposure"). Turns a visualisation tool into a decision-support system.
- **F - Health risk:** temperature + humidity + heat index -> risk model + population information -> heat-risk map -> high-risk zones -> targeted alerts (red high / orange / green low). Authorities prioritise interventions.

Design-space picture (draw this):

```
                 HEATWAVE MONITORING
                          |
       +------------------+------------------+
       |                  |                  |
   Data source        Processing          Interface
   IoT / Satellite   Rules / ML / GIS    Web / Mobile / GIS / Chatbot
   Weather stn       Heat index           
   Citizen data      Prediction           
       +------------------+------------------+
                          |
                  MULTIPLE DESIGNS
```

**Final evaluation matrix (from the doc) - numerical / selection question**

| Criteria (score 1-5) | A | B | C | D |
|---|---|---|---|---|
| User value | 5 | 4 | 5 | 5 |
| Feasibility | 5 | 4 | 3 | 3 |
| Cost (5 = cheaper) | 4 | 3 | 5 | 3 |
| Scalability | 4 | 5 | 3 | 5 |
| Innovation | 3 | 4 | 5 | 5 |
| **Total** | **21** | **20** | **21** | **21** |

Unweighted, A, C and D tie at 21. To break the tie use **weights**. [OWN worked tie-break, weights are an assumption: user value 30%, feasibility 25%, cost 15%, scalability 15%, innovation 15%]

| | A | B | C | D |
|---|---|---|---|---|
| User value x 0.30 | 1.50 | 1.20 | 1.50 | 1.50 |
| Feasibility x 0.25 | 1.25 | 1.00 | 0.75 | 0.75 |
| Cost x 0.15 | 0.60 | 0.45 | 0.75 | 0.45 |
| Scalability x 0.15 | 0.60 | 0.75 | 0.45 | 0.75 |
| Innovation x 0.15 | 0.45 | 0.60 | 0.75 | 0.75 |
| **Weighted total** | **4.40** | **4.00** | **4.20** | **4.20** |

Answer: prototype **A** first (highest user value and feasibility, which suits a first prototype); C or D can follow in later iterations. This links *generate alternatives -> evaluate -> prototype*.

**Design Thinking twist (5 questions asked after choosing, from the doc):** Who is your primary user? What problem (pain point) does it solve? Why these technologies? Is it realistically feasible? What makes it different from existing systems (innovation)?

#### 3.2.3 Analogical and metaphorical thinking

**Easy explanation:** When you face a blank page, borrow structure from something familiar. Computers have "folders" and a "trash can" because we borrowed from an office.

**Short note (5 M):**
> *An analogy points out parallels between a new problem and something already familiar, giving a way to generate ideas without a blank page. A metaphor is a figure of speech that likens an object or process to a more familiar object or process.*
>
> **Types of analogy:** **Direct** - look for parallels or similarities (the shopping cart in e-commerce). **Symbolic** - draw connections through some underlying symbolism (files and folders standing in for paper). **Fantasy** - imagine something literally fantastic or beyond belief, "thinking outside the box" (a voice assistant as a companion).
>
> **Common software analogies:** Shopping cart (checkout mimics physical retail carts); Trash can (file deletion mimics throwing paper in a bin); Material Design (Google mapped digital layers to physical paper and ink responding to light and touch); **Desktop metaphor** (screen = office desk, files = paper documents, folders hold documents, trash = deletion), which helps users understand abstract computing functions instantly.
>
> **Metaphorical solutions:** *Similar* solutions (look for similar ideas), *Contrasting* solutions (look for opposite ideas), *Contiguous* solutions (adjacent ideas; natural connections between ideas, concepts, artifacts).

**Thinking modes (very exam friendly):**

| Mode | Meaning | Slogan |
|---|---|---|
| Divergent | Remove limits/barriers to increase the store of design ideas and choices; widen | "Think outside the box" |
| Convergent | Narrow the design space; focus on the best alternative(s); weigh against constraints and goals | "Stay within the game" |
| Hybrid (metaphorical thinking) | Mix both | "Think outside the box, but stay within the game" |

#### 3.2.4 Team ideation games

**A) 6-3-5 method (brainwriting)** - [NOTES]
> Design in a team setting. **Six** team members sit around a table and take part in an idea-generation "game". Each writes **three** design ideas in key words/phrases. The six lists are circulated past each remaining member in **five** rotations of written (only) comment and annotation. Verbal communication or cross-talk is not allowed. Each list makes a complete circuit; each member is stimulated by the increasingly annotated lists of others and comments on every list. The team then lists, discusses, evaluates and records all ideas in a common visualisation medium (projector, board).
> **General form:** m members use (m - 1) rotations: **m-3-(m-1)** method. Natural upper limit m = 6, prefer fewer.
> **4 steps:** Write -> Pass -> Build -> Converge.

**Numerical 2 - ideas produced** [arithmetic: slide says 108 ideas in 30 minutes]
- m = 6: sheets = 6, each sheet gets 1 initial entry of 3 ideas and goes through 6 rounds in total (1 writing round + 5 rotations), each round 5 minutes. Ideas = 6 members x 3 ideas x 6 rounds = **108** ideas, time = 6 x 5 = **30 minutes**.
- Generalised: ideas = m x 3 x m = 3m^2, time = 5m minutes. [OWN generalisation]
- Example: m = 4 -> 4-3-3 method: 3 x 16 = **48** ideas in **20 minutes**; rotations = m - 1 = 3. [OWN example]

**Diagram (sheet for one participant):**

```
Sheet of Person 1            Round 1 : P1 writes 3 ideas
+------+--------+--------+--------+   Round 2 : P2 reads, adds 3 (extends)   -- pass right, silent
| Row  | Idea 1 | Idea 2 | Idea 3 |   Round 3 : P3 ...  ...  Round 6 : P6
+------+--------+--------+--------+   After the last round -> team converges and evaluates
| P1   |        |        |        |
| P2   |        |        |        |
| ...  |        |        |        |
+------+--------+--------+--------+
```

**B) C-Sketch method** - sketching as a natural form of thinking. Team seated around a table; each member sketches **one** design idea on paper, then it proceeds like 6-3-5 (sheets rotate, others add or modify). The only permissible communication is by pencil on paper. Appealing in areas like mechanical design; drawings and diagrams help group relevant information and visualise objects.

**C) Gallery method** - [NOTES]
1. Each member independently develops initial ideas within a time box.
2. All sketches are posted on a corkboard / whiteboard / shared board (e.g. Figma) as backdrop for open group discussion: questions, critiques, suggestions.
3. Each participant returns to his/her drawing and revises it within a time limit -> a second-generation idea (iterative and progressive).
4. Repeat until a consensus emerges / until one more cycle gains no new information (saturation plateau). Number of cycles cannot be predicted.

**Comparison (likely 5 M "differentiate"):** [OWN synthesis from the notes]

| Aspect | 6-3-5 | C-Sketch | Gallery |
|---|---|---|---|
| Medium | Written keywords | Sketches | Sketches posted on wall/board |
| Communication | Silent, written | Silent, pencil only | Open discussion and critique |
| Cycle | Fixed (m-1) rotations | Same as 6-3-5 | Repeats until saturation |
| Output | Many annotated idea lists | Annotated sketches | Second-generation sketches |

#### 3.2.5 Design generation and navigating the design space

**Design generation** is an exciting **goal-directed creative activity**: designed to serve a known purpose, not to search for one; the goal may be imposed externally or internally; creative activity requires work. Beyond the morph chart and team tools, designers must navigate/expand/contract the design space, design more subsystems and components, and combine and connect the subsidiary designs.

**Large design spaces** are complex: hundreds or thousands of design variables, interactions between subsystems and components, collaboration with many specialists is critical -> **divide and conquer**, contract when too large. **Small/bounded spaces:** number of potential designs is limited, or variables are few with limited ranges; individual components of large systems are designed within small spaces -> **expand** when too small.

| Know when to... | Expand (space too small / too few options) | Contract (space too large / complex) |
|---|---|---|
| Example | A single microservice, a form rule, a caching layer | Platform migration, multi-service architecture with dozens of variables |
| Techniques | **Prior art & literature** (RFCs, engineering blogs; literature review, state of the art) | **Apply constraints** (latency, scale, security, cost; check external constraints) |
| | **Open-source search** / patent search (reuse libraries; do not reinvent the wheel) | **Freeze scope early** (defer nice-to-haves; freeze number of features and behaviours) |
| | **Competitor benchmarking** (try competing products) | **Prioritise by impact** (rank against real requirements; impose order using data from problem definition) |
| | **Reverse engineering** (inspect how existing APIs/products achieve a function; identify alternate means) | **"Get real" check** (plain engineering judgment to rule out infeasible ideas) |

**Final word:** there is a sea of alternatives; resources (time, money, manpower) are scarce. Blend morph charts, design-generation games, research, experience-based judgment and gut feeling, group and reorganise functions and alternatives, then **pick the winner**. The goal was never to keep every alternative alive; it was to generate enough of them to make a confident choice.

---

### 3.3 Storyboarding and user journey mapping

> Note: the slide deck only has title slides for this topic. The content below is from `Story-boarding-vs-user-journey-mapping-notes.docx`, the PYQs (Dec 2022, Nov 2023, Jul 2025, Nov-Dec 2021), and my own expansion where marked [OWN].

#### 3.3.1 Storyboarding

**Easy explanation:** A storyboard is a comic strip of your design. Each panel is one moment: a person with a problem, then using your software, then a better outcome. It lets the team and stakeholders **see** and **feel** the idea before any code exists.

**Definition (from the notes):** *A storyboard is a visual sequence of events that describes how a user interacts with a product or solves a problem. It is a visual representation of a user's experience through a sequence of scenes or events.*

**Example from the notes - Smart Teaching-Learning System (draw this as 8 panels):**

```
[1 Student has     [2 Student opens   [3 Logs into       [4 App identifies
   difficulty]  ->    app]         ->    account]      ->    weak subject]
                                                                  |
[8 App gives       [7 Student takes   [6 Student studies  [5 App recommends
   feedback]    <-    quiz]        <-    material]      <-    learning material]
```

**Parts of a good storyboard [OWN]:** character (persona), context/setting, problem/trigger, scenes (panels) in order, captions or dialogue, the interaction with the product, outcome/emotion at the end.

**How to create [OWN]:** (1) pick the persona and one key scenario from research; (2) write the story in 6-8 steps (start, trigger, interaction, resolution); (3) sketch a rough panel per step (stick figures are enough) with one-line captions; (4) add the user's emotion in each panel; (5) review with team/stakeholders and revise; (6) use it to decide features and as input for wireframes and prototype.

**Why it is useful (justify points) [PYQ Dec 2022 "A storyboard is a great way to tell the stories. Justify."]:** shows the problem in context, builds empathy, communicates the idea to non-technical stakeholders, aligns the team on one story, finds gaps in the flow early and cheaply, supports idea evaluation before development, is quick and low-fidelity (anyone can draw it), and keeps focus on the user's goal rather than on technology.

#### 3.3.2 User journey mapping

**Easy explanation:** A storyboard tells the story of **one scenario**. A journey map zooms out and records **the whole experience over time**, stage by stage, including what the user **thinks and feels** and where they **struggle**.

**Definition (from the notes):** *A user journey map represents the complete experience of a user while interacting with a product, service or system.*

**Example from the notes - Smart Teaching-Learning Application:**

| Stage | User action | User thought | Emotion | Pain point |
|---|---|---|---|---|
| Login | Opens application | "I need to study." | Neutral | Login may take time |
| Search | Searches for topic | "Where can I find notes?" | Negative / frustrated | Too many resources |
| Recommendation | Views recommended content | "This looks useful." | Positive / happy | - |
| Learning | Studies video/notes | "Now I understand." | Neutral (mixed) | Difficult topic |
| Quiz | Attempts quiz | "How well did I perform?" | Anxious | Questions may be difficult |
| Feedback | Checks score | "I need more practice." | Negative / concerned | Limited explanation |

(The Emotion column in the source file uses face symbols; I have written them out as words. "?" = neutral/mixed, "bad" = negative, "good" = positive, "anx" = anxious.)

**Emotion curve to draw (optional, shows high/low points) [OWN rendering of the notes' table]:**

```
Emotion
 +  |                  *                    (Recommendation: good)
 0  |  *                      *
 -  |        *                      *   (Search: bad)       (Feedback: bad)
    |             . Quiz: anxious .
    +---------------------------------------------------------------> Stages
      Login  Search  Recommend  Learning  Quiz  Feedback
```

**Components of a journey map [OWN, standard]:** persona/actor and goal; stages (phases); user actions; touchpoints/channels; thoughts; emotions (curve); pain points; **opportunities** for design improvement. The low points of the emotion curve are where ideation (SCAMPER, HMW) should be aimed. Example opportunity from the table above: Search - "Too many resources" -> AI recommendation / filters; Feedback - "Limited explanation" -> detailed answer explanations and practice sets.

**How to create a journey map [OWN]:** define persona and goal -> list stages -> record actions, thoughts, emotions per stage (from interviews/observation) -> mark pain points and plot emotion curve -> identify opportunities -> prioritise and redesign -> validate with users.

#### 3.3.3 Storyboard vs User journey map (table for a 5 M differentiate)

| Aspect | Storyboard | User journey map |
|---|---|---|
| Meaning | Visual sequence of scenes/events showing how a user interacts with a product or solves a problem | Complete experience of a user while interacting with a product, service or system |
| Scope | One specific scenario / interaction | Whole end-to-end experience across stages |
| Form | Panels (drawings) with captions | Table / chart with stages, actions, thoughts, emotions, pain points |
| Focus | What happens (the story) | What the user does, thinks, feels, and struggles with |
| Emotions / pain points | Shown implicitly | Explicit columns / emotion curve |
| Used when | Communicating and testing an idea / concept | Understanding the current experience and finding opportunities |
| Example (notes) | Student has difficulty -> opens app -> login -> weak subject identified -> material recommended -> studies -> quiz -> feedback | Login -> Search -> Recommendation -> Learning -> Quiz -> Feedback with thoughts, emotions, pain points |

#### 3.3.4 Related items that the PYQs attach to this topic

**User flow [PYQ Nov 2023, 10 M]:** a diagram of the path a user takes through a product to complete a task: entry point, screens/steps, decisions and outcomes. Drawn with flowchart symbols (oval start/end, rectangle step/screen, diamond decision, arrows). See Section 4, A3 for the full answer.

**User journey vs user flow [OWN]:** a *flow* shows **screens and decisions** (how the system lets the user reach the goal); a *journey map* shows **human experience** (thoughts, feelings, pain points), which can include offline steps.

**Wireframe vs storyboard [PYQ Jul 2025, 5 M]:** see Section 4, A5.

---

### 3.4 Design heuristics for software solutions

**Easy explanation:** A heuristic is a **rule of thumb**. In design there is rarely one mathematically correct answer, so we judge a design against well-known rules: "is it simple? is it consistent? does it tell the user what is happening? is it split into sensible modules?" Heuristics are the **criteria used to decide whether a proposed software solution is a good design**, and they are especially useful when moving from problem understanding -> ideation -> conceptual design -> detailed design.

**Short note (5 M):**
> *Design heuristics are practical rules of thumb that help a designer make good software-design decisions when there is no single correct solution. A heuristic is a general principle that guides design decisions, e.g. "Keep the user interface simple and consistent." Instead of asking only "Can we implement this feature?" the designer asks: Is it easy for the user? Is the solution understandable? Can it handle future changes? Is the system divided into meaningful components? Is unnecessary complexity avoided? Does the design satisfy the requirements?*

**Why we need design heuristics [NOTES table]:**

| Purpose | Explanation |
|---|---|
| Reduce complexity | Avoid unnecessarily complicated solutions |
| Improve usability | Make systems easier to learn and use |
| Improve maintainability | Make future modifications easier |
| Improve reliability | Reduce opportunities for errors |
| Support decision making | Compare alternative designs |
| Encourage reuse | Use existing components/patterns |
| Improve scalability | Prepare the system for growth |
| Improve consistency | Similar functions should behave similarly |

**Where they sit in the process [NOTES flow, slide 135]:** Problem -> Design Thinking -> Ideation -> Alternative solutions -> **Design heuristics (evaluate alternatives)** -> Conceptual design -> Architecture -> Detailed design -> Design patterns -> Prototype -> Test and iterate.

#### 3.4.1 Nielsen's 10 usability heuristics (core, highest PYQ frequency)

Mnemonic for the order: **V**isible **M**ice **U**se **C**heese, **E**ating **R**ice **F**or **A**fternoon **H**elp **H**ere. = Visibility, Match, User control, Consistency, Error prevention, Recognition, Flexibility, Aesthetic, Help recover, Help docs. [OWN mnemonic]

| # | Heuristic | Meaning (from slides) | Software example |
|---|---|---|---|
| 1 | **Visibility of system status** | Keep users informed about what is going on through appropriate feedback within a reasonable time; predictable interactions build trust. | Progress bar while uploading; "Order is being prepared"; mall-map "You are here" |
| 2 | **Match between system and the real world** | Speak the users' language (words, phrases, concepts familiar to them), follow real-world conventions, natural and logical order; do not assume your terms match the users'. | Calculator app that looks like a physical calculator; "Cart" and "Checkout" in shopping apps |
| 3 | **User control and freedom** | Users choose functions by mistake and need a clearly marked "emergency exit"; support undo and redo; clear, labelled, discoverable Cancel. | Undo/Redo in a word processor; Cancel on a file-extraction dialog |
| 4 | **Consistency and standards** | Users should not wonder whether different words, situations or actions mean the same thing; follow platform conventions. **Internal consistency** (within a product/suite, e.g. Google apps) and **external consistency** (industry/web conventions, e.g. cart icon and search bar placement on shopping sites). Reduces cognitive load, improves learnability. | Same toolbar icons across Word/Excel; cart icon top right on IKEA/Etsy |
| 5 | **Error prevention** | Minimise the chance of mistakes: eliminate error-prone conditions or check and ask for confirmation before commit; prevent high-cost errors first; use constraints, good defaults, undo, warnings. | "Are you sure you want to delete this file?"; password strength meter; disabled Submit until the form is valid |
| 6 | **Recognition rather than recall** | Minimise memory load by making elements, actions and options visible; do not make users remember information from one part to another; offer help in context. | Google autosuggest; "Sign up with Google/Facebook" buttons; "Recently played" lists |
| 7 | **Flexibility and efficiency of use** | Shortcuts (hidden from novices) speed up experts; provide accelerators (keyboard shortcuts, touch gestures), personalisation, customisation; flexible processes. | Ctrl+C/V; tool shortcuts in design apps; customisable dashboard |
| 8 | **Aesthetic and minimalist design** | Do not show irrelevant or rarely needed information; every extra unit competes with relevant units and lowers their visibility; focus on essentials and primary goals. | Google search home page; calculator with only essential keys |
| 9 | **Help users recognise, diagnose and recover from errors** | Error messages in **plain language** (no codes), precisely indicate the problem, and constructively suggest a solution; with visual treatment so users notice them. | "Did you mean joe@gmail.com?"; "Password must be 8+ characters, add a number" |
| 10 | **Help and documentation** | Best if no explanation needed, but provide documentation that is easy to search, focused on the user's task, concise, listing concrete steps. | Contextual tooltips, searchable FAQ, onboarding tour |

**Heuristic evaluation [PYQ Nov-Dec 2021 Q1A(8)]:** a usability inspection method in which a few evaluators examine a user interface and judge its compliance with recognised usability principles (heuristics such as Nielsen's 10), listing violations with severity, without needing end users. (Cheap and fast; done early on prototypes.)

#### 3.4.2 Software-design heuristics (system/architecture side) — summary table from the notes

| Heuristic | Simple meaning | Tiny example [OWN] |
|---|---|---|
| Simplicity | Keep the solution as simple as possible | One REST endpoint instead of three overlapping ones |
| Modularity | Divide the system into manageable components | Separate Auth, Payment, Notification modules |
| High cohesion | Keep related responsibilities together | A `PaymentService` handles only payment tasks |
| Low coupling | Minimise dependencies between components | Modules talk via interfaces, not each other's internals |
| Separation of concerns | Each component has a clear responsibility | UI, business logic and data access in separate layers |
| DRY | Avoid unnecessary duplication | One validation function used by all forms |
| Reusability | Reuse suitable components | Use an existing login library |
| Consistency | Similar things behave similarly | Same error format from every API |
| Visibility | Make important information easy to see | Dashboard shows system health |
| Feedback | Tell users what happened | "Payment successful" screen |
| Error prevention | Prevent mistakes where possible | Input validation, confirmation dialogs |
| Abstraction | Hide unnecessary implementation details | Caller uses `sendEmail()` without knowing the SMTP details |
| Scalability | Prepare for growth | Stateless services behind a load balancer |
| Security | Build security into the design | Role-based access control from day one |
| Failure handling | Expect and handle failures | Retry with back-off, fallback page |
| Design for change | Make future modification easier | Configurable rules instead of hard-coded values |
| Patterns | Reuse proven solutions | MVC, Observer, Factory |
| Trade-offs | Balance competing quality attributes | Faster response vs higher cost |

**Practical heuristic checklist [NOTES] (use as a case-study answer skeleton):**

| Area | Ask |
|---|---|
| User | Easy to understand? Solves the user's real problem? Important functions easy to find? |
| Functionality | Satisfies all requirements? Error cases considered? Feedback provided? |
| Architecture | Responsibilities separated? Coupling low? Cohesion high? Interfaces clearly defined? |
| Maintainability | Modular? Components modifiable independently? Duplication avoided? |
| Quality | Secure? Scalable? Reliable? Usable? Accessible? |
| Evolution | What if requirements change? New functionality easy to add? Components reusable? |

**Heuristic vs principle [OWN]:** a *principle* is a fundamental guideline; a *heuristic* is a practical rule of thumb that helps judge or choose, not guaranteed to be perfect. In the exam, treat "design principles" and "heuristics" as closely related and say Nielsen's heuristics are broad usability principles.

---

### 3.5 Evaluating idea feasibility and prioritization

**Easy explanation:** Many ideas now exist. Three questions decide which survive:
1. **Desirability** - do users **want** it?
2. **Feasibility** - can engineers **build and maintain** it (in time, within budget)?
3. **Viability** - should the **business** build it (does it pay back)?
Feasibility is the technical filter applied to human-centred ideas. Prioritization then turns the surviving ideas into an actionable roadmap.

```
        DESIRABILITY (users want)
               /\
              /  \
             / SWEET\
            /  SPOT  \
 FEASIBILITY ---------- VIABILITY
 (can build)            (business should build)
```
(The three-circle overlap diagram is [OWN] standard drawing; the three definitions are [NOTES].)

#### 3.5.1 Idea feasibility

**Definition (5 M):**
> *Feasibility evaluates whether a proposed software solution can be practically built, deployed in time and within the specified budget, within real-world technical, financial, operational and time constraints. It focuses on architectural viability, system constraints and technical-risk reduction before production code is written.*

**Types of feasibility (draw as a table, 10 M):**

| Type | What it checks | Key questions / sub-points |
|---|---|---|
| **Technical** | Can it be built with current technology, tools and engineering capability? | Architecture and infrastructure (event-driven microservices vs monolith fits stack?); data and integration (APIs, data pipelines, third-party services available, documented, reliable?); performance and scalability (response time, throughput/RPS, concurrency SLAs); team skills (Rust, distributed systems, ML pipelines, steep learning curve?) |
| **Operational** | Fit with daily workflow and maintenance capability | Maintainability and technical debt; observability and monitoring (logs, debugging in production); DevOps and deployment (CI/CD, rolling updates, disaster recovery) |
| **Economic and resource** (cost-benefit) | Does lifetime cost justify business value? | Cloud and compute costs (hosting, database, bandwidth, API usage at scale); development effort (person-months to build, test, release) |
| **Legal, security and regulatory** | Compliance with statutory rules and security standards | Data privacy (GDPR, CCPA, HIPAA; encryption at rest/in transit; data residency); security architecture (zero-trust, RBAC, secure credential storage) |

**The five feasibility concerns used while evaluating a concept [NOTES slides 143-147]:**
1. **Architectural and stack compatibility** - can it reuse existing microservices and databases or need a complete refactor? Does it add technical debt or lock us to unsupported third-party vendors?
2. **Data availability and integration** - are internal/external APIs available for real-time data? Is data cleansed, structured and privacy-compliant (GDPR)? Enough training data for AI/ML features?
3. **Performance and scalability constraints** - can the architecture meet PSLA targets: response time, uptime/availability, latency, error/failure rate, throughput, MTTR, scaling?
4. **Resource and team capability** - experience with the technology; steep learning curve threatening deadlines?
5. **Security, risk and regulatory compliance** - new attack vectors (sensitive data exposure, third-party script injection)? Standards: **PCI-DSS** (mandate for any organisation that stores, processes or transmits credit-card data), **SOC 2** (evaluates how well a service provider manages and protects customer data; critical for SaaS, cloud vendors, tech companies).

**Techniques to validate feasibility (lightweight, before full development) [NOTES]:**

| Technique | What it is |
|---|---|
| Technical spike | Short, focused research task or throw-away code to explore an unknown technology or evaluate API capabilities |
| Proof of concept (PoC) | Small bare-bones implementation proving a core technical concept is possible (e.g. sub-50 ms search indexing) |
| Architecture prototyping | Build a skeleton to test non-functional requirements: load balancing, DB read/write throughput, messaging queues |
| Risk matrix analysis | Identify high-risk design decisions (e.g. reliance on a single third-party vendor) and plan fallback architectures |

**Worked feasibility check (using the food-delivery ideas from the slides, extended) [OWN]:**

| Idea | Technical | Operational | Economic | Legal/security | Verdict |
|---|---|---|---|---|---|
| Live order tracking | High (GPS APIs exist) | Medium (needs monitoring) | Medium (map API cost) | Medium (location privacy) | Feasible |
| AI recommendations | Medium (needs order data) | Medium | Medium | Medium (personal data) | Feasible with data |
| Voice ordering | Medium (speech API) | Medium | Medium | Medium | Possible later |
| Drone delivery | Low (aviation tech) | Low | Low (very costly) | Low (aviation law) | Not feasible now |

#### 3.5.2 Idea prioritization

> *Prioritization translates wild user-centric concepts into actionable engineering roadmaps and balances human desirability with technical feasibility and business viability.*

**(1) Value vs Effort matrix (2 x 2) [NOTES]**

```
   VALUE
   high |  QUICK WINS            |  MAJOR PROJECTS
        |  high value, low effort|  high value, high effort
        |  -> do FIRST           |  -> plan strategically
        +------------------------+------------------------
   low  |  FILL-INS              |  THANKLESS TASKS
        |  low value, low effort |  low value, high effort
        |  -> do in downtime     |  -> drop / deprioritise
        +------------------------+------------------------
             low effort                 high effort   EFFORT
```

Worked placement [OWN, using the food app ideas]: One-click reorder = Quick win; Live tracking = Quick win or major project; AI recommendations = Major project; Voice ordering = Major project; A cosmetic theme colour option = Fill-in; Drone delivery = Thankless task.

**(2) MoSCoW method [NOTES]**

| Class | Meaning | Food app example [OWN] |
|---|---|---|
| **M**ust have | Non-negotiable core functionality for launch | Browse menu, place order, payment, login |
| **S**hould have | High value; workaround exists if delayed | Order tracking, order history |
| **C**ould have | Nice-to-have if time and budget permit | Voice search, meal subscriptions |
| **W**on't have (this time) | Excluded from the current release | Drone delivery, AR food preview |

**(3) KANO model [NOTES]** - measures how each feature affects customer satisfaction compared to the effort it needs. Five categories:

| Category | Behaviour | Example |
|---|---|---|
| Must-be (basic / threshold) | Taken for granted; presence does not raise satisfaction, absence causes severe dissatisfaction | Login screen; working brakes on a car |
| One-dimensional (performance) | Linear: better/faster = happier | Battery life; search speed; page load speed |
| Attractive (delighters / excitement) | Unexpected; absence does not hurt, presence delights and differentiates | Personalised automated workflow; free hotel room upgrade |
| Indifferent | Users do not care either way; no return on investment | Rarely used settings screen [OWN] |
| Reverse | Annoys users when present | Aggressive pop-up ads; forced multi-step checkout |

KANO curve to draw (satisfaction vs feature performance) [OWN drawing of the standard graph]:

```
Satisfaction
   ^            Attractive (delighters)  ___/
   |                                 ___/
   |          One-dimensional    ___/  (straight rising line)
   |                         ___/
 0 +-------------------------------------------------> Feature fulfilment
   |  ___ Must-be (basic)  - never goes above 0, only drops if absent
   v
Dissatisfaction
```

**(4) RICE scoring [NOTES]** - quantitative scoring to compare and rank features objectively.

```
                Reach  x  Impact  x  Confidence
RICE score  =  ----------------------------------
                            Effort
```

| Factor | Meaning | Scale |
|---|---|---|
| **R**each | How many target users are affected in a timeframe (e.g. users per quarter); raw number | e.g. 2,000 users/quarter |
| **I**mpact | How much it improves UX or the business goal | 3 = massive, 2 = high, 1 = medium, 0.5 = low, 0.25 = minimal |
| **C**onfidence | How sure the team is about R, I, E | 100% = high (quantitative data and research), 80% = medium (qualitative feedback or proxy data), 50% = low (educated guess/intuition) |
| **E**ffort | Total time from all team members (designers, developers, QA) to ship | person-months |

**Numerical 3 - RICE worked example [OWN numbers; formula is NOTES]** (college LMS features, quarter)

| Feature | Reach | Impact | Confidence | Effort (person-months) | RICE = R x I x C / E |
|---|---|---|---|---|---|
| Deadline reminders | 3000 | 2 | 100% (1.0) | 2 | 3000 x 2 x 1.0 / 2 = **3000** |
| AI study recommendations | 2000 | 3 | 80% (0.8) | 6 | 2000 x 3 x 0.8 / 6 = **800** |
| Dark mode | 1500 | 0.5 | 100% (1.0) | 1 | 1500 x 0.5 x 1.0 / 1 = **750** |
| Voice assistant | 500 | 1 | 50% (0.5) | 5 | 500 x 1 x 0.5 / 5 = **50** |

Ranking: Deadline reminders (3000) > AI recommendations (800) > Dark mode (750) > Voice assistant (50). Build deadline reminders first. Higher score = higher priority. Note how a low-confidence idea (voice assistant) is penalised.

**Approach comparison table [NOTES slide 160]:**

| Approach | Best used for | Primary strength | Potential pitfall |
|---|---|---|---|
| Value vs Effort | Early-stage design workshops | Fast visual consensus | Subjective estimations |
| MoSCoW | Fixed-scope release planning | Clear boundaries for MVPs | Everything becomes a "Must have" |
| KANO model | User experience (UX) refinement | Validates true user desire | High research and survey overhead |
| RICE scoring | Mature product roadmap triage | Data-backed objectivity | Complex math based on estimates |

**Closing the module (one paragraph to memorise):** *brainstorm / SCAMPER / mind-map to diverge -> morphological chart and analogies to build multiple design alternatives -> storyboard and journey-map to make them experiential -> heuristics to judge design quality -> feasibility and prioritization (value-effort, MoSCoW, KANO, RICE) to converge on what to prototype first.*

---

## 4. PYQ SOLUTIONS (Module-3-relevant only)

> **Scope decision (honest):** Only these PYQ items overlap Module 3. Others (empathy map, personas, user research, usability testing, AR/VR, 5S model, wicked problems, Gestalt, interaction styles, widgets, wireframing advantages, information architecture, etc.) belong to Modules 1, 2, 4 or 5 and are not solved here. Borderline items are listed at the end (section E) with a brief answer.
>
> **Tally of PYQs used:** A1 Dec 2022 (5 M) | A2 Nov 2023 (10 M) | A3 Nov 2023 (10 M) | A4 Nov 2023 (10 M) | A5 Jul 2025 (5 M) | A6 Nov-Dec 2021 (1 M) | B1 Dec 2022 (10 M) | B2 Jul 2025 (10 M) | B3 Nov-Dec 2021 (1 M) | C1 Dec 2022 (5 M).

### A. Storyboarding, user journey, user flow, UX stories

#### A1. "A storyboard is a great way to tell the stories." Justify. [PYQ Dec 2022, Q1(i), 5 M]

**Answer:**
A **storyboard** is a visual sequence of scenes/events that shows how a user interacts with a product or solves a problem. It is like a comic strip: each panel shows one moment, with a short caption.

**Why it is a great way to tell stories (justification):**
1. **Visual and easy to grasp** - a picture sequence communicates faster than a long document.
2. **Puts the user in context** - shows who the user is, what problem they face and how the product helps.
3. **Builds empathy** - shows feelings (frustration, relief) at each step.
4. **Aligns the team and stakeholders** - everyone sees the same story, including non-technical people.
5. **Exposes gaps early and cheaply** - missing steps or unnecessary steps show up before design or coding starts.
6. **Quick and low-fidelity** - stick figures and captions are enough; easy to change.
7. **Guides decisions** - helps choose features and feeds into wireframes/prototypes.

**Example - Smart Teaching-Learning System:**

```
[1 Student has   -> [2 Opens app] -> [3 Logs in] -> [4 App finds
   difficulty]                                         weak subject]
                                                            |
[8 App gives     <- [7 Takes quiz] <- [6 Studies  <- [5 App recommends
   feedback]                            material]       material]
```

**Conclusion:** A storyboard converts an abstract idea into a user-centred story, making it easier to communicate, test and refine the design before development.

#### A2. "Great questions lead to great design." Map the given statement to user research and journey with appropriate example. [PYQ Nov 2023, Q2A OR, 10 M]

**Answer (structure: meaning -> link to research -> link to journey -> example -> conclusion):**

**1. Meaning.** The quality of a design depends on the quality of the questions asked at the start. A vague question ("build a college app") yields a vague design; a sharp, user-centred question ("How might we help first-year students find their study material quickly?") yields a focused design. Great questions are open, user-centred, and framed as **How Might We (HMW)** statements.

**2. Mapping to user research.** Questions decide what we learn about the user:

| Question asked | Research method used | What we learn |
|---|---|---|
| Who are the users? What are their goals? | Interviews, surveys, personas | User needs and context |
| What do they do, say, feel? Why? | Observation, shadowing, empathy map | Behaviour, motivations |
| Where do they struggle? | Usability tests, diaries | Pain points |
| How many/how often? | Quantitative surveys, analytics | Evidence at scale |

(Asking "why?" repeatedly (5 whys) reveals root causes and latent needs.)

**3. Mapping to the user journey.** The same questions are asked at **every stage** of the journey map:
- What is the user **doing** at this stage? (action)
- What are they **thinking**? (thought)
- How do they **feel**? (emotion)
- What **blocks** them? (pain point)
- How **might we** improve it? (opportunity)

**4. Example - Smart Teaching-Learning Application**

| Journey stage | Great question asked | Research finding | Design decision |
|---|---|---|---|
| Login | How long does login take for a student who just wants to study? | Login may take time | Social/one-tap login |
| Search | Where do students look for notes? Why do they struggle? | Too many resources | Search filters and AI recommendations |
| Learning | When do students stop understanding? | Difficult topic | Short videos + examples |
| Quiz | How do students feel before a quiz? | Anxiety, hard questions | Practice mode with hints |
| Feedback | What do they do after seeing the score? | Limited explanation | Answer explanations, practice sets |

```
Great question -> User research -> Insight/pain point -> Journey map -> Ideation (HMW) -> Better design
```

**5. Conclusion.** Great questions guide user research, research feeds the journey map, the journey map exposes pain points, and these become HMW questions for ideation. So great questions lead to great design.

#### A3. What are User Flows in User Experience (UX) Design? How does it benefit the UX designer for depicting the user journey? [PYQ Nov 2023, Q3(ii), 10 M]

**Answer:**

**Definition.** A **user flow** is a diagram of the path a user follows through a product to complete a specific task, from the entry point to the final outcome, showing the screens, actions and decisions in between. (Example tasks: log in, place an order, reset password.)

**Elements / symbols (flowchart style):**

| Symbol | Meaning |
|---|---|
| Oval | Start / end (entry point, goal reached) |
| Rectangle | Screen or step |
| Diamond | Decision (yes/no, valid/invalid) |
| Arrow | Direction of flow |

**Diagram - Food ordering user flow:**

```
 (Start: open app)
        |
   [Login screen] --- no account? ---> [Sign up] --+
        |                                          |
     valid? <--------------------------------------+
     /     \
   no       yes
    |        |
 [Error]  [Home / restaurant list]
    |        |
    +--->  [Select items] -> [Cart] -> [Payment]
                                          |
                                    payment ok?
                                     /       \
                                   no         yes
                                   |           |
                             [Retry payment] [Order confirmed] -> (End)
```

**How it benefits the UX designer in depicting the user journey:**
1. Shows the **complete path** (steps and screens) clearly, so no step is forgotten.
2. Reveals **friction points, dead ends and unnecessary steps** that can be removed (SCAMPER: eliminate).
3. Shows **alternate paths and error paths** (wrong password, failed payment) so they are designed for.
4. Acts as a **communication tool** between designers, developers and stakeholders.
5. Helps plan **information architecture and wireframes** (each rectangle becomes a screen).
6. Supports **testing** - usability test tasks follow the flow.
7. Keeps design **goal-oriented** - focuses on the user's task, not on features.

**User flow vs journey map:** a flow shows screens and decisions; a journey map adds thoughts, emotions and pain points over the whole experience. Together they describe both what the user does and how it feels. (Combine with the journey table from 3.3.2 if the examiner expects a journey.)

#### A4. Explain with the help of an example how UX stories capture attention, provide clarity, and inspire UX designers to take decisions. [PYQ Nov 2023, Q3(iii), 10 M]

**Answer:**

**What is a UX story?** A short narrative about a **specific user** in a **specific situation** trying to reach a goal with the product, including their feelings and obstacles. It can be written (scenario / user story) or visual (storyboard).

**Example persona:** *Riya, a first-year student, has three assignments due and cannot find her study material.* (Smart Teaching-Learning App.)

**Story:** Riya is stressed (trigger) -> opens the app -> logs in -> app notices weak subject -> recommends notes -> she studies -> takes a quiz -> gets feedback and feels confident (resolution).

| What a story does | How, with the Riya example |
|---|---|
| **Captures attention** | A real, relatable character with a real problem and emotion (stress, deadline) makes people care, unlike a list of requirements |
| **Provides clarity** | A beginning-middle-end sequence shows exactly when and why the product is used and what outcome is expected; removes ambiguity |
| **Inspires designers to take decisions** | Pain points in the story (too many resources, difficult quiz) point directly at features: filters, recommendations, hints, explanation. The story is a test: "would this feature help Riya at this moment?" |

Additional benefits: builds empathy, aligns the team and stakeholders on one shared picture, helps prioritise features, and gives test scenarios.

**Diagram (storyboard of the story):**

```
[Riya stressed] -> [Opens app] -> [Weak subject found] -> [Material recommended] -> [Quiz + feedback] -> [Confident]
```

**Conclusion:** stories make design human; they attract attention with emotion, give clarity with sequence, and inspire decisions by exposing user needs.

#### A5. Illustrate the difference between wire-framing and storyboarding in UX design. [PYQ Jul 2025, Q5(vi), 5 M]

**Answer:**

| Aspect | Wireframing | Storyboarding |
|---|---|---|
| Meaning | Low-fidelity layout/skeleton of a screen/page showing placement of elements | Visual sequence of scenes showing how a user uses a product to solve a problem |
| Focus | **Structure and layout** of the interface (what is where) | **Story and context** of use (who, why, what happens) |
| Shows | Boxes for header, menu, buttons, text, images | Characters, situations, actions, emotions in panels |
| Scope | One screen / page at a time | A sequence over time, often beyond the screen (real world) |
| Stage | Later: after concept, when designing the interface | Early: ideation, to explain and evaluate the concept |
| Audience question | "How will the screen be arranged?" | "How will the user experience the solution?" |
| Output | Screen blueprint for prototype/UI design | Narrative for understanding and communication |

```
WIREFRAME (one screen)            STORYBOARD (sequence)
+---------------------+           [Student     [Opens   [Gets
|  [Logo]   [Menu]    |            struggles] -> app] -> recommendation]
|  +---------------+  |
|  |    Banner     |  |
|  +---------------+  |
|  [Button]  [Text]   |
+---------------------+
```

**Example:** For the Smart Teaching-Learning App, the storyboard shows a student struggling, opening the app and receiving a recommendation; the wireframe shows the layout of the recommendation screen (list of materials, search bar, quiz button). Both are low-fidelity and are used together: the storyboard decides *what experience* we want, the wireframe decides *how the screen will look*.

#### A6. Wireframing and storyboard are ______ & ______ tools used for designing interface. [PYQ Nov-Dec 2021, Q1(A)9, 1 M]
Options: (a) Dynamic & Static (b) Dynamic & Dynamic (c) Static & Dynamic (d) Static & Static.

**Answer: (d) Static & Static.** Both are static (non-interactive) low-fidelity representations: a wireframe is a static layout of a screen, a storyboard is a static sequence of drawn panels. Neither responds to user input, unlike an interactive prototype. (The official answer key is not in the files; this is my reasoning. Confirm with the key if available.)

### B. Design heuristics

#### B1. Illustrate on any five heuristic design principles with supporting examples. [PYQ Dec 2022, Q2B(ii), 10 M]

**Answer:**

**Introduction.** Heuristic design principles (Jakob Nielsen's 10 usability heuristics) are broad rules of thumb used to design and evaluate user interfaces. Five of them are illustrated below.

**1. Visibility of system status.** The system should always keep users informed about what is happening through appropriate feedback within a reasonable time.
*Example:* a progress bar while a file uploads or "Your order is being prepared" with live tracking in a food app. Users know the outcome of their action and what to do next, building trust.

**2. Match between the system and the real world.** Use words, phrases and concepts familiar to the user and follow real-world conventions, with information in a natural and logical order.
*Example:* a shopping app uses "Cart" and "Checkout"; a calculator app looks like a physical calculator; a delete action uses a "Trash can".

**3. User control and freedom.** Users make mistakes and need a clearly marked "emergency exit"; support undo and redo and a clear Cancel.
*Example:* Undo/Redo in a document editor; Cancel button on a file-extraction dialog; "Undo send" in email.

**4. Consistency and standards.** The same words, icons and actions should mean the same thing; follow platform conventions. *Internal consistency* within a product family (Gmail, Calendar, Drive look and behave alike); *external consistency* with industry conventions (cart icon at the top right, search bar at the top). Reduces cognitive load and improves learnability.

**5. Error prevention.** Design to stop errors before they occur, or ask for confirmation before committing.
*Example:* "Are you sure you want to delete this file?" dialog; password strength meter; disabling the Pay button until all fields are valid.

*(Other heuristics you may substitute: recognition rather than recall (Google autosuggest, recent items); flexibility and efficiency of use (keyboard shortcuts); aesthetic and minimalist design (Google search page); help users recognise, diagnose and recover from errors ("Did you mean joe@gmail.com?"); help and documentation (searchable FAQ, tooltips).)*

```
Nielsen heuristics wheel (draw if time):
 Visibility | Real-world match | User control | Consistency | Error prevention
 Recognition | Flexibility | Minimalist | Error recovery | Help & documentation
```

**Conclusion.** Applying heuristics reduces usability problems, lowers cognitive load, and results in interfaces that are easy to learn and use.

#### B2. Designing a Smart Home App: List and justify applicable principles of the heuristic analysis for the Smart Home App case study. [PYQ Jul-Nov 2025, Q2(i), 10 M]
(Case: a start-up builds a mobile app to control smart-home devices: lights, thermostat and security; it must be intuitive and meet the needs of diverse users.)

**Answer (list the heuristic, then justify with a Smart Home application):**

| # | Nielsen heuristic | Application in the Smart Home App | Justification |
|---|---|---|---|
| 1 | **Visibility of system status** | Show each device's state (light On/Off, thermostat current vs target temperature, door locked/unlocked, camera online/offline, "Connecting..." indicator, last updated time) | Users cannot see the physical result at once, so confirming the state prevents repeated taps and builds trust; critical for security |
| 2 | **Match between system and real world** | Name devices by room and function ("Living room light", "Front door"); sun/moon icons and sliders for brightness; modes "Home / Away / Night" instead of technical codes (e.g. "Zigbee node 4") | Diverse users, including non-technical and elderly, understand everyday language |
| 3 | **User control and freedom** | Undo accidental changes, easy cancel of schedules and scenes, manual override of automation, one tap "turn everything off" | Mistaken taps are common; a wrong lock/unlock or thermostat change must be reversible |
| 4 | **Consistency and standards** | Same toggle/slider style for all devices, same colour for On/Off everywhere, standard icons for lock, bulb, thermostat; follow platform conventions (Android/iOS) | Learn once, use for every device; lowers cognitive load |
| 5 | **Error prevention** | Confirmation before disarming security or unlocking doors; thermostat limits (e.g. 16-30 degrees C); warning on conflicting schedules; PIN/biometrics for sensitive actions | Mistakes with security and energy are costly; prevent high-cost errors first |
| 6 | **Recognition rather than recall** | Dashboard of device cards by room, Favourites and Recent scenes, visible labels instead of hidden gestures | Users should not memorise commands or device IDs |
| 7 | **Flexibility and efficiency of use** | Scenes ("Good Night" switches off lights, lowers thermostat, arms security), widgets, voice assistant and shortcuts for experts; simple default mode for novices | Serves both novice and expert users; saves time on frequent actions |
| 8 | **Aesthetic and minimalist design** | Clean home screen with only essential controls (rooms, quick toggles); advanced settings under a menu | Reduces clutter and distraction, especially for older users |
| 9 | **Help users recognise, diagnose and recover from errors** | Plain messages: "Thermostat is offline. Check Wi-Fi/power and tap Retry" with a retry button, not "Error 502" | Network/device failures are common in IoT; users must know what to do |
| 10 | **Help and documentation** | Onboarding for pairing devices, contextual tips, searchable FAQ, video guide, support chat | Initial set-up of devices is the hardest step for new users |

**Diverse users note (ties to the case):** use large touch targets, readable fonts and contrast, voice control and multilingual support (accessibility); a simple view for elderly users and an advanced view for tech-savvy users.

**Conclusion.** Evaluating the Smart Home App against these heuristics finds usability problems early (heuristic evaluation), ensures the app is intuitive, safe and suitable for diverse users, and guides redesign before development. (In the exam, if time is short, write 6-7 rows in a table and add one line of justification each; the examiner expects "list and justify".)

#### B3. A heuristic evaluation is a method of ______. [PYQ Nov-Dec 2021, Q1(A)8, 1 M]
**Answer:** Evaluating/inspecting a user interface for **usability problems** by having a small group of evaluators examine it against recognised usability principles (heuristics, e.g. Nielsen's 10).

### C. Link to ideation: HMW and framing

#### C1. "Great questions lead to great design." Explain. [PYQ Dec 2022, Q1(iii), 5 M]

**Answer:**
The statement means that the **quality of the questions asked at the start decides the quality of the final design**.
1. **Questions focus the problem.** A broad question ("improve the app") gives scattered solutions; a precise question ("How might we help students manage academic deadlines?") focuses ideation.
2. **Questions uncover real user needs.** Asking users and observing with "Why?" and "What if?" reveals latent needs and root causes, not just symptoms (user research, empathy).
3. **Questions open possibilities.** "How Might We" questions are optimistic, open-ended and invite many ideas (brainstorming, SCAMPER).
4. **Questions challenge assumptions.** "What if we remove this step?" leads to simplification (SCAMPER eliminate / reverse).
5. **Questions drive evaluation.** "Is it feasible? Is it valuable?" guide selection and prioritization.

**Example:** Poor: "Make the library app better." Great: "How might we help a student find and reserve a book in under one minute?" -> ideas: search by voice, QR scan, availability alerts, one-tap reserve.

```
Great question (HMW) -> Research -> Ideas -> Prototype -> Test -> Great design
```

### D. Expected questions NOT yet asked (marked [OWN]; solved so that you have model answers)

#### D1. [OWN] Apply SCAMPER to an "Online Food Ordering" application and give a new version (slides' activity: changes in functionality, appearance, performance). 10 M

| SCAMPER step | Version 1 (existing app) | Version 2 (suggested) | Type of change |
|---|---|---|---|
| **Substitute** | Manual/phone customer support | AI chatbot answering queries instantly, 24/7 | Functionality |
| **Combine** | Only food delivery | Food + groceries + pharmacy in one app | Functionality |
| **Adapt** | Static "order placed" message | Ride-sharing style live GPS tracking with estimated arrival time | Functionality / performance |
| **Modify** (magnify/minify) | Generic menus, small images | Larger food images, voice ordering, personalised recommendations from previous orders and diet | Appearance / functionality |
| **Put to another use** | Individual orders only | Bulk lunch orders for companies, catering for events | Functionality |
| **Eliminate** | Long registration, many checkout steps | Login via Google/Apple/phone OTP; one-tap reorder; fewer checkout screens | Performance / appearance |
| **Reverse / Rearrange** | Search restaurant -> select food -> pay | AI suggests dishes first by preference and budget, then shows restaurants; or choose delivery time first | Functionality |

**Evaluate and select:** AI recommendations (feasible: high, value: high), live tracking (high, high), voice search (medium, high), one-click reorder (high, high), drone delivery (low, high -> rejected). Selected: AI recommendations, live tracking, voice search, one-click reorder. **Benefits:** creative thinking, better UX, higher satisfaction, competitive advantage.

#### D2. [OWN] Differentiate brainstorming and mind mapping. 5 M
Use the table in 3.1.6. Add example: brainstorming = "generate 20 app ideas"; mind mapping = "organise those ideas into Attendance / Exams / Fees / Library / Placement". Closing line: use brainstorming first, then a mind map to structure.

#### D3. [OWN] Explain the 6-3-5 method. If 5 members take part with the m-3-(m-1) rule, how many ideas and how much time? 5 M
Definition and steps from 3.2.4. Calculation: m = 5, rotations = m - 1 = 4; rounds = 5; ideas = 5 x 3 x 5 = **75**; time at 5 minutes per round = 5 x 5 = **25 minutes**. (Standard 6-3-5: 6 x 3 x 6 = 108 ideas in 30 minutes.)

#### D4. [OWN] What is a morphological chart? Construct one for a "Student Attendance System" and state how many designs are possible. 10 M

| Function | Means 1 | Means 2 | Means 3 | Means 4 |
|---|---|---|---|---|
| Identify student | Biometric | QR code | Face recognition | Mobile NFC |
| Capture attendance | Teacher app | Classroom kiosk | Student mobile app | - |
| Store data | Cloud database | College server | Hybrid | - |
| Notify | SMS | Push notification | Email | - |
| Report | Web dashboard | Mobile report | PDF export | - |

Number of designs = 4 x 3 x 3 x 3 x 3 = **324**.
Candidate designs: **A** = QR code + student mobile app + cloud + push notification + web dashboard (low cost, easy); **B** = Face recognition + classroom kiosk + college server + SMS + web dashboard (higher cost, strong anti-proxy).
Infeasible: Biometric + student mobile app (a fingerprint cannot be scanned reliably through a student's own phone for another student; proxy risk) - prune.
Choose by an evaluation matrix (cost, feasibility, user value, scalability) and prototype the best one first. (SCAMPER's "substitute" examples biometric -> QR -> face -> NFC come from the slides; the rest is my construction.)

#### D5. [OWN] Explain direct, symbolic and fantasy analogies with software examples. 5 M
Use 3.2.3. Direct: shopping cart; Symbolic: folders/files for paper documents, trash can for deletion; Fantasy: voice assistant as a companion / "talk to the ERP like ChatGPT". Add: analogies help generate ideas without a blank page, belong to divergent thinking.

#### D6. [OWN] Explain how to expand and contract a design space. 5 M
Use the table in 3.2.5.

#### D7. [OWN] Differentiate technical, operational, economic and legal feasibility with examples. 10 M
Use the table in 3.5.1; give one example per type: technical (do we have skills for ML?), operational (can we monitor and deploy with CI/CD?), economic (cloud cost per user), legal (GDPR consent for location data). Close with the validation techniques (spike, PoC, architecture prototype, risk matrix).

#### D8. [OWN] Compare Value-Effort, MoSCoW, KANO and RICE. Prioritise the features of a campus app using RICE. 10 M
Use the comparison table and the RICE worked example in 3.5.2. State formula, factor meanings, ranking and the decision.

#### D9. [OWN] Explain Six Thinking Hats with a software example. 5 M
Use the table in 3.1.5 (Smart Food Delivery App example from slides).

#### D10. [OWN] Explain journey mapping for an online shopping app (user actions, thoughts, emotions, pain points). 10 M

| Stage | Action | Thought | Emotion | Pain point | Opportunity |
|---|---|---|---|---|---|
| Discover | Searches for a product | "Which one is good?" | Curious | Too many similar results | Filters, comparison view |
| Choose | Reads reviews | "Can I trust this?" | Doubtful | Fake/unclear reviews | Verified-purchase badges |
| Add to cart | Adds item | "I will buy it now." | Positive | - | - |
| Checkout | Enters address and payment | "Why so many steps?" | Frustrated | Long forms | One-click checkout, saved addresses |
| Delivery | Tracks order | "When will it arrive?" | Anxious | No live update | Live tracking and ETA |
| After-sale | Returns/reviews | "Hope returns are easy." | Uncertain | Complicated returns | Easy return and refund status |

Add the emotion curve and state that the low points (checkout, delivery) are targeted with SCAMPER/ HMW ideation.

### E. Borderline PYQs (partial overlap; handled briefly)

| PYQ | Module | Brief handling |
|---|---|---|
| Jul 2024 Q2A OR (10 M): six stages of the design process for "Designing a remote control for air-conditioner" | Module 1 mainly; **Ideate stage is Module 3** | Write all six stages (Module 1 answer) and in the Ideate stage use: HMW "How might we let users set comfortable temperature with the fewest steps?", brainstorming + SCAMPER ideas (voice control, auto mode, scheduling, bigger buttons, eliminate rarely used buttons), a morphological chart (display type, input method, connectivity) and choose with a value-effort matrix. |
| Jul 2024 Q1(i) and Nov-Dec 2021 Q1(B)1: "Explain design principles in brief" | Mostly visual/UX design principles (Module 2/4); heuristics link | If asked generically, answer with Nielsen heuristics (3.4.1) plus visual principles (contrast, alignment, hierarchy, consistency); this is Module 3 only if the paper says "heuristics". |
| Jul-Nov 2025 Q3(i): "Elaborate activities carried out during design process for Uber's ride selection panel" | Module 1/4 mainly | Activities: empathise (riders), define (HMW), **ideate** (brainstorm options for pricing display, ETA, vehicle categories; SCAMPER), prototype, test. Use Module 3 for the ideation activities. |
| Dec 2022 Q1(iv): "How flowcharts help in UX design" | Module 4 (flow), related to user flows | Reuse A3 (user flow) points. |
| Nov 2023 Q3(i) / Q2B(ii) persona and empathy map for Alex | Module 2 | Excluded. The "great questions" and journey ideas are used in A2. |

---

## 5. LAST-MINUTE REVISION CHEAT-SHEET

**Ideation:** generate MANY solutions after Empathize + Define; bridge user needs -> software concepts; diverge then converge.
**Brainstorming rules (5):** defer judgment, quantity, wild ideas, build on others, clear HMW.
**Process:** Problem -> HMW -> Rules -> Generate -> Record -> Group -> Evaluate -> Select.
**SCAMPER:** Substitute, Combine, Adapt, Modify (Magnify/Minify), Put to another use, Eliminate, Reverse (Rearrange). Food-delivery examples: chatbot, food+grocery+pharmacy, live GPS, voice ordering and larger images, catering/bulk orders, one-tap login and reorder, dishes-first.
**Crazy 8s:** 8 sketches, 8 minutes, A4 folded 2 x 4, speed over perfection.
**Six Hats:** White facts, Red feelings, Black risks, Yellow benefits, Green creativity, Blue process.
**Mind map vs brainstorm:** map = organise/relationships/hierarchy; brainstorm = generate/quantity. DT mind mapping = yard-sale clustering -> insights -> design criteria.
**Design alternative / design space:** same components arranged differently; all possible solutions; large vs small space.
**Morphological chart:** functions (rows) x means (columns); one per row; count = product (juice container 4 x 5 x 6 x 2 x 3 = 720; heatwave 4^12 = 16,777,216); prune infeasible (OAuth + JWT + modal + email reset = feasible; biometric + localStorage + security questions = not).
**Analogies:** direct, symbolic, fantasy; metaphors (desktop, cart, trash can, Material Design); similar / contrasting / contiguous solutions; divergent = outside the box, convergent = inside the game, hybrid = both.
**Team games:** 6-3-5 (6 people, 3 ideas, 5 rotations, 108 ideas in 30 min; m-3-(m-1)); C-Sketch (sketch, pencil only); Gallery (post, critique, revise until saturation).
**Expand:** prior art, open-source, benchmarking, reverse engineering. **Contract:** constraints, freeze scope, prioritise by impact, get-real check.
**Storyboard:** visual sequence of scenes of how a user interacts with a product (8-panel Smart Teaching-Learning). **Journey map:** complete experience: Stage / Action / Thought / Emotion / Pain point (+ opportunity). **User flow:** screens + decisions diagram. **Wireframe:** layout of one screen; **storyboard:** story over time; both static low-fi.
**Heuristics:** rules of thumb to judge designs. Nielsen 10: Visibility of status, Match real world, User control and freedom, Consistency and standards (internal/external), Error prevention, Recognition not recall, Flexibility and efficiency, Aesthetic and minimalist, Help recognise/diagnose/recover from errors, Help and documentation. Software heuristics: simplicity, modularity, high cohesion, low coupling, separation of concerns, DRY, reuse, abstraction, scalability, security, failure handling, design for change, patterns, trade-offs.
**Feasibility:** desirability (users want) + feasibility (can build) + viability (business should). Types: technical, operational, economic, legal/security/regulatory. Validate with spike, PoC, architecture prototype, risk matrix. Standards: GDPR, CCPA, HIPAA, PCI-DSS, SOC 2.
**Prioritization:** Value-Effort (quick wins, major projects, fill-ins, thankless tasks); MoSCoW (Must, Should, Could, Won't); KANO (must-be, one-dimensional, attractive, indifferent, reverse); RICE = R x I x C / E (impact 3/2/1/0.5/0.25; confidence 100/80/50%; effort in person-months).
**Highest PYQ-frequency items to master first:** (1) Nielsen heuristics with examples and case-study application (Dec 2022, Jul 2025, Nov-Dec 2021), (2) storyboard and storyboard vs wireframe (Dec 2022, Jul 2025, Nov-Dec 2021), (3) journey map / user flow / UX story (Nov 2023), (4) "great questions lead to great design" / HMW (Dec 2022, Nov 2023).
