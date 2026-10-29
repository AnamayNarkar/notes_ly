# SDT_Mod_1 — Software Design Thinking, Module 1: Introduction to Software Design Thinking (09 hrs, CO1)

> **Sources I went through (all of them):** `Module 1.pptx` (72 slides, incl. Netflix/IBM/Airbnb/Moonrise cases, SCAMPER, 10-tool slides), the two lecture PDFs (58 slides), `SDT Module 1 — Exam Reference.pdf`, `Design_Thinking_in_SE-notes.pdf`, `Divergent and convergent in Design Thinking-notes.pdf`, and all 10 scanned PYQ screenshots + `User Experience Design.PDF` (2 pages) in `../question_papers_all_time/`.
>
> **Honest note on the PYQs:** the old papers are for the course *User Experience Design* (UXD), plus one *Software Architecture & Design Thinking* paper (May 2023, 100 % architecture → not this module). Only the UXD questions that overlap with Module 1 (design thinking, design process/stages, wicked problems, user-centred design, problem framing, "know the user first") are used. Empathy map, personas, user research, usability testing, heuristics, AR/VR, 5S model, Gestalt etc. belong to Module 2+ / other units and are **excluded**.
>
> **Marking:** 🔴 = this exact topic + question-type has appeared in a PYQ. ⚪ = not yet asked in PYQs but likely/possible (from syllabus & notes). — = not applicable.

---

## 1. TOPIC MAP

```
MODULE 1 : INTRODUCTION TO SOFTWARE DESIGN THINKING
│
├── 1.1 Concept of Design Thinking in Software Engineering
│   ├── Definition (human-centred, iterative, creative + empathetic + experimental)
│   ├── Why it matters (real problems, UX, cost, innovation, collaboration, Agile/DevOps fit)
│   ├── Stakeholder view (house-building example: engineer, architect, decorator, owner, end users)
│   ├── Interdisciplinary team (designers, behavioural scientists, marketers, engineers)
│   ├── Three Spaces of Innovation  (non-linear, iterative)
│   │   ├── Inspiration   → watch what they DO / listen to what they SAY / experience what they FEEL
│   │   │                   (latent needs, target the extremes, technocentric → human-centred)
│   │   ├── Ideation      → quantity over quality, one problem → many solutions
│   │   └── Implementation→ project room → market
│   ├── Approach to Design : 10 Tools
│   │   ├── What is?     : 1 Visualization (runs through ALL), 2 Journey Mapping,
│   │   │                  3 Value Chain Analysis, 4 Mind Mapping
│   │   ├── What if?     : 5 Brainstorming, 6 Concept Development
│   │   ├── What wows?   : 7 Assumption Testing, 8 Rapid Prototyping
│   │   └── What works?  : 9 Customer Co-Creation, 10 Learning Launch
│   ├── 4 PMA (Project Management Aid) tools
│   │   └── Design Brief · Design Criteria · Napkin Pitch · Learning Guide
│   └── 4-Stage Design Process : What is? → What if? → What wows? → What works?
│
├── 1.2 Stages : Empathize → Define → Ideate → Prototype → Test   (non-linear loop)
│   ├── Empathize  : Observation & Shadowing · Deep-dive interviews ("why?" ×5) · Immersion
│   ├── Define     : synthesis → POV statement → "How Might We" (HMW)
│   ├── Ideate     : rules (defer judgment, wild ideas, build on others)
│   │                techniques → Brainstorming · Brainwriting · Mind Mapping ·
│   │                SCAMPER · Morphological Chart · Crazy 8s
│   ├── Prototype  : low-fidelity (sketch / paper / wireframe) — "fail fast to learn faster"
│   ├── Test       : real users, friction points, validate not sell
│   ├── Iterative cycle : Insights → Redefine → Iterate → Refine → Launch
│   └── Diverge ⇄ Converge pattern inside EVERY stage
│
├── 1.3 Human-Centred (Software) Design — HCD / HCSD
│   ├── Definition (technology-first → people-first)
│   ├── 4 Core Principles : Focus on People · Fix the Root Problem ·
│   │                       Everything is a System · Iterate Continuously
│   ├── 6 Key Characteristics : user-focused, empathy-driven, iterative,
│   │                           evidence-based, accessible, collaborative
│   ├── 5 Principles of HCSD : understand users · involve users throughout ·
│   │                          usability · iterative design · accessibility & inclusivity
│   ├── Merits (6)
│   └── Case: College Canteen (personas, facilities, food-order system)
│
├── 1.4 Design vs Traditional Problem-Solving
│   ├── Comparison table (focus, process, approach, failure, feedback, experiments, framing, team)
│   ├── Wicked problems (definition, characteristics, example, why DT suits them)
│   ├── 4-stage design process (diverge/converge in each)
│   └── Problem-finding (DT) vs Problem-solving (Agile) → Dual-Track Agile
│
└── 1.5 Case Studies on Successful Design Thinking in Software
    ├── Taught in class : Netflix · IBM Design Thinking · Airbnb ·
    │                     American Family Insurance + IDEO "Moonrise"
    ├── Worked scenarios : Student Portal · Smart Campus Navigator · College Canteen ·
    │                      IRCTC · Uber ride selection (✱ = ride-booking appeared in PYQ)
    └── How to answer : "apply DT to X" → map 5 stages with specifics
```

---

## 2. TOPIC-WISE QUESTION TYPES

This subject has **no numericals / derivations**. Question types seen: **short theory (5 M)**, **long theory/explain (10 M)**, **compare/differentiate**, **case-scenario application (10 M)**, **diagram-based** (draw/illustrate), **justify/"why" statements**, and **MCQ/fill-in (1 M, 2021 paper)**.

| Topic | Short theory (5 M) | Long theory (10 M) | Compare / differentiate | Case / scenario application | Diagram / illustrate | Justify / reason | MCQ / fill-in |
|---|---|---|---|---|---|---|---|
| 1.1 Concept of DT / 3 spaces | 🔴 (Dec 2022: "Design Thinking" short note) | ⚪ | ⚪ | ⚪ | ⚪ (3-space loop) | ⚪ | ⚪ |
| 1.1 10 tools / PMA / 4-stage process | ⚪ | ⚪ | ⚪ (tool-vs-tool) | ⚪ | ⚪ (wave diagram) | — | ⚪ |
| 1.2 Five stages (Empathize…Test) | ⚪ | 🔴 (2024 Q2A: six stages – AC remote; 2021 Q4a: six stages – ride booking) | ⚪ | 🔴 (same two) | 🔴 ("neat diagrams" instruction) | 🔴 (2024 Q1: justify problem-formulation / Define step) | ⚪ |
| 1.2 Empathize / "know the user first" | ⚪ | ⚪ | — | ⚪ | — | 🔴 (2021: justify need to know the user before designing) | — |
| 1.2 Ideation techniques (brainstorm, SCAMPER, morph. chart) | ⚪ | ⚪ | ⚪ (brainstorm vs brainwriting; morph chart vs mind map) | ⚪ | ⚪ (mind map / chart) | — | — |
| 1.2 Diverge–Converge | ⚪ | ⚪ | ⚪ | ⚪ | ⚪ (double diamond) | — | — |
| 1.3 Human-centred design | 🔴 (2023: goal-directed → user-centred; 2021: need of user-centric design) | 🔴 (2023 Q2B: phases for achieving user-centric design) | ⚪ | ⚪ | — | 🔴 (2021 "justify the need…") | 🔴 (2021 MCQ: "UCD is ___") |
| 1.4 Design vs traditional | ⚪ | ⚪ | ⚪ (very likely – table) | — | — | — | — |
| 1.4 Wicked problems | 🔴 (Nov 2023; 2021 UI design as wicked problem) | 🔴 (Dec 2022 Q3i: illustrate steps; 2024 Q2B ii: why wicked + how to take care) | — | 🔴 (give example w.r.t. UI/UX) | — | 🔴 ("Why are some problems called wicked?") | — |
| 1.5 Case studies (IRCTC / Uber / campus / Netflix / Airbnb…) | ⚪ | 🔴 (ride-booking, 2021) | — | 🔴 | ⚪ (stage table / flow) | — | — |

**Hot-spot summary (by PYQ frequency):** Wicked problems (4 papers!) > Five/six-stage process applied to a scenario (2 papers) > User-centred design (2 papers) > "Design Thinking" short note (1) > Define step/problem formulation (1) > Need to know user first (1).

---

## 3. TOPIC-BY-TOPIC DETAILED BREAKDOWN

### 3.1 Concept of Design Thinking in Software Engineering

**Easy explanation:** Normally engineers ask *"What can we build?"* Design Thinking (DT) flips this to *"What do people actually need?"* It is a **human-centred, iterative problem-solving approach** that mixes **creativity + empathy + experimentation**. You first understand the user, then define the *right* problem, then generate ideas, build cheap prototypes, test with real users, and keep looping.

**Short note (5 M) — how to write:**
> *Design Thinking is a human-centred, iterative problem-solving methodology that combines creativity, empathy and experimentation to solve complex problems. In software engineering it makes developers understand users deeply before designing/coding. It has five stages — Empathize, Define, Ideate, Prototype, Test — which are non-linear. Importance: solves real (not assumed) problems, improves UX and satisfaction, encourages innovation, reduces cost by finding issues early, supports iterative development, and promotes collaboration between developers, designers, testers and stakeholders. Benefits: user-friendly software, lower project risk, better stakeholder communication, supports Agile & DevOps.* Add a one-line example (e.g., student portal: students can't find exam schedules → dashboard of deadlines).

**Stakeholder example (from slides – the "building a home" analogy):** Different stakeholders have different points of view, so design must balance them.

| Stakeholder | POV / Interest |
|---|---|
| Civil engineer | Stability, safety |
| Architect | Standards |
| Interior decorator | Aesthetics |
| Home owner | Return on investment |
| House-wife | Efficiency, maintenance, management |
| Children | Facilities, entertainment |
| Elderly | Accessibility, comfort |

Lesson: designing a product needs an **interdisciplinary team** (designers, behavioural scientists, marketers, engineers) who identify appropriate **constraints**, and who stay involved from inspiration → ideation → implementation.

#### Three Spaces of Innovation (very important)
Not a straight line — the team **loops back** repeatedly.

```
      ┌──────────────┐     ┌────────────┐     ┌────────────────┐
      │ INSPIRATION  │ ──► │  IDEATION  │ ──► │ IMPLEMENTATION │
      │ (problem /   │ ◄── │ (generate, │ ◄── │ (project room  │
      │ opportunity) │     │ develop,   │     │  → market)     │
      └──────────────┘     │ test ideas)│     └────────────────┘
                           └────────────┘      (iterative loops)
```

| Space | Meaning | Key points |
|---|---|---|
| **Inspiration** | Problem/opportunity that motivates the search for solutions; team *immerses in the user's world* | **Divergent exploration**; **uncover latent needs** (needs users can't state because they've adapted to bad design); **shift perspective** technocentric → human-centred. Approach: **watch what they DO**, **listen to what they SAY**, **experience what they FEEL**. **Target the extremes** (extreme users expose pain points & flaws). |
| **Ideation** | Generating, developing and testing ideas | **Quantity over quality**; *one problem → many solutions*; don't settle on one idea |
| **Implementation** | Path from project room to the market | Iterative path to product/launch |

#### Approach to Design — the 10 Tools
Memorize the one-liners (the sequence in the diagram — slide 39 — is the key to remember which tool goes where).

| # | Tool | One-line definition | Key points to add in a 5 M answer |
|---|---|---|---|
| 1 | **Visualization** | Use imagery/diagrams to envision possibilities & bring ideas to life | Integral to *all* other tools; sketches, diagrams, storyboards replace dense text; bridges language gaps between multidisciplinary members; reveals missing elements/logic flaws early; enhances empathy |
| 2 | **Journey Mapping** | Assess the existing end-to-end experience through the *customer's* eyes | Captures touchpoints/actions; shows emotional highs & lows; reveals pain points & "moments of truth"; exposes gap between what company thinks it delivers vs. what users experience |
| 3 | **Value Chain Analysis** | Assess the enterprise operations (back-stage) supporting the customer journey | Finds bottlenecks/redundancies; checks flexibility of chain for new solutions; partners/vendors; bridges desirability with feasibility |
| 4 | **Mind Mapping** | Synthesize exploration insights visually to form **design criteria** | Central theme → branches; clusters & relationships; bridge between exploration & ideation; stops rush to solutions |
| 5 | **Brainstorming** | Generate new possibilities / alternative business models | Defer judgment, quantity over quality, wild ideas welcome, build on others; raw material for filtering |
| 6 | **Concept Development** | Assemble innovative elements into a coherent alternative solution for evaluation | Combine ideas into complete packages; assess **desirability, feasibility, viability**; drop weak/redundant parts |
| 7 | **Assumption Testing** | Isolate & test key assumptions that make/break a concept | Ask "what must be true?"; prioritise by uncertainty × impact; cheap & quick; evidence over blind faith |
| 8 | **Rapid Prototyping** | Express the concept in tangible form for testing & refinement | Paper mock-ups, storyboards, wireframes; speed & low cost; fail early & cheaply; builds stakeholder consensus |
| 9 | **Customer Co-Creation** | Enrol customers to participate in creating the solution | Design *with* not *for* customers; workshops; uncovers latent needs; ownership & loyalty; faster iteration |
| 10 | **Learning Launch** | Affordable, real-world experiment over an extended time to test assumptions with market data | Purpose is learning, not revenue; small controlled rollout; metrics (engagement, retention); evidence to scale/pivot/cancel; bridges prototype and full launch |

#### The 4-stage Design Process & where tools sit (slide 39 diagram)

```
 What is?            What if?              What wows?           What works?
 (current reality)   (visualise new        (make choices for    (feasible solution)
                      future)               better solution)
 ╱╲   ╱╲            ╱‾‾‾‾╲               ╱╲  ╱╲                ╱╲  ╱╲
╱  ╲ ╱  ╲          ╱      ╲             ╱  ╲╱  ╲              ╱  ╲╱  ╲
 2   3   4            5     6              7    8                9    10
 Journey Value Mind   Brain- Concept       Assump. Rapid        Customer Learning
 Map   Chain Map      storm  Develop.      Testing Prototyping  Co-Create Launch
 (1 Visualization spans the whole process)
 ▲ Design Brief      ▲ Design Criteria     ▲ Napkin Pitch       ▲ Learning Guide
```
Each question is answered by **diverging** (broadening, many options) then **converging** (narrowing to the most promising) — hence the wave/“double diamond” shape.

#### 4 PMA (Project Management Aid) tools
| PMA | Tool | Purpose |
|---|---|---|
| 1 | **Design Brief** | Formalizes the project; defines goals, resources, timelines; the **"North Star"** |
| 2 | **Design Criteria** | Criteria to evaluate alternative designs (from user needs + business requirements); part of the brief |
| 3 | **Napkin Pitch** | Crystallizes the best 3–5 solutions (after brainstorming & concept development) in a template (Need / Approach / Benefit / Competition) → apples-to-apples comparison |
| 4 | **Learning Guide** | Defines an affordable level of resources to invest in testing whether the top 2–3 concepts are feasible |

---

### 3.2 The Five Stages: Empathize, Define, Ideate, Prototype, Test

**Core rule:** non-linear and iterative — you can return to any stage; insights in Test often send you back to Empathize/Define.

```
 EMPATHIZE ─► DEFINE ─► IDEATE ─► PROTOTYPE ─► TEST
     ▲           ▲         ▲          ▲           │
     └───────────┴─────────┴──────────┴───────────┘   (feedback loops)
```

| Stage | Goal | Methods / activities | Output | Example (student portal) |
|---|---|---|---|---|
| **1. Empathize** | Understand users' real needs (not just what they say) — set aside your assumptions | **Observation & shadowing** (natural environment, notice pain points users don't see); **Deep-dive interviews** (keep asking "why?" → latent needs); **Immersion** (live the user's journey); surveys, personas | Insights, empathy maps, personas | Students struggle to find exam schedules/deadlines |
| **2. Define** | Frame the exact problem clearly | Synthesize findings; analyze data; list pain points; write **POV statement** (human-centred, *not* business-focused); pose **"How Might We"** questions | POV + HMW | "Students need a faster, simpler way to access exam schedules & deadlines." / "HMW help busy office workers eat healthier at lunch?" |
| **3. Ideate** | Generate as many solutions as possible (quantity first) | Rules: **defer judgment, encourage wild ideas, build on others' ideas**. Techniques below | Pool → shortlist | Deadline dashboard, push notifications, AI chatbot, personalised timetable |
| **4. Prototype** | Make ideas tangible — *build to learn, not to impress* | **Low-fidelity**: sketches, paper models, wireframes, mock-ups, clickable prototypes. Motto: **"Fail fast to learn faster"** | Interactive model | Dashboard showing classes, deadlines, exam schedule, notifications |
| **5. Test** | Validate with real users | Usability testing, observe friction points, collect feedback, find bugs; *validate, don't sell* | Feedback → refine/redefine | Users ask for larger buttons, dark mode, calendar integration → modify |

**Ideation techniques (compare):**
| Technique | What | Pro |
|---|---|---|
| **Brainstorming** | Verbal, collaborative, out loud | High energy, immediate feedback, momentum |
| **Brainwriting** | Silent writing on sticky notes then share | Avoids groupthink/loud-voice bias; everyone heard |
| **Mind Mapping** | Central idea → branches → sub-branches | Organises ideas, shows relationships |
| **SCAMPER** | Substitute · Combine · Adapt · Modify/Magnify · Put to another use · Eliminate · Reverse | Modify existing products systematically |
| **Morphological Chart** | Table: functions × alternatives; pick one per row to build concepts | Systematically explores combinations |

**SCAMPER questions to remember:** Substitute (swap components?), Combine (merge with another service?), Adapt (tweak for another industry?), Modify/Magnify (make a feature 10× bigger?), Put to another use (how would a child/elder use it?), Eliminate (remove to simplify?), Reverse (flip the user journey?).

**Morphological chart example (Smart Teaching-Learning System):**
| Function | Alt 1 | Alt 2 | Alt 3 |
|---|---|---|---|
| User login | Email | Mobile OTP | College ID |
| Learning material | PDF | Video | Interactive content |
| Communication | Email | Chat | Discussion forum |
| Assessment | MCQ | Assignment | Online quiz |
| Feedback | Rating | Comments | Survey |

Concept 1 = Email + PDF + Email + MCQ + Rating; Concept 2 = OTP + Video + Chat + Online quiz + Survey; Concept 3 = College ID + Interactive + Forum + Assignment + Comments.
**Morphological chart vs mind map:** chart = table, *generates design alternatives* by combining options, common in product/system design; mind map = branches, *organises/explores ideas & shows relationships*, common in brainstorming.

**Iterative cycle (slide 21):** Insights (research reveals new need) → Redefine (adjust POV) → Iterate (pivot solution) → Refine (update prototypes) → Launch (implement with user confidence).

#### Diverge → Converge (Double-diamond thinking)
- **Divergent** = expand solution space ("what *could* we do?"), *quantity & variety*, needs **suspension of judgment** (Crazy 8s, structured brainstorming prevent premature critique).
- **Convergent** = narrow ("what *should* we do?"), *quality*, needs **explicit criteria** (dot voting, impact/effort matrix) — otherwise the loudest voice wins. You converge **multiple times** (dozens → shortlist → concept → prototype spec).

| Stage | Diverge | Converge |
|---|---|---|
| Empathize | Interview many users, observe multiple contexts | Synthesize themes; focused empathy maps/personas |
| Define | Write multiple HMW / problem framings | Select the single most actionable problem statement |
| Ideate | Generate as many ideas as possible | Evaluate, cluster, pick ideas to prototype |
| Prototype | Build multiple low-fi versions | Choose the one that best tests the riskiest assumption |
| Test | Broad feedback from diverse users | Decide to iterate, pivot or ship |

**How to write a 5 M / 10 M answer on stages (template):** for each stage → (1) name + one-line goal, (2) 2–3 activities, (3) a small example. Add a diagram of the loop and a one-line conclusion ("non-linear and iterative").

---

### 3.3 Human-Centred Software Design (HCD / HCSD)

**Easy explanation:** Don't make users adapt to your software — make the software adapt to humans (their behaviour, cognitive limits, emotions). Start from people, not technology.

**Definition (write this first):** *Human-Centred Software Design is an approach that prioritizes the needs, goals, abilities and experiences of the people who will use the software. Instead of starting with technology or features, it begins by understanding users and designing solutions that are useful, usable and accessible.* (shift from "What can we build?" → "What do users need, and how can we make it effortless?")

**4 Core Principles**
| Principle | Meaning |
|---|---|
| Focus on People | Design with deep empathy for real end-users — environment, daily frustrations, workflows |
| Fix the Root Problem | Don't just build what users *say*; observe to find the true underlying friction |
| Everything is a System | Software doesn't live in a vacuum — device, internet speed, surroundings, organisational processes shape experience |
| Iterate Continuously | First design won't be perfect — test early, fail fast, refine with feedback |

**6 Key characteristics:** User-focused · Empathy-driven · Iterative · Evidence-based · Accessible · Collaborative.

**5 Principles of HCSD (10 M answers):** (1) *Understand users* — interviews, surveys, observation, usability studies; (2) *Involve users throughout* — planning, design, development, testing; (3) *Focus on usability* — easy to learn, efficient, minimises errors; (4) *Iterative design*; (5) *Accessibility & inclusivity* — different abilities, backgrounds, languages, technical experience.

**Merits:** improves user satisfaction · increases productivity/efficiency · reduces errors & training · enhances accessibility/inclusiveness · lowers development cost (problems found early) · increases adoption & customer loyalty.

**Mini case (slides) — College Canteen:** *Personas:* students, faculty/staff, suppliers, cashiers, counter staff, cook, table cleaner. *Facility issues:* crowd, cleanliness. *Order-system issues:* payment queue, waiting for food, not knowing when food is ready → solution ideas: pre-order & online payment app, order-ready notification, crowd/time-slot display.

**Relating to PYQ phrases (general knowledge, not in the notes — useful for "why goal-directed = user-centred" & "phases of user-centric design"):** goal-directed design focuses on the user's *goals* (why they use the product) not just tasks/features, and goals are known only by studying users → so it is user-centred. Phases of user-centred design (ISO 9241-210 style): understand & specify context of use → specify user requirements → produce design solutions → evaluate against requirements → iterate. These map exactly onto Empathize/Define → Ideate/Prototype → Test.

---

### 3.4 Design vs Traditional Problem-Solving

**Comparison table (use 5–6 rows in exam):**
| Feature | Design Thinking | Traditional problem solving |
|---|---|---|
| Focus | User-centred | Technology-centred |
| Process | Iterative (non-linear) | Sequential (linear) |
| Approach | Understand users first | Implement requirements directly |
| Attitude to failure | Fail fast, learn fast | Failure = bad |
| Feedback | Continuous throughout | Mainly after development |
| Experimentation | Encouraged | Follows predefined plans |
| Problem framing | Reframe the problem | Accept problem as given |
| Team | Interdisciplinary | Usually only technical team |

**Intro line:** *"Design thinking differs from traditional problem solving in its fundamental approach. While traditional methods are technology-centred and sequential, design thinking is human-centred and iterative…"* then table.

**Problem-finding vs problem-solving (slide 65):** DT identifies the *right problem*; Agile/Scrum builds the solution incrementally. **Dual-Track Agile** = *Discovery Track* (DT) runs in parallel with *Delivery Track* (Agile sprints) to test assumptions before writing production code.

#### Wicked Problems (asked in 4 different papers — master this)
**Definition:** Problems that are complex, ambiguous, have no single correct solution and *change as you try to solve them* (term from Rittel & Webber).

**Characteristics:**
1. No definitive formulation — you can't state it fully until you've solved it.
2. No stopping rule — never fully "solved"; you stop when out of time/money.
3. Solutions are not right/wrong — only **better or worse** (good/bad).
4. Every wicked problem is unique (no precedent to copy).
5. Solving it changes the problem itself (each attempt has consequences; no trial-and-error without cost).
6. Many stakeholders with conflicting views.

**Example (from notes):** healthcare app for rural users — fix affordability → find literacy problem → then connectivity problem — the problem keeps evolving.
**UI/UX example:** designing an e-commerce / banking app for "all users" — user needs, devices, accessibility, business goals conflict and shift; improving checkout speed may reduce trust/security.

**Why DT handles them better:** it is iterative, empathy-driven, reframes the problem (HMW), prototypes cheaply to learn, uses diverge–converge, and doesn't assume the problem is fixed.

**Steps to resolve / take care (Dec 2022 Q3i, 2024 Q2Bii) — build from DT:** (1) Empathize with all stakeholders; (2) Define/reframe the problem (POV + HMW, accept it is provisional); (3) Ideate many alternatives; (4) Prototype small, cheap experiments; (5) Test with users; (6) Iterate/refine & accept "good enough" solution; (7) Collaborate across disciplines. *(Wicked-problem property list and mapping to the steps are standard theory; the notes only give the short version above.)*

---

### 3.5 Case Studies on Successful Design Thinking in Software

**Exam tip:** a scenario is given → *"apply design thinking to X"* → map all 5 stages with **specific** details, then a 1-line conclusion.

**Industry case studies from the slides (know 2–3 well):**
| Case | Empathize & Define | Ideate & Prototype | Test & Implement | Outcome |
|---|---|---|---|---|
| **Netflix** (DVD → streaming) | Observed living-room behaviour: *decision fatigue* & loading hassle | Visual preview reels, personalised thumbnails, continuous play | Extensive **A/B tests** → "Skip Intro", localized thumbnails, auto-previews | Less search time, high retention |
| **IBM Design Thinking** | Shadowed enterprise users; software too complex vs consumer apps (long onboarding, errors) | Replaced spec documents with "Playback" sessions & journey blueprints; early low-fi prototypes | **Carbon** design system with 2-week Agile sprints | Shorter cycles, less rework, unified UI |
| **Airbnb (2009)** | Founders met hosts in New York; bookings low because listing **photos were poor** (code was fine) | Non-scalable experiment: rented a camera, shot professional photos | Replaced photos on live site to test impact | Revenue doubled ($200→$400/week) |
| **American Family Insurance + IDEO – Moonrise** | Assumed need = budgeting app; interviews showed families budget tightly — real issue = **unexpected financial shocks** | On-demand micro-shift work platform with instant payout | Prototyped with **plain SMS** before building backend | Became startup Moonrise |

**Worked scenarios (stage-wise tables) — use as templates:**

**Smart Campus Navigator** — Empathize: interview first-years, visitors, faculty, security; find: students lost in 1st semester, classroom locations change, maps confusing, want Google-Maps-like. Define: *"New students need a simple, interactive campus navigation system because they waste time searching for classrooms/facilities."* Ideate: interactive map, GPS indoor/outdoor, QR codes at entrances, voice directions, AI chatbot, event navigation. Prototype: mobile app (map, building search, classroom locator, faculty-office finder, cafeteria/washroom locator, emergency contacts). Test: add wheelchair routes, walking time, classroom photos, live shuttle location → iterate. Benefits: fewer late arrivals, saves time, visitors find places.

**IRCTC** — Empathize: interview passengers, ticket collectors, station staff → seat availability confusion, confusing UI, slow booking at peak. Define: *"Passengers need a fast, reliable way to book tickets without confusion."* Ideate: real-time seat map, one-click booking, AI chatbot, offline mode, PNR push notifications. Prototype: low-fi wireframe — 3-step booking flow, simplified seat selection. Test: add regional language, show platform number, simplify cancellation → iterate.

**Uber / ride selection** — Empathize: observe booking, interview drivers & riders. Define: *"Users need to quickly select a ride type and see accurate arrival times."* Ideate: ride selection panel, price comparison, live tracking. Prototype: clickable mock-up of selection screen. Test: users confused by pricing → simplify and iterate.

**Student portal** — see 3.2. **Canteen** — see 3.3.

**10-mark answer structure:** Intro (2 lines) → 5 stages × (name + one-line definition + 2–3 scenario-specific activities + one concrete output) → Conclusion ("This iterative process ensures the final solution is user-validated and meets real needs rather than assumed ones.").

---

## 4. PYQ SOLUTIONS (Module-1-relevant only)

Grouped by topic. Answers are written the way they should appear in the exam (marks in brackets).

### A. Wicked Problems

**A1. Why are some problems called "wicked problems"? How can these be taken care of in designing? (10 M — July 2024, Q2B ii)**

*Wicked problems* are problems that are complex, ambiguous, have no single correct solution, and change as we try to solve them. Term introduced by Rittel & Webber for social/design problems that cannot be tackled with the linear "understand → analyse → solve" method used for "tame" problems (e.g., sorting a list).

**Why called wicked (characteristics):**
1. No definitive formulation — stakeholders define the problem differently.
2. No stopping rule — never fully solved; we stop when time/resources end.
3. Solutions are not right/wrong, only better or worse.
4. Every wicked problem is unique.
5. Every attempt at a solution changes the problem (solving affordability reveals literacy, then connectivity — e.g., a rural healthcare app).
6. Many stakeholders with conflicting needs.

**How to take care in design (Design Thinking approach):**
1. *Empathize* — study all stakeholders & context; observe, interview.
2. *Define* — frame a human-centred POV and HMW questions; keep the framing open to revision.
3. *Ideate* — generate many alternatives (diverge), shortlist with criteria (converge).
4. *Prototype* — cheap low-fi prototypes to learn, not to finalise.
5. *Test* — real users; feedback may redefine the problem.
6. *Iterate* — loop; settle for the best-available ("better") solution; use interdisciplinary teams.

Conclusion: DT suits wicked problems because it is iterative, empathy-driven and does not assume the problem is fixed.

**A2. What are wicked problems? Give an example w.r.t. UI/UX. (5 M — Nov 2023, Q1 v)** and **A3. Briefly explain how user interface design is a classic example of a wicked problem (≈2 M — 2021 Q1B 4)**

*Definition:* complex, ambiguous problems with no single correct solution that change while being solved. *Characteristics:* no definitive formulation; no stopping rule; better/worse not right/wrong; unique; solving changes the problem.
*Example (UI/UX):* designing a mobile banking app for all customers. Young users want speed, elderly want large text and simplicity, security teams want multi-step verification, business wants cross-selling. Making login faster reduces security; adding security hurts usability; new devices/regulations keep changing requirements — so there is no final "correct" design, only continuously improved versions.
*Why UI design is a classic wicked problem (A3):* the "problem" (what users need) cannot be fully specified up front; users, tasks, devices, and technologies vary and keep changing; every design decision changes user behaviour (so new requirements appear); there is never a final "done" UI — only better or worse ones validated by user testing.

**A4. What are wicked problems? Illustrate the steps to resolve them. (10 M — Dec 2022, Q3 i)**
Answer = definition + characteristics + example (from A1/A2) + the 6 steps (Empathize → Define → Ideate → Prototype → Test → Iterate) each with a rural-healthcare-app illustration: interview villagers/ASHA workers → POV "Rural patients need affordable, low-literacy access to doctors" → ideas: voice-based app, SMS, local-language video, kiosks → paper/wireframe prototype → pilot in one village → results show connectivity issue → redefine → offline mode & loop again. Draw the 5-stage loop diagram.

### B. Design Thinking / Design-process stages applied to a scenario

**B1. Explain the six stages of design process with reference to "Designing a remote control for air-conditioner". (10 M — July 2024, Q2A OR)**
*Assumption:* the design process stages follow the Design Thinking framework (Empathize, Define, Ideate, Prototype, Test) plus a final Implement/Launch stage = six stages.

Intro: *Design thinking is a human-centred iterative approach. Applying it to an AC remote involves:*

| # | Stage | Activities (specific) | Output |
|---|---|---|---|
| 1 | **Empathize/Research** — understand the user | Observe people using remotes in homes/hotels; interview elderly, children, hostel students; find: too many tiny buttons, unclear icons, can't use in dark, lost remote | Pain-point list, persona |
| 2 | **Define** — frame problem | Synthesize findings. POV: *"Users need a simple, easy-to-read way to set temperature and mode without confusion."* HMW: *How might we make the remote usable in the dark/for the elderly?* | POV/HMW |
| 3 | **Ideate** — many ideas | Brainstorm: large-display remote, backlit buttons, voice control, mobile-app remote, one-touch "sleep/eco" mode, magnet holder | Shortlist (using criteria: cost, usability, feasibility) |
| 4 | **Prototype** | Paper/cardboard model & wireframe of button layout; clay/3-D model; clickable app mock-up | Low-fi prototype |
| 5 | **Test** | Users operate prototype; watch errors/time to set temperature; feedback: bigger temp display, colour-coded mode buttons, braille dot | Feedback → iterate |
| 6 | **Implement/Launch** | Finalise design, manufacture, pilot release, monitor reviews | Product |

Conclusion: the loop is iterative; feedback may send us back to any stage, ensuring the remote is user-validated. *(Draw the loop diagram.)*

**B2. Considering the six stages of UX design process, design an interface for a ride-booking application. Explain how each stage is considered; write assumptions and constraints clearly. (10 M — Nov-Dec 2021, Q4a)**

*Assumptions:* users have smartphones with GPS and internet; payment via UPI/card/cash; drivers' app is separate. *Constraints:* patchy network, low-end devices, time-critical booking, safety/privacy of location, multiple languages.

| Stage | Application to ride booking |
|---|---|
| **Empathize** | Observe how people book rides at stations/offices; interview riders (students, office-goers, elderly) and drivers → pain points: unclear arrival time, price surge confusion, safety, cancellations |
| **Define** | POV: *"Users need to quickly select a ride type and see accurate arrival times and fare."* HMW make price transparent? |
| **Ideate** | Ride-type selection panel, price comparison, live tracking, share-trip for safety, SOS button, saved places, multi-language, voice booking |
| **Prototype** | Low-fi wireframe: Home (pickup/drop) → Select ride (type, ETA, fare) → Confirm → Track; then clickable mock-up |
| **Test** | Users test; confusion over pricing → show fare breakdown; add driver photo/vehicle number → refine |
| **Implement** | Build interface components (map, bottom-sheet ride list), release in beta city, monitor metrics, iterate |

Conclusion: iterative process ensures the interface meets real needs rather than assumed ones.

**B3. "Design Thinking" — short note (5 M — Dec 2022, Q5 vi)**
Use the short-note answer from 3.1 + a 5-stage diagram + 1-line example (student portal / campus navigator).

**B4. Justify the problem formulation step in enhancing user experience. (5 M — July 2024, Q1 ii)**
Problem formulation = the **Define** stage. Justification points:
1. Frames the *right* problem — otherwise a perfect solution to the wrong problem wastes effort.
2. Converts raw research into a human-centred POV: *"Students need a faster way to access exam schedules"* — keeps the focus on users, not business/technology.
3. HMW questions open the solution space and prevent premature solutions.
4. Aligns the team, gives a measurable target (design criteria) for ideation and testing.
5. Saves cost — mistakes in problem definition caught early rather than after coding.
6. Directly improves UX because every feature is traceable to a real user need, avoiding clutter and rework.
Example: Campus navigator — vague "students are late" becomes "New students need a simple interactive campus navigation system."

**B5. Justify the need to know the user before designing a system. (≈2 M — Nov-Dec 2021, Q1B 7)** (Empathize stage)
Users' goals, abilities, environment and mental models differ from designers'; designers' assumptions are often wrong; real needs are *latent* — found only by observation & interview ("what they do, say, feel"). Knowing users prevents building unwanted features, reduces errors/training/rework cost, and increases adoption and satisfaction (HCD merits).

### C. Human/User-Centred Design

**C1. Infer why goal-directed design is referred to as "User-Centred Design" (5 M) and discuss the different phases for achieving user-centric design (5 M). (Nov 2023, Q2B i)**
(a) Goal-directed design focuses on *why* users use the product (their goals — e.g., "get to class on time", not "use a map") rather than on features/technology. Goals can be known only by studying real users (observation, interviews, personas), and the design is then validated against those goals. Since the user's needs, abilities and context drive every decision, it is user-centred (human-centred: "What do people actually need?" not "What can we build?"). Core principles: Focus on people; fix the root problem; everything is a system; iterate continuously.
(b) Phases: (1) **Understand users & context** (Empathize — interviews, observation, surveys); (2) **Specify requirements** (Define — POV, HMW, design criteria); (3) **Create design solutions** (Ideate + Prototype); (4) **Evaluate with users** (Test — usability testing); (5) **Iterate & implement** until goals are met; users involved at all phases; accessibility and usability considered throughout. Diagram: loop of the 4–5 phases.

**C2. Justify the need of user-centric design for enhancing user experience (≈2 M — 2021 Q1B 2).**
Software must fit the people using it; UCD (i) improves satisfaction and usability, (ii) reduces errors and training, (iii) increases productivity and accessibility, (iv) catches problems early (lower cost), (v) raises adoption and loyalty.

**C3. MCQ/fill-in: "User-centered design (UCD) is ____ ." (1 M, 2021 Q1A 3)**
*An iterative design process/philosophy in which designers focus on the users and their needs at each phase of design, involving users throughout design and testing, so the product is useful, usable and accessible.*

### D. Items from the PYQs I judged only partially in-module (brief handling)

| PYQ | Why borderline | What to write |
|---|---|---|
| "Great questions lead to great design" — explain/map to user research & journey (5 M Dec 2022 Q1 iii; 10 M Nov 2023 Q2A OR) | Links to Empathize (interviews → asking "why", HMW) + Journey Mapping (tool #2) | Good questions in Empathize (open "why?" questions) uncover latent needs; in Define they become HMW questions; they frame the right problem → so the design solves the right thing. Map journey with stages, touchpoints, emotions (highs/lows) for e.g. booking a train ticket (IRCTC). Full user-research/journey mapping detail is Module 2. |
| "Importance of Research Stage in designing with examples" (5 M, 2024) | = Empathize stage | Research reveals real needs, prevents assumptions, reduces cost (e.g., Airbnb founders discovered poor photos by meeting hosts; Moonrise found real issue was financial shocks). |
| 5S model (2021, 2024) | UX-planes model, not in this syllabus | Skip for Module 1 |

> **Not in provided scans:** the Exam Reference says IRCTC was a "direct PYQ"; I did not see an IRCTC question in the papers provided, only the ride-booking one. IRCTC template is still included in 3.5 because it is a likely scenario.

---

## 5. LAST-MINUTE REVISION CHEAT-SHEET
- DT stages: **E-D-I-P-T**, non-linear. Slogans: "Fail fast to learn faster"; "Quantity over quality"; "Validate, don't sell".
- 3 spaces: Inspiration · Ideation · Implementation. Inspiration = DO / SAY / FEEL + latent needs + extremes.
- 10 tools: Visualization, Journey Mapping, Value Chain, Mind Mapping | Brainstorming, Concept Development | Assumption Testing, Rapid Prototyping | Customer Co-Creation, Learning Launch → mapped to What is / What if / What wows / What works.
- 4 PMA: Design Brief (North Star) · Design Criteria · Napkin Pitch (3–5 concepts) · Learning Guide (2–3 concepts).
- HCD 4 principles: People · Root problem · System · Iterate.
- Wicked problem: no definitive formulation · no stopping rule · better/worse · unique · changes as solved.
- Any "apply DT to X" → 5 stages × (name + activities + output) + diagram + conclusion.
