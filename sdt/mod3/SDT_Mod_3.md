# SDT_Mod_3 — Ideation in Software Design (Software Design Thinking, 216U01E701)

> **Sources used:** `SDT Module 3 _ Ideation … final_V2` (160 slides, including image-only slides 59–129 that I read visually), `SDT Module 3 … V1 (1)` (57 slides), `Module 3.2_Morphological Chart` (heatwave case), `Story-boarding-vs-user-journey-mapping-notes.docx`, and every PYQ scan in `../question_papers_all_time/` (10 screenshots plus the Jul–Nov 2025 PDF).
> **Syllabus (9 hrs, CO2/CO3/CO4):** 3.1 Creativity techniques: brainstorming, SCAMPER, mind mapping · 3.2 Generating multiple design alternatives · 3.3 Storyboarding and user journey mapping.
> **PYQ labels:** **[25]** Jul–Nov 2025 · **[24]** Jul–Nov 2024 · **[23]** Nov 2023 · **[22]** Dec 2022 · **[21]** Nov–Dec 2021 (50-mark paper). The May 2023 *Software Architecture & Design Thinking* paper is a different course and is excluded.
>
> **Read this first (honest PYQ picture):**
> - Only **3.3 (storyboarding / journey mapping)** has direct PYQs. There are 3 direct ones and 3 adjacent ones (user flows, journey, UX stories).
> - **3.1 and 3.2 have never been asked in these papers.** The old papers belong to the *User Experience Design* course. Brainstorming, SCAMPER, mind maps and morphological charts are new to this *SDT* course. Expect the first SDT paper to lean on them, since the slides contain many worked examples.
> - So Part 4 solves the real PYQs. Part 5 adds **expected questions** for 3.1 and 3.2, clearly marked as *expected, not PYQ*.
> - No numericals exist. The "numerical-like" items are counting design combinations, the 6-3-5 idea count, and the scoring matrix. These are covered in Part 3.
> - The slides also contain heuristics, feasibility and prioritization. Those are **not in the syllabus you pasted**, so they are a short appendix (Part 6).

---

## 1. TOPIC MAP

```
MODULE 3 : IDEATION IN SOFTWARE DESIGN (9 hrs)
│
├── 0. Ideation basics (context)
│   ├── Definition: generating many possible solutions before choosing the best
│   ├── Bridge: user needs (stories, personas, pain points) → software concepts
│   ├── Place in DT: after Empathise + Define, before Prototype
│   ├── Objectives / why ideation / process (understand → generate → evaluate → select → refine)
│   └── Characteristics of good design: user-centric, feasible, innovative, valuable, scalable
│
├── 3.1 Creativity techniques
│   ├── Brainstorming
│   │   ├── Objective: quantity first, quality later
│   │   ├── 5 principles: defer judgment · quantity · wild ideas · build on others · focused HMW
│   │   ├── Process: problem → HMW → rules → generate → record → group → evaluate → select
│   │   └── Example: hospital appointment system
│   ├── Brainwriting (6-3-5)   [also appears in 3.2 as a team-ideation game]
│   ├── SCAMPER
│   │   ├── S Substitute · C Combine · A Adapt · M Modify/Magnify/Minify
│   │   ├── P Put to another use · E Eliminate · R Reverse/Rearrange
│   │   ├── Examples: food delivery app, WhatsApp for college, attendance, campus visitor app
│   │   └── Benefits
│   ├── Mind mapping
│   │   ├── Central topic → branches → sub-branches
│   │   ├── "Yard sale" 7-step method (insights → design criteria)
│   │   └── Mind mapping vs brainstorming
│   └── Other slide techniques: Crazy 8's · Six Thinking Hats
│
├── 3.2 Generating multiple design alternatives
│   ├── Basics: alternative · design alternatives · design space (large vs small)
│   ├── Morphological chart
│   │   ├── Function × means matrix; assemble one means per row
│   │   ├── Counting designs (product of means)
│   │   ├── Feasible vs infeasible combinations (pruning)
│   │   └── Examples: juice container, login feature, user authentication, heatwave system
│   ├── Analogical thinking: metaphors, direct / symbolic / fantasy analogy,
│   │   metaphorical solutions (similar / contrasting / contiguous), desktop metaphor
│   ├── Divergent vs convergent vs hybrid thinking
│   ├── Team ideation games: 6-3-5 · C-Sketch · Gallery method
│   ├── Design generation (goal-directed creative activity)
│   ├── Navigating the design space
│   │   ├── Expand: literature/patent search, benchmarking, reverse engineering, open-source
│   │   └── Contract: apply constraints, freeze scope, prioritize, "Get real!"
│   ├── Final word: blend morph charts + games + research + experience
│   └── Evaluation matrix: alternatives → scoring → prototype first
│
├── 3.3 Storyboarding and user journey mapping
│   ├── Storyboarding
│   │   ├── Definition, elements (scenes, captions, character, context, emotion, outcome)
│   │   ├── Steps to create, benefits, example (smart learning app)
│   │   └── Storyboard vs wireframe
│   ├── User journey mapping
│   │   ├── Definition; stages, actions, thoughts, emotions, pain points, opportunities
│   │   ├── Steps to create, benefits, example (learning app table)
│   │   └── User flow (related)
│   └── Storyboard vs user journey map (comparison)
│
└── Appendix (slides only, not in the pasted syllabus)
    ├── Design heuristics (Nielsen's 10, design principles checklist)
    └── Feasibility (technical / operational / economic / legal) and
        prioritization (Value-Effort, MoSCoW, KANO, RICE)
```

---

## 2. TOPIC-WISE QUESTION TYPES

**Legend:** ★ = appeared in a PYQ (year in brackets). ◐ = adjacent PYQ (user flows, journey, UX stories). ✔ = syllabus-valid and likely, never asked. — = not applicable.
There is no derivation in this module. "Numerical" means counting or scoring problems.

| Topic | Definition / short note | Explain with example | Compare / differentiate | Case-based application | Diagram / chart | Numerical-like | Advantages / limitations |
|---|---|---|---|---|---|---|---|
| Ideation basics | ✔ | ✔ | ✔ (divergent vs convergent) | — | ✔ (process flow) | — | ✔ |
| Brainstorming | ✔ | ✔ | ✔ (vs mind map) | ✔ (HMW case) | ✔ (process flow) | — | ✔ |
| Brainwriting 6-3-5 | ✔ | ✔ | ✔ (vs brainstorming) | ✔ | ✔ | ✔ (108 ideas) | ✔ |
| SCAMPER | ✔ | ✔ | — | ✔ (improve app X with all 7 letters) | ✔ (table) | — | ✔ |
| Mind mapping | ✔ | ✔ | ✔ (vs brainstorming) | ✔ (draw a mind map) | ✔ | — | ✔ |
| Crazy 8's / Six Hats | ✔ | ✔ | — | ✔ | ✔ | — | ✔ |
| Design alternatives / design space | ✔ | ✔ | ✔ (large vs small space) | — | — | — | — |
| Morphological chart | ✔ | ✔ | — | ✔ (build a chart for a system) | ✔ | ✔ (count designs, matrix scoring) | ✔ (feasible vs infeasible) |
| Analogy / metaphor | ✔ | ✔ | ✔ (3 analogy types) | ✔ | — | — | — |
| Expand / contract design space | ✔ | ✔ | ✔ | — | — | — | — |
| Storyboarding | ★ [22] ★ [25] ★ [21] | ✔ | ★ [25] (vs wireframe) ★ [21] | ✔ (draw for scenario) | ★ [22] | — | ✔ |
| User journey mapping | ✔ | ◐ [23] | ✔ (vs storyboard) | ◐ [23] | ✔ (table) | — | ✔ |
| User flows | ✔ | ◐ [23] | ✔ (vs journey map) | ✔ | ✔ | — | ✔ |
| UX stories / storytelling | ✔ | ◐ [23] | — | ◐ [23] | — | — | ✔ |

---

## 3. TOPIC-BY-TOPIC BREAKDOWN

### 3.0 Ideation (opening context, 2–3 mark note)

**Definition.** Ideation is the process of generating, exploring and developing many possible solutions to a clearly identified user problem. In software design it happens *after* we have understood the user (Empathise) and framed the problem (Define).

**Key line to write:** "Ideation = generating many possible software solutions *before* selecting the best one. The goal is to explore a wide range, not to find the perfect idea immediately."

**Why it matters (4 points):**
- It bridges user needs (user stories, personas, pain points) and concrete software concepts (architecture, UI/UX flows, feature sets).
- It converts abstract user problems into technically sound concepts *before* costly development starts.
- It encourages creativity and innovation.
- It improves software quality and solves real user problems.

**Ideation process:** Understand problem → Generate ideas → Evaluate ideas → Select best ideas → Refine ideas.

**Good design is:** user-centric, feasible, innovative, valuable, scalable.

**Divergent vs convergent** (this is where ideation lives):

| Divergent | Convergent |
|---|---|
| Expands the design space | Narrows the design space |
| Many ideas, no judging | Weigh ideas against constraints and goals |
| "Think outside the box" | "Stay within the game" |
| Brainstorming, SCAMPER, 6-3-5 | Feasibility check, pruning, evaluation matrix |

Ideation uses **hybrid thinking**: diverge first, then converge.

---

### 3.1 Creativity techniques

#### A. Brainstorming

**Short note (write this in the exam).**
Brainstorming is a group creativity technique in which participants generate a *large number of ideas* for a problem *without judging or criticizing* them during the initial generation phase. Its objective is **"quantity first, quality later."**

**5 key principles (with the slide examples):**
1. **Defer judgment.** Do not say "that won't work." Record the idea and evaluate it later.
2. **Encourage quantity.** Aim for many ideas, not one perfect one.
3. **Encourage wild ideas.** Unusual ideas can lead to practical innovation. Example: "What if students could talk to the college ERP like ChatGPT?"
4. **Build on others' ideas.** Student A: "Send attendance notifications." Student B: "Add a prediction that tells students if attendance may fall below 75%."
5. **Keep the problem clearly defined.** Focus on one *How Might We* question. Example: "How might we help students manage their academic deadlines?"

**Process (draw this flow):**

```
Identify Problem → Define HMW Question → Set Rules → Generate Ideas
      → Record Ideas → Group Similar Ideas → Evaluate → Select Best Ideas
```

**Worked example (from slides): Hospital Appointment System**
- *Problem:* patients spend too much time waiting.
- *HMW:* How might we reduce patient waiting time?
- *Ideas:* online appointment booking, digital token, live queue tracking, doctor availability indicator, SMS notification, estimated waiting time, video consultation, AI symptom pre-screening, automatic reminders, self-service kiosk.
- *Group:* booking (online booking, reminders, kiosk) · queue (token, live tracking, waiting time) · communication (SMS) · remote care (video, AI pre-screening).
- *Select* using feasibility and user value, for example online booking + digital token + live queue tracking.

**Practice activities in slides:** "How can we improve the college library experience?" and "How can I improve the LMS experience?" For these, give 8–10 ideas, group them and pick 3.

**Advantages:** many ideas fast, team participation, builds on diversity of thought, no cost.
**Limitations:** dominant voices can hijack the session, groupthink, ideas can be unrealistic, needs a facilitator.

#### B. Brainwriting — the 6-3-5 method

The slides note that **6-3-5 prevents dominant voices from hijacking brainstorming.**

- **6** participants sit around a table, **3** ideas each (written as key words or phrases), in **5**-minute rounds.
- Sheets are passed to the right. **No talking or cross-talk**, only written annotation. The next person expands on what is on the sheet.
- After a full circuit (6 rounds: the first round writes, then 5 rotations), the team lists, discusses, evaluates and records all ideas on a common medium (projector or board).
- General form: **m members use (m − 1) rotations: an m–3–(m − 1) method.** The natural upper limit is m = 6; prefer fewer.

**Counting problem (likely numerical-style question):**
Maximum ideas = 6 persons × 3 ideas × 6 rounds = **108 ideas in 30 minutes** (6 rounds × 5 min). That matches the slide's "108 ideas in 30 minutes".
For m = 4: rotations = 3, rounds = 4, ideas = 4 × 3 × 4 = 48, time = 4 × 5 = 20 min.

#### C. SCAMPER — the high-yield topic

**Short note.** SCAMPER is a *structured* creativity technique used to *modify an existing* product, service, process or idea to generate new alternatives. Instead of asking "What new software should we create?", we ask "**How can we change the existing software?**"

| Letter | Meaning | Question | Software example |
|---|---|---|---|
| **S** | Substitute | What can we replace? (technology, interface, process, input, output, interaction) | Biometric attendance → QR code → face recognition → mobile NFC. Phone support → AI chatbot. |
| **C** | Combine | What can we combine? | Timetable + attendance + assignments + notifications = *Student Academic Assistant*. Maps + food delivery + reviews = location-based restaurant recommendations. Fitness tracker + diet planner + doctor consultation = one health platform. |
| **A** | Adapt | What idea from another context can we adapt? | Uber's live tracking → school bus, ambulance or college shuttle tracking. Swipe left/right → job applications. |
| **M** | Modify / Magnify / Minify | What can we change, enlarge, reduce or simplify? | ERP with 20 menu options → My Attendance, My Timetable, My Assignments, My Fees, My Exams. E-commerce search: "products under ₹2,000 suitable for a college student". |
| **P** | Put to another use | Can the technology serve another purpose? | QR payments → attendance, library tracking, event registration, visitor management. GPS from food delivery → college bus tracking. |
| **E** | Eliminate | What can we remove (features, screens, steps, forms, approvals)? | Cart → Address → Delivery option → Coupon → Payment → Confirmation becomes Cart → **One-click checkout** → Payment. |
| **R** | Reverse / Rearrange | What if we flip the order or roles? | Food ordering: search restaurant → pick food → order becomes AI learns preference → suggests food → customer selects. |

**Full worked case — improving a food delivery app (slide table, reproduce this in the exam):**

| SCAMPER | Existing app: search restaurant → select food → pay → restaurant prepares → partner delivers | Improved version |
|---|---|---|
| Substitute | Manual customer support | AI chatbot answers queries 24/7 |
| Combine | Food only | Food + groceries + pharmacy in one app |
| Adapt | No tracking detail | Ride-sharing-style live GPS tracking with ETA |
| Modify | Generic listing | AI meal recommendations from past orders and diet preferences; voice ordering, larger images |
| Put to another use | Individual orders | Companies place bulk lunch orders; catering and event orders |
| Eliminate | Lengthy registration | Login via Google, Apple or phone OTP; one-tap reorder |
| Reverse | Restaurant first | Recommend dishes first (by preference and budget), then show restaurants offering them; schedule delivery before choosing the restaurant |

**After SCAMPER: evaluate and select (slide).**
Ideas: AI recommendations, voice search, scheduled delivery, one-click reorder, live GPS tracking, smart offers.

| Idea | Feasibility | User value |
|---|---|---|
| AI recommendations | High | High |
| Voice ordering | Medium | High |
| Live tracking | High | High |
| Drone delivery | Low | High |

Selected: AI recommendations, live tracking, voice search, one-click reorder. Drone delivery is dropped because of low feasibility.

**Worked case 2 — WhatsApp for college students (slide):**
Substitute text announcements with short voice/video ones · Combine WhatsApp with the college timetable · Adapt disappearing messages for temporary assignment reminders · Modify with an academic dashboard inside the app · Put to another use: groups for automated attendance notifications · Eliminate repetitive messages with automated FAQs · Reverse: instead of students asking faculty, an AI bot proactively pushes updates.

**Case template — Campus Visitor Application (slides leave Version 1 / Version 2 blank).** Fill it like this in the exam:

| Step | Goal | Version 1 (existing) | Version 2 (SCAMPER) |
|---|---|---|---|
| Swap | replace with better, cheaper, faster | Paper register at gate | QR pre-registration and e-pass |
| Combine | join unrelated features | Separate gate entry and host notification | Visitor entry + host notification + campus map in one app |
| Adapt | borrow from another industry | Guard phones the host | Airport-style check-in kiosk; Uber-style live location to guide visitor |
| Modify | tweak size or frequency | Single-day pass | Multi-day and group passes, simplified 3-field form |
| Put to another use | secondary utility of data | Logs unused | Visitor footfall data for event planning and security audits |
| Eliminate | strip friction | Manual ID photocopy, calls | Auto ID scan, no calls, instant approval |
| Reverse | flip the sequence | Visitor arrives, then host is contacted | Host invites visitor in advance and the pass is sent *before* arrival |

For "Online Food Ordering — provide a new version" (slide 29–30), use the food-delivery table above and state changes in **functionality, appearance and performance**:
- Functionality: voice ordering, group ordering.
- Appearance: larger images, dark mode.
- Performance: one-tap reorder, faster checkout.

**Benefits of SCAMPER:** encourages creative thinking; improves user experience; increases customer satisfaction; enhances app functionality; creates competitive advantage; finds business opportunities.
**Limitation (add):** it only improves an *existing* product, so it is weaker for fully new concepts.

#### D. Mind mapping

**Short note.** Mind mapping is a visual technique for **organizing information and exploring relationships between ideas around a central topic**. The core problem or idea sits in the *centre* and expands outward into categorized **branches and sub-branches** of words, themes and user insights. It is used to connect thoughts, structure complex data and spark creative solutions.

**Slide example (Smart College App):**

```
                        Smart College App
   ┌───────────┬───────────┬───────────┬───────────┬───────────┐
Attendance    Exams       Fees       Library    Placement
 ├ Percentage  ├ Schedule  ├ Payment  ├ Search   ├ Jobs
 ├ Alerts      ├ Results   ├ Receipt  ├ Issue    ├ Resume
 └ Prediction  └ Forms     └ History  └ Return   └ Interview
```

**Second (design-research) sense in the slides — "mind mapping" as sense-making.** It is the process of looking for *patterns in the large quantity of data collected* during exploration (the "What is" stage). The goal is to establish **design criteria** for the "What if" idea-generation stage. The 7 steps ("yard sale" method):
1. **Hold a yard sale**: lay out all collected data visibly.
2. **Invite shoppers**: 10–50 thoughtful people.
3. **Offer tours**: briefly explain each visual.
4. **Pick out the good stuff**: browse silently and note learnings on Post-its.
5. **Cluster**: sort Post-its into themes. Unassigned notes go on the margin as **outliers**, and these may still matter.
6. **Identify insights** per cluster and the connections between clusters.
7. **Translate into design criteria**: "Based on what you have learned, if anything were possible our design would…"

**Mind mapping vs brainstorming (table to memorize):**

| Brainstorming | Mind mapping |
|---|---|
| Mainly **generates** ideas | **Organizes and connects** ideas |
| Individual or group | Usually visual; individual or group |
| Focuses on **quantity** | Focuses on **relationships** |
| Ideas initially unstructured | Ideas arranged **hierarchically** |
| e.g., generate 20 app ideas | e.g., organize app features into categories |

Best practice: brainstorm first, then mind-map the results.

**How to draw one in an exam (case: "Mind map for an Online Learning App"):** centre = Online Learning App. Branches = Content (videos, notes, quizzes) · Users (student, teacher, admin) · Engagement (badges, streaks, reminders) · Assessment (quiz, feedback, progress) · Tech (mobile, offline mode, AI recommender). Add one sub-branch layer and a colour per branch.

#### E. Other techniques in the slides

**Crazy 8's.** A rapid ideation technique in the Ideate phase: **8 ideas in 8 minutes** (about 1 min per sketch) on an A4 sheet folded into 8 boxes (2 × 4).
- *Steps:* define problem → fold A4 → set 8-minute timer → sketch one idea per box (stick figures and icons are fine) → share and discuss → select the best using user needs, feasibility, innovation, cost and ease of implementation.
- *Example:* university cafeteria ordering → voice ordering, AI meal recommendations, one-click reorder, QR menu, live kitchen status, group ordering, meal subscriptions, AR view of food.
- *Advantages:* many ideas fast, prevents overthinking, equal participation, multiple solution paths.
- *Limitations:* time pressure, needs basic sketching, some ideas unrealistic.

**Six Thinking Hats (Edward de Bono).** The whole team wears *one coloured hat at a time*, which gives balanced discussion and less conflict.

| Hat | Purpose | Key question | Smart food delivery example |
|---|---|---|---|
| White | Facts and information | What do we know? | Average wait is 40 min |
| Red | Emotions, intuition | How do users feel? | Frustrated by delays |
| Black | Risks, caution | What could go wrong? | Traffic causes late delivery |
| Yellow | Benefits, optimism | Why will it work? | Live tracking raises satisfaction |
| Green | Creativity | What new ideas? | AI route optimization, voice ordering |
| Blue | Process and control | What next? | Select best ideas, prototype, user-test |

Advantages: structured thinking, risks found early, teamwork. Limitations: needs practice, can be slow if badly managed.

---

### 3.2 Generating multiple design alternatives

#### A. Basics: alternative, design alternatives, design space

- **Alternative:** a choice limited to one of two or more possibilities, where choosing one precludes the others.
- **Design alternatives:** when a product exists in different designs that **share the same components but arrange or implement them differently**, those designs are design alternatives.
  *Example: "Let clients fetch and update product data" can be built as REST API (resource endpoints, wide tooling), GraphQL (single endpoint, client-shaped queries) or gRPC (binary, fast service-to-service).*
- **Design space:** the imaginary intellectual region containing **all potential solutions** to the design problem. It "conveys a feel for the problem."
  - **Large** design space → many acceptable designs, or many design variables.
  - **Small** design space → a tightly constrained problem, or the options have not been fully explored.
  - Naming the space early gives the team a shared sense of how much room there is.
- Tools to populate and explore the space: **morphological chart** (formal) and **analogical thinking**.

#### B. Morphological chart

**Short note.** A morphological chart is a **matrix** in which the leftmost column lists the principal **functions** the design must perform (plus key features), and each row lists the different **means** (ways) of achieving that function. A complete design is assembled by **choosing one means from each row** and combining them into a functional concept. It is *both* a tool to generate the design space *and* a way to prune infeasible combinations.

**4 steps (V2 slide):**
1. List the **functions** (one per row), at the same level of detail.
2. List the **means** for each function (columns).
3. **Combine** by picking one means per row; that is one candidate design.
4. **Prune** by crossing out combinations that clash or break constraints.

**Rules and cautions from the slides:**
- Keep the list a manageable size and entries at the same level of detail.
- Separate *functions* from *key features*, or the chart gets confusing and large. You may create two charts for two "design spaces."
- The design must satisfy **all** functions in the leftmost column.
- Some functions may have more means than others.
- A *small number of means* suggests a small design space or incomplete exploration.
- Do not develop highly detailed designs at the conceptual stage.
- For big systems, list principal *subsystems* in the first column and create a chart per subsystem.
- *Not all combinations are feasible.* Apply interface constraints, physical principles and common sense.

**Counting designs (numerical-style).**
Number of possible designs = product of the number of means in each row.

*Juice container (slide).* Rows (means): Contain liquid (4: can, bottle, bag, box) · Fill and seal (6) · Empty container (6: pull tab, inserted straw, twist top, tear corner, unfold container, zipper) · Resist forces (2: thick walls, flexible materials) · Identify product (3: shape, distinctive label, colour).
**4 × 6 × 6 × 2 × 3 = 864 combinations**, and only a subset is feasible. Example *infeasible* mix: bottle + glue-container-material + unfold container + flexible materials + colour, which is physically inconsistent. Example *feasible* mix: can + fill-and-heat seal + pull tab + thick walls + shape.

*Login feature (V2 slide).* Auth method (4: email+password, OAuth, biometric, magic link) · Session handling (3: JWT, server session + cookie, token in localStorage) · UI pattern (3: modal, full-page form, inline embedded) · Password recovery (3: email reset link, SMS OTP, security questions).
Total = 4 × 3 × 3 × 3 = **108**.
- ✔ **Feasible:** OAuth + JWT + Modal + Email reset link. It is widely supported and keeps auth stateless for scaling.
- ✗ **Infeasible:** Biometric + localStorage + Security questions. localStorage tokens are XSS-exposed and security questions are a weak recovery path.

*User authentication system (slide).*

| Sub-function | A (simple) | B (standard) | C (advanced / secure) |
|---|---|---|---|
| Primary identifier | Username/email | Phone number | Hardware security key (FIDO2) |
| Verification | Static password | 6-digit SMS OTP | Biometric |
| Session storage | Client-side cookies | Server-side Redis cache | Distributed JWT |
| Login UI trigger | Standard page redirect | Pop-up modal | Magic link / inline passwordless |
| Failure handling | Simple error text | CAPTCHA + lockout | Rate limiting + risk-based IP challenge |

Alternatives = *meaningful combinations*, not random picks. A = all column A (cheap, weak); C = all column C (secure, costly); a hybrid such as phone + OTP + Redis + modal + CAPTCHA is a "standard" design.

**Full worked case — Heatwave Monitoring and Heatmap System (Module 3.2 docx).**
*Problem (HMW):* How might we identify heat-stressed areas in a city and provide timely information to citizens and authorities?

12 functions × 4 means each:

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
| Visualization | Colour heatmap | Risk zones | Charts | 3D map |
| Historical analysis | Daily | Weekly | Monthly | Seasonal |
| Recommendation | Stay indoors | Cooling centre | Route suggestion | Water reminder |

Total theoretical designs = 4¹² = **16,777,216**. This shows why we must build *meaningful* combinations and prune.

The six alternatives in the docx, each a combination:

| Alt | Idea | Flow |
|---|---|---|
| **A** IoT Smart Heatmap | Sensors give heat index, shown as an interactive map for the municipality | IoT → GPS → Heat index → Cloud → GIS heatmap → Web dashboard → Municipality |
| **B** Satellite-based | Large geographic coverage | Satellite → GIS coords → Spatial analysis → Cloud → Raster heatmap → Web GIS → Disaster mgmt |
| **C** Citizen-based | Community-generated heatmap | Mobile location + crowdsourced temp → ML → Interactive map → Mobile app → Citizen |
| **D** Predictive heatwave | Answers "which areas will be dangerous *tomorrow*?" | Weather + Satellite + Historical + IoT → ML → Prediction → Risk heatmap → Early warning → Citizens + Authorities |
| **E** Heat-safe route | Turns the visualization tool into a **decision-support system** ("Route B takes 7 min longer but has lower heat exposure") | Heatmap + Road network + Weather → Route engine → Heat-safe route → Citizen |
| **F** Health-risk system | Adds population data and targets alerts | Temp + humidity + heat index → Risk model + population → Heat-risk map → High-risk zones → Targeted alerts |

**Design-space tree:** Heatwave monitoring splits into Data source (IoT, satellite, weather station, citizen data), Processing (rules, ML, GIS, heat index, prediction) and Interface (web, mobile, GIS, chatbot), which together give multiple designs.

**Evaluation matrix (from the docx, scores 1–5):**

| Criteria | A | B | C | D |
|---|---|---|---|---|
| User value | 5 | 4 | 5 | 5 |
| Feasibility | 5 | 4 | 3 | 3 |
| Cost (5 = cheapest) | 4 | 3 | 5 | 3 |
| Scalability | 4 | 5 | 3 | 5 |
| Innovation | 3 | 4 | 5 | 5 |
| **Total** | **21** | **20** | **21** | **21** |

*Interpretation:* A, C and D tie on 21, so the raw total cannot decide. Break the tie with weights. For example, with weight ×2 on Feasibility (a student project needs something buildable), A = 26, B = 24, C = 24, D = 24, so **prototype A first**. Pipeline: brainstorming → morphological chart → design alternatives → feasibility evaluation → prototype.
**Key teaching message:** a morphological chart does not give *the* solution; it gives a *structured design space* from which many solutions can be built.

**Design-thinking twist (5 questions to ask of any chosen alternative):** Who is the primary user? What pain point is solved? Why these technologies? Is it feasible? What makes it different from existing systems?

#### C. Analogical thinking and metaphors

**Short note.** Analogies point out **parallels or similarities** between a new problem and something already familiar, so the team does not start from a blank page. A *metaphor* is a figure of speech that gives depth to a description by likening it to a more familiar object or process.

| Type | Meaning | Software example |
|---|---|---|
| **Direct analogy** | Looks for parallels or similarities | The "shopping cart" in e-commerce |
| **Symbolic analogy** | Connects through underlying symbolism | Files and folders standing in for paper |
| **Fantasy analogy** | Imagines something fantastic, beyond belief ("thinking outside the box") | A voice assistant as a companion |

**Metaphorical solutions:**
- **Similar** solutions: look for similar ideas.
- **Contrasting** solutions: look for opposite ideas.
- **Contiguous** solutions: adjoining or adjacent ideas, using natural connections between ideas, concepts and artifacts.

**Classic examples:**
- **Desktop metaphor:** the screen is an office desk, files are documents, folders hold them, the trash can means deletion. Users grasp abstract computing instantly.
- **Shopping cart:** checkout models mimic physical retail carts.
- **Trash can:** file deletion mimics throwing paper in a bin.
- **Material Design:** Google mapped digital layers to physical paper and ink responding to light and touch.

#### D. Team ideation games

| Method | How it works | Key rules |
|---|---|---|
| **6-3-5 brainwriting** | 6 members, 3 ideas, 5 rotations of written passing (see 3.1B) | No talking, only written comments; each list makes a full circuit |
| **C-Sketch** | Same as 6-3-5 but each member **sketches** one design idea per sheet and passes it round | Only communication is pencil on paper; suits mechanical or visual design; drawings group information and aid visualization |
| **Gallery method** | Each member develops individual initial ideas in a time box → all sketches posted on a wall, corkboard or Figma board → open group critique and questions → each person revises their own sketch (second-generation idea) → repeat | Iterative; stop when consensus emerges or at a **saturation plateau** (one more cycle gains nothing new) |

**Design generation** is an exciting *goal-directed* creative activity, designed to serve a known purpose (not to search for one). The goal may be imposed externally or internally, and creative activity requires work.

#### E. Navigating the design space — expand or contract

Large spaces are complex (hundreds or thousands of variables, interacting subsystems, many specialists). Strategy is *divide and conquer*: design individual subsystems (small spaces), then combine and connect them.

| ↗ **Expand** (space too small, too few options) | ↘ **Contract** (space too large or complex) |
|---|---|
| **Literature / prior art:** reviews, RFCs, engineering blogs; state of the art | **Apply constraints:** latency, scale, security, cost; external constraints |
| **Patent / open-source search:** identify available technology, "don't reinvent the wheel" | **Freeze scope early:** freeze the number of features; defer nice-to-haves |
| **Competitor benchmarking:** try competing products, measure performance | **Prioritize by impact:** rank against real requirements and problem-definition data |
| **Reverse engineering:** see how existing systems perform a function and find alternate means | **"Get real!" check:** plain engineering judgment to rule out infeasible ideas |

**Final word.** Resources (time, money, manpower) are scarce. The aim is not to keep every alternative alive but to *generate enough to make a confident choice*. Blend morphological charts, design-generation games, research, experience-based judgment and gut feeling.

---

### 3.3 Storyboarding and user journey mapping

*Source: the V2 slides for this section are empty headings, so the content comes from the docx and standard UX practice.*

#### A. Storyboarding

**Definition.** A storyboard is **a visual sequence of events (scenes) that describes how a user interacts with a product or solves a problem.** It is a visual representation of a user's experience through a sequence of scenes. It borrows from film and animation and is used in the Ideate and Prototype stages to test an idea *before* building it.

**Elements:** characters (persona), context/setting, scenes (panels in order), captions or narration, user actions, emotions (shown on faces), and the outcome or resolution.

**Steps to create:** (1) pick the persona and scenario/problem → (2) define the start and end points → (3) list the key events → (4) sketch one panel per event (simple sketches) → (5) add captions, thoughts and emotions → (6) review with the team or users and refine.

**Example (docx) — Smart teaching-learning system:**

```
[Student has difficulty] → [Opens app] → [Logs into account]
   → [App identifies weak subject] → [App recommends learning material]
   → [Student studies material] → [Student takes quiz] → [App gives feedback]
```

**Why use it (benefits):**
- **Tells a story:** it shows *context* and *emotion*, not only screens.
- It communicates ideas to team members and stakeholders quickly.
- It exposes gaps and unrealistic assumptions before design and coding.
- It is cheap, fast and low-fidelity.
- It keeps the design user-centred.
- It helps pick between design alternatives (it links to 3.2).

**Limitations:** it needs drawing effort, it shows one scenario only, and it is not a precise interface specification.

#### B. User journey mapping

**Definition.** A user journey map represents **the complete experience of a user while interacting with a product, service or system**, across stages over time, including what the user *does, thinks and feels* and where the pain points are.

**Components (rows) of a map:** persona/scenario · **stages** (columns) · **user actions** · **thoughts** · **emotions** (a curve or emoji) · **pain points** · **touchpoints** · **opportunities** for design improvement.

**Steps to create:** (1) choose persona and goal → (2) list stages end to end → (3) fill actions → (4) record thoughts and emotions (from user research) → (5) mark pain points → (6) identify opportunities → (7) validate with users.

**Example (docx) — Smart teaching-learning application:**

| Stage | User action | User thought | Emotion | Pain point |
|---|---|---|---|---|
| Login | Opens application | "I need to study." | Neutral | Login may take time |
| Search | Searches for topic | "Where can I find notes?" | 😞 Bad | Too many resources |
| Recommendation | Views recommended content | "This looks useful." | 😀 Good | — |
| Learning | Studies video or notes | "Now I understand." | Neutral to positive | Difficult topic |
| Quiz | Attempts quiz | "How well did I perform?" | 😟 Anxious | Questions may be difficult |
| Feedback | Checks score | "I need more practice." | 😞 Bad | Limited explanation |

**Reading the map:** the low points (Search, Quiz, Feedback) are design opportunities, for example better search filtering, hints for hard questions, and detailed explanations after feedback.

**Benefits:** gives a user-eye view of the whole experience; finds pain points and moments of truth; builds empathy; aligns teams; prioritizes improvements. **Limitations:** based on one persona and may be assumption-driven unless backed by real research.

**User flow (related, asked in [23]).** A user flow is a diagram (boxes and arrows with decision diamonds) of the *steps a user takes to complete one task*, for example login → search → add to cart → pay. It is task-focused and shows decisions and paths, but not emotions.

#### C. Storyboard vs user journey map vs related tools

| Aspect | Storyboard | User journey map | User flow |
|---|---|---|---|
| Form | Visual **scenes / sketches** in sequence | Tabular or graphical **stages × rows** | Flowchart of **steps and decisions** |
| Focus | A specific scenario, narrative | The *entire* experience | One task path |
| Emotion | Shown in the drawing | Explicit emotion row or curve | Not shown |
| Scope | One story | End-to-end with pain points | Task level |
| Stage used | Ideate | Empathise / Define / Ideate | Define / Design |
| Output | Shared understanding of an idea | Pain points and opportunities | Navigation structure |

**Storyboard vs wireframe** (asked [25]; MCQ [21]):

| Storyboard | Wireframe |
|---|---|
| Sequence of scenes showing a user's *story* and context | Skeleton layout of a *single screen* |
| **Dynamic** (shows time, flow and emotion) | **Static** (no flow, no emotion) |
| Answers "how/why will the user use it?" | Answers "where does each element go?" |
| Early, low fidelity, often hand-drawn | Mid-fidelity, drawn in Figma or on paper |
| Includes people and context | Includes only UI elements |

---

## 4. PYQ SOLUTIONS (module-relevant only)

**Filter result.** I checked all 11 papers. Only these appear for Module 3; they are all in 3.3. Everything on UX principles, usability testing, AR/VR, personas, empathy maps and wicked problems belongs to Modules 1–2 or to the UX course, so it is excluded.

| # | Paper | Question | Marks | Type |
|---|---|---|---|---|
| 1 | [22] Q1(i) | "A storyboard is a great way to tell the stories." Justify. | 5 | Justify |
| 2 | [25] Q5(vi) | Difference between wire-framing and storyboarding | 5 | Compare |
| 3 | [21] Q1(A)(9) | MCQ: Wireframing and storyboard are ___ & ___ tools | 1 | MCQ |
| 4 | [23] Q3(ii) | What are user flows? How does it benefit the UX designer in depicting the user journey? | 10 | Theory (adjacent) |
| 5 | [23] Q2(A) OR | "Great questions lead to great design." Map to user research and journey with example | 10 | Case (adjacent) |
| 6 | [23] Q3(iii) | With example, how UX stories capture attention, provide clarity and inspire designers | 10 | Theory + example (adjacent) |

Q4–Q6 are adjacent: they touch journey and story, so they may recur in the SDT paper.

### PYQ 1 — [22] Q1(i): "A storyboard is a great way to tell the stories." Justify. (5 marks)

**Answer.** A storyboard is a **visual sequence of scenes** showing how a particular user, in a particular context, interacts with a product to reach a goal. It is a good storytelling tool because:

1. **Human context.** It shows *who* the user is, *where* and *why*, so the design is judged against a real situation rather than a feature list.
2. **Sequence and time.** Panels follow a beginning, middle and end, showing the *flow* of the interaction.
3. **Emotion.** It captures feelings (frustrated, relieved) and pain points, building empathy.
4. **Shared understanding.** Designers, developers and clients "see the same story" instantly, without long documents.
5. **Cheap early validation.** Sketches reveal missing steps and wrong assumptions before costly development.

*Example (draw 5–6 boxes):* Smart learning app: ① student struggles with a subject → ② opens the app → ③ the app finds the weak subject → ④ recommends notes → ⑤ takes a quiz → ⑥ gets feedback and feels confident.

**Conclusion:** because it combines user, context, sequence and emotion in one visual, a storyboard communicates the user's story better than text.

### PYQ 2 — [25] Q5(vi): Difference between wire-framing and storyboarding. (5 marks)

| Point | Wireframing | Storyboarding |
|---|---|---|
| Meaning | Skeletal **layout of a screen** showing placement of elements | **Sequence of scenes** showing how a user uses the product to solve a problem |
| Nature | **Static** | **Dynamic** (flow over time) |
| Focus | Structure, layout, content hierarchy | User, context, actions, emotion |
| Question answered | *Where* does each element go? | *How* and *why* is the product used? |
| Fidelity | Low to mid, UI-only | Low, hand-drawn people and scenes |
| Stage | Design / prototype | Ideate / early concept |
| Example | Login-screen box layout | Panels from "student struggles" to "student gets feedback" |

(Write the 5–6 points; the example row earns marks.)

### PYQ 3 — [21] Q1(A)(9): "Wireframing & storyboard are ______ & ______ tools used for designing interface" (1 mark)

**Answer: (c) Static & Dynamic.** A wireframe shows one fixed layout (static). A storyboard shows a sequence of interactions over time (dynamic).

### PYQ 4 — [23] Q3(ii): What are user flows in UX design? How do they benefit the UX designer in depicting the user journey? (10 marks)

**Definition.** A **user flow** is a diagram of the **path a user takes to complete a task** in a product, from the entry point through each screen and decision to the final outcome. It uses boxes (screens/actions), diamonds (decisions) and arrows (direction).

**Elements.** Entry point · screens or steps · decision points (yes/no) · actions · system responses · exit/goal · error or alternate paths.

```
[Open app] → [Search product] → [Select product] → ◇ Logged in?
                                                     ├ No → [Login/Register] ─┐
                                                     └ Yes ◄──────────────────┘
→ [Add to cart] → [Address] → [Payment] → ◇ Payment OK? ─ No → [Retry]
                                                        └ Yes → [Order confirmation]
```

**How it benefits the designer in depicting the user journey:**
1. **Visualizes the task path.** The journey (the user's overall experience) is broken into concrete, ordered steps.
2. **Finds friction.** Extra steps, dead ends and confusing decision points show up early (a link to SCAMPER "Eliminate").
3. **Handles alternatives.** It shows error, retry and alternate routes, not just the happy path.
4. **Aligns the team.** Designers, developers and stakeholders agree on navigation before screens are drawn.
5. **Guides information architecture and wireframes.** Each box becomes a screen.
6. **Supports testing.** Usability tests can follow each path and measure drop-off.
7. **Complements journey maps.** The journey map shows *how the user feels* at each stage, and the user flow shows *what the user does*.

**Difference from a journey map:** a user flow is task-based and system-oriented, with no emotions. A journey map is experience-based and covers feelings and pain points across stages.

### PYQ 5 — [23] Q2(A) OR: "Great questions lead to great design." Map the statement to user research and journey with an appropriate example. (10 marks)

**Explanation of the statement.** A design can only be as good as the problem it solves. Asking the *right questions* in research uncovers real needs and pain points. Those insights shape the journey map and finally the design.

**Mapping (Question → Research method → Journey stage → Design response)** — Example: a **college placement-preparation app**.

| Journey stage | Great question to ask | Research method | Insight | Design response |
|---|---|---|---|---|
| Awareness / Login | "How do you currently find out about placement drives?" | Interview | Students miss notices on scattered WhatsApp groups | Central notification feed |
| Search | "Walk me through your last search for company details. Where did you get stuck?" | Observation / contextual inquiry | Too many unorganized resources | Filters and recommended content |
| Preparation | "What stops you from practising regularly?" (5 Whys) | Interview, diary study | No personalized plan, loses motivation | Personalized roadmap, streaks |
| Assessment | "How do you feel before a mock test?" | Survey (Likert) | Anxiety about difficult questions | Practice mode with hints |
| Feedback | "What do you do after you see your score?" | Usability test | Limited explanation, no next step | Detailed solutions and next-topic suggestion |

**Flow of the argument:**
1. **Great questions** are open-ended, ask about stories rather than opinions ("Tell me about the last time…"), and use "why" to reach root causes.
2. They are asked through **user research** (interviews, surveys, observation) and give the *what, why and feel* at each step.
3. The answers are mapped onto the **user journey** as actions, thoughts, emotions and pain points, which makes the weak moments visible.
4. Pain points become **design opportunities**, and the result is a design that fits real needs ("great design").

**Conclusion:** poor questions give surface answers and a generic design. Good questions give deep insight, an accurate journey map and a design that addresses real pain points.

### PYQ 6 — [23] Q3(iii): Explain with an example how UX stories capture attention, provide clarity and inspire UX designers to take decisions. (10 marks)

**What a UX story is.** A UX story is a short narrative about a user (a persona with a goal, context, obstacles and outcome). It can be told as text, a storyboard or a journey. It turns research data into something people remember.

**Running example:** *Alex*, a shy final-year student, misses a placement notice because it is buried in a chat group and loses an interview opportunity.

**1. Captures attention**
- A person with a name, a feeling and a problem is more memorable than a table of statistics.
- *Example:* "Alex found out about the drive one day late" engages the team more than "30% of students miss notices."

**2. Provides clarity**
- The story gives *context* (who, where, when, why) and the step-by-step sequence, so the problem is understood the same way by everyone.
- *Example:* the story shows that the real problem is *notice discovery*, not "a bad UI," so the team defines the problem correctly (HMW: How might we make sure every student sees relevant drives in time?).

**3. Inspires designers to make decisions**
- It creates empathy and urgency, and it becomes a yardstick for choosing between design alternatives: "Does this help Alex?"
- *Example:* options are a push notification, a weekly email digest or a personalized feed. The story shows Alex needs *timely, personal* alerts, so the team picks push notification + personalized feed.
- Stories also help prioritize features and justify decisions to stakeholders.

**4. Aligns the team and supports validation.** Everyone shares one story, and the final design can be tested against it (does Alex now succeed?).

**Conclusion:** UX stories translate data into human experience. They catch attention through emotion, bring clarity through context and sequence, and give designers a user-based basis for decisions.

### Adjacent but not Module 3 (noted, not solved)

- [22] Q1(iv) *How flowcharts help in UX design*: uses the same material as PYQ 4 (flows; steps, decisions, friction). Reuse that answer if it comes up.
- [22] Q5(vi) *Design Thinking* (short note), [22] Q3(iii) *Empathy map*, personas, wicked problems: **Module 1/2**.

---

## 5. EXPECTED QUESTIONS (not PYQs; prepared because 3.1 and 3.2 will be asked)

Likely marks in the SDT paper: 5-mark short notes and 10-mark cases. Model answers sit in Part 3. Here is the exam-ready skeleton for each.

**Q-A. Explain brainstorming. State its principles. (5 marks)**
Definition (2 lines) → 5 principles with one-line examples → process flow → hospital example → 1 advantage and 1 limitation. All in section 3.1A.

**Q-B. Explain SCAMPER with a software example. (5 or 10 marks)**
Definition ("change the existing software") → 7-row table (letter, question, example) → full food-delivery case with a before/after table → benefits. Section 3.1C.

**Q-C. Apply SCAMPER to improve a food ordering / WhatsApp / campus visitor / ERP / library app. (10 marks)**
Use the 7-row Version 1 / Version 2 table. Always cover functionality, appearance and performance. Finish with *evaluate* (feasibility × value) and *select* (this earns bonus marks).

**Q-D. What is mind mapping? Differentiate from brainstorming. Draw a mind map for a Smart College App. (5–10 marks)**
Definition → draw the centre-and-branches diagram → 5-row comparison table → the 7 "yard sale" steps if marks allow.

**Q-E. What is a morphological chart? Construct one for a login feature and show feasible and infeasible combinations. (10 marks)**
Definition → 4 steps → login chart with 4 × 3 × 3 × 3 = 108 → feasible (OAuth + JWT + Modal + Email reset) vs infeasible (Biometric + localStorage + Security questions), each with a reason → conclusion (pruning).

**Q-F. Explain design alternatives and design space. (5 marks)**
Definitions → REST/GraphQL/gRPC example → large vs small space → morphological chart and analogical thinking as tools.

**Q-G. Explain analogical thinking and metaphors in design. (5 marks)**
Direct / symbolic / fantasy table with an example each → desktop metaphor.

**Q-H. Explain 6-3-5, C-Sketch and Gallery methods. (5–10 marks)**
Section 3.2D table. For a numerical version, compute ideas = 6 × 3 × 6 = 108.

**Q-I. How do you expand and contract a design space? (5 marks)**
Section 3.2E two-column table.

**Q-J. Heatwave monitoring: generate design alternatives using a morphological chart and select one. (10 marks)**
Chart → 2–3 alternatives as flows → evaluation matrix with scores and a weighted tie-break → choose one to prototype.

**Q-K. Difference between storyboard and user journey map. (5 marks)**
Section 3.3C table, with a one-line example for each.

**Q-L. Draw a journey map for any app (learning, food delivery, banking). (10 marks)**
Use the 6-stage table (stage, action, thought, emotion, pain point) and add an "Opportunities" column.

**Q-M. Crazy 8's or Six Thinking Hats with example. (5 marks)**
Section 3.1E.

---

## 6. APPENDIX — in the slides, but not in the pasted syllabus (read only if time remains)

The slide deck's own Module 3 outline lists two more items: *design heuristics for software solutions* and *evaluating idea feasibility and prioritization*. Your pasted syllabus ends at 3.3. If your faculty includes them, these are the essentials.

### A. Design heuristics

Heuristics are practical **rules of thumb** for making good design decisions when there is no single correct answer. They are used to evaluate and improve alternatives.

**Nielsen's 10 usability heuristics (with one example each):**
1. **Visibility of system status:** progress bars, "You are here" markers.
2. **Match between system and real world:** use the user's language and familiar icons (trash can, calculator).
3. **User control and freedom:** undo, redo, cancel, an "emergency exit."
4. **Consistency and standards:** internal consistency (within the product) and external (platform conventions).
5. **Error prevention:** confirmation dialogs, good defaults and constraints.
6. **Recognition rather than recall:** visible options and suggestions in search.
7. **Flexibility and efficiency of use:** shortcuts and personalization for experts.
8. **Aesthetic and minimalist design:** no irrelevant information.
9. **Help users recognize, diagnose and recover from errors:** plain-language messages that suggest a solution.
10. **Help and documentation:** concise, task-focused, searchable.

**Software design heuristics (checklist):** simplicity · modularity · **high cohesion** · **low coupling** · separation of concerns · DRY · reusability · consistency · visibility and feedback · error prevention · abstraction · scalability · security · failure handling · design for change · use patterns · balance trade-offs.

### B. Feasibility

Feasibility is the technical filter on human-centred ideas: can it be built, deployed on time and within budget? It is judged alongside *desirability* (what users want) and *viability* (what the business should build).

| Type | Asks |
|---|---|
| Technical | Does it fit the stack? Are APIs and data available? Does it meet performance and scale targets? Does the team have the skills? |
| Operational | Maintainability, technical debt, monitoring, CI/CD, disaster recovery |
| Economic | Cloud and compute cost, person-months of effort, cost-benefit |
| Legal, security, regulatory | Privacy (GDPR, HIPAA), security architecture (RBAC, zero-trust), PCI-DSS, SOC 2 |

**Validation techniques:** technical spike, proof of concept (PoC), architecture prototype, risk matrix analysis.

### C. Prioritization

**1. Value vs Effort 2×2:**

| | Low effort | High effort |
|---|---|---|
| **High value** | **Quick wins** (do first) | **Major projects** (plan) |
| **Low value** | **Fill-ins** (when idle) | **Thankless tasks** (drop) |

**2. MoSCoW:** Must have (needed for launch) · Should have (important, workaround exists) · Could have (nice to have) · Won't have (this release).

**3. KANO:** Must-be / basic (login; absence hurts) · One-dimensional / performance (speed; more is better) · Attractive / delighter (unexpected delight) · Indifferent (no one cares) · Reverse (annoys users, for example aggressive pop-ups).

**4. RICE score = (Reach × Impact × Confidence) ÷ Effort.**
Impact scale: 3 massive, 2 high, 1 medium, 0.5 low, 0.25 minimal. Confidence: 100% / 80% / 50%. Effort in person-months.

*Worked example.* Feature X: reach 2000 users/quarter, impact 2, confidence 80%, effort 4 person-months → (2000 × 2 × 0.8) / 4 = **800**. Feature Y: reach 500, impact 3, confidence 100%, effort 1 → (500 × 3 × 1) / 1 = **1500**. Y ranks higher.

| Approach | Best for | Strength | Pitfall |
|---|---|---|---|
| Value vs Effort | Early design workshops | Fast visual consensus | Subjective estimates |
| MoSCoW | Fixed-scope release planning | Clear MVP boundaries | Everything becomes "Must" |
| KANO | UX refinement | Validates real user desire | Needs research and surveys |
| RICE | Mature product roadmap triage | Data-backed objectivity | Complex math on estimates |

---

## 7. LAST-MINUTE REVISION CARD

- **Ideation** = many solutions before choosing; bridges user needs to software concepts; diverge then converge.
- **Brainstorming** = quantity first. 5 rules: defer judgment, quantity, wild ideas, build on others, focused HMW.
- **6-3-5** = 6 people × 3 ideas × 5 min, 6 rounds, **108 ideas / 30 min**; silent, written; m-3-(m−1).
- **SCAMPER** = Substitute, Combine, Adapt, Modify/Magnify/Minify, Put to another use, Eliminate, Reverse/Rearrange. It modifies something that already exists.
- **Mind map** = centre → branches → sub-branches; organizes and connects (brainstorm = generates).
- **Crazy 8's** = 8 ideas, 8 minutes. **Six Hats** = White facts, Red feelings, Black risks, Yellow benefits, Green ideas, Blue process.
- **Design space** = all potential solutions. **Morph chart** = functions × means, pick one per row, **count = product**, prune infeasible. Juice = 864; Login = 108; Heatwave = 4¹².
- **Analogies:** direct, symbolic, fantasy. Metaphor solutions: similar, contrasting, contiguous. Desktop metaphor.
- **Games:** 6-3-5, C-Sketch (sketching), Gallery (post, critique, revise, saturation plateau).
- **Expand:** literature, patent, benchmark, reverse-engineer. **Contract:** constraints, freeze scope, prioritize, "Get real!".
- **Storyboard** = visual scenes with a story, dynamic. **Wireframe** = layout of a screen, static. **Journey map** = stages × (action, thought, emotion, pain point), the whole experience. **User flow** = task steps and decisions.
- **PYQ pattern:** storyboard vs wireframe, storyboard justify, user flow / journey, UX stories. Never yet: brainstorming, SCAMPER, mind map, morph chart. Prepare them anyway.
