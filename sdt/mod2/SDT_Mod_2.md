# SDT_Mod_2 — Empathise & Define (Software Design Thinking, 216U01E701)

> **Sources used:** `SDT Module 2_Empathise and Define_V4` (60 slides; the 2 PDFs have identical content), the `PPts-with-examples/` folder (user-research deck, DT-in-SE notes, DT case studies, journey-map and storyboard notes, campus-navigation personas), and all PYQ scans in `../question_papers_all_time/` (10 screenshots plus the Jul–Nov 2025 PDF).
> **PYQ labels used below:**
> **[25]** Jul–Nov 2025 · **[24]** Jul–Nov 2024 · **[23]** Nov 2023 · **[22]** Dec 2022 · **[21]** Nov–Dec 2021 (50-marks paper).
> The May 2023 *Software Architecture & Design Thinking* paper (connectors, C2 style, ADL…) belongs to a different course and is **excluded**.
> No numericals exist in this module. "Solving" means case-based answers: empathy maps, personas, POV and HMW statements, journey maps and design goals.

---

## 1. TOPIC MAP

```
MODULE 2 : EMPATHISE & DEFINE (9 hrs, CO1)
│
├── 2.1 Understanding user needs, pain points & requirements
│   ├── User Needs
│   │   ├── Explicit vs implicit vs latent needs
│   │   ├── Needs vs wants (surface requests vs underlying need)
│   │   ├── Emotional drivers (secure, valued, efficient)
│   │   ├── Extreme users (power users + novices)
│   │   ├── Unstated needs → workarounds / hacks
│   │   ├── Context (physical, social, cultural)
│   │   └── Real-user examples (agriculture, weather, healthcare)
│   ├── Pain Points
│   │   ├── Types: friction · financial · process bottleneck · emotional stress ·
│   │   │          accessibility · information gap · trust & safety · cognitive load
│   │   ├── Sources: negative feedback, support logs, reviews
│   │   ├── Severity × frequency prioritisation
│   │   └── Root-cause analysis (5 Whys)
│   └── Requirements
│       ├── Functional / Non-functional (performance, usability, accessibility, security)
│       ├── Must-have vs nice-to-have (prioritisation)
│       ├── User stories ("As a… I want… so that…")
│       ├── Success metrics, constraints & guardrails, contextual requirements
│       ├── Accessibility compliance (WCAG) · MVS · stakeholder alignment
│       └── Requirement tracing · scope control · validation with users
│
├── 2.2 Conducting user research
│   ├── What / why / importance / types (interview, survey, observation,
│   │                                  focus group, contextual inquiry, diary study)
│   ├── Interviews  (qualitative, 1-to-1)
│   │   └── Tips: stories > opinions · 5 Whys · verbatim quotes · silence/non-verbal · HMW
│   ├── Surveys  (quantitative, many users)
│   │   ├── Question types: MCQ · rating · Likert · open · yes/no
│   │   └── Tips: closed+open mix · segment · short (5-10 Q) · cross-reference · percentages
│   ├── Observation  (behavioural)
│   │   ├── Types: direct · participant · contextual · shadowing
│   │   └── Tips: beginner's mindset · workarounds · context · AEIOU (Activities,
│   │             Environments, Interactions, Objects, Users) · contradictions
│   ├── Qualitative vs Quantitative · comparison table
│   └── Best practices (consent, privacy, unbiased) · challenges (bias, response, time)
│
├── 2.3 Creating empathy maps & personas
│   ├── Affinity mapping (synthesising raw data into themes)
│   ├── Empathy map  (4 quadrants: Says · Thinks · Does · Feels; open-ended; bottom-up)
│   │   └── Extension: Pains & Gains
│   ├── Personas  (archetypes; types of users/personas; template; steps)
│   └── Supporting tools: Journey map · Storyboard (journey ≠ storyboard)
│
├── 2.4 Problem framing & POV statements
│   ├── Why framing matters (right problem, saves cost, aligns team)
│   ├── 5 steps: Gather insights → Map system → Question brief → POV → Generative Qs
│   ├── POV = [User] needs [Need] because [Insight]
│   └── POV → "How Might We" (HMW) questions
│
└── 2.5 Translating requirements → design goals
    ├── 10-step process (gather → analyse → needs → prioritise → define problem →
    │                    convert to goals → SMART → align business → validate → refine)
    ├── Requirement → Design-goal examples
    └── Persona-wise requirement/goal tables (hotel-booking case)
```

---

## 2. TOPIC-WISE QUESTION TYPES (with PYQ evidence)

**Legend:** ★ = has appeared in a PYQ (year in brackets). ✔ = syllabus-valid and likely, but not yet asked. — = not applicable.
The **Numerical** column is "—" for every topic: no numericals have ever been asked.

| Topic | Theory / short note (5M) | Long answer / explain-process (10M) | Compare / differentiate | Case-based / apply to a scenario | Diagram / template | MCQ / objective |
|---|---|---|---|---|---|---|
| **2.1 User needs / types of users** | ★ types of users [25]; ★ user categorisation [24]; ★ need to know the user [21] | ✔ | ✔ needs vs wants | ✔ | — | ★ non-functional requirement [21] |
| **2.1 Pain points** | ✔ | ✔ | ✔ | ✔ (Alex persona [23] needs pain points) | — | — |
| **2.1 Requirements (FR/NFR, user stories)** | ✔ | ✔ | ✔ FR vs NFR | ✔ (banking app assumptions & constraints [21]) | — | ★ [21] |
| **2.2 User research (goals, importance, ways, tools, methods)** | ★ goals of user research [24], [21]; ★ tools for user research [22]; ★ "great questions lead to great design" [22] | ★ ways of conducting user research [24]; ★ importance of research stage [24]; ★ user research methodologies [22]; ★ great questions → user research & journey [23] | ★ qualitative vs quantitative [25], [21] | ✔ interview/survey plan for an app | — | — |
| **2.3 Empathy map** | ★ importance [24]; ★ usefulness [25] | ★ process of building [22] | — | ★ empathy map for Alex [23]; ★ TV buyer [22]; ★ food-ordering 4 quadrants [21] | ★ (quadrant diagram expected every time) | — |
| **2.3 Personas** | ★ importance of "persona" [24]; ★ persona types & purpose [25] | ★ creating personas [22]; ★ constructing persona steps [25] | ✔ persona vs user | ★ persona for Alex [23] | ★ (persona card) | ★ "a user persona is __" [21] |
| **2.3 Journey map / storyboard (supporting)** | ★ storyboard justify [22]; ★ storyboard vs wireframe [25] | ★ user flows / journey [23]; ★ UX stories [23] | ★ journey map vs storyboard (material) ✔ | ✔ | ★ journey table / flow | ★ wireframe/storyboard static-dynamic [21] |
| **2.4 Problem framing / POV / HMW** | ★ problem formulation step [24] | ✔ POV + HMW | ✔ problem statement vs POV | ✔ write POV + HMW for a scenario (very likely, since the slides carry a worked hotel example) | — | ✔ |
| **2.5 Requirements → design goals** | ✔ | ✔ steps / SMART | ✔ requirement vs design goal | ✔ table for a persona | ✔ table | ★ [21] (NFR) |

**Exam pattern in one line:**
- Q1 (5M short): types of users, persona, empathy map, qual vs quant, goals of research, storyboard.
- Q2/Q3 (10M): empathy map or persona for a given scenario (Alex, TV, food app) and user-research methods.
- Highest-frequency items: **Empathy map (5 of 5 papers)**, **Persona (5 of 5)**, **User research (5 of 5)**.
- **Never asked yet but in the syllabus and slides: POV, HMW, requirements → design goals, SMART, pain-point classification.** These are the likely new questions.

---

## 3. TOPIC-BY-TOPIC DETAILED BREAKDOWN

> Where the Empathise and Define stages sit: Design Thinking runs Empathise → Define → Ideate → Prototype → Test. **Empathise** means understanding the users. **Define** means turning what you learned into one clear problem. Module 2 covers these first two stages.

### 3.1 Understanding user needs, pain points & requirements  *(slides 3–19)*

#### A. User needs
**Short note (5M):**
A user need is what *drives, motivates and fulfils* a user: the underlying goal behind what they ask for. Designers look beneath the feature request to the need.

- **Types of needs:**
  - *Explicit*: the user says it ("I want to track my order").
  - *Implicit*: the user doesn't say it, but you can see it by observing ("keeps screenshotting the tracking page").
  - *Latent*: the user can't articulate it because no solution has existed ("Uber before Uber").
- **Needs vs wants:** a want is a surface feature request ("add a dark mode button"). A need is the fundamental reason ("reduce eye strain at night"). Filter wants to find needs.
- **Emotional drivers:** look beyond tasks to feelings (feeling secure, valued, efficient).
- **Extreme users:** interview power users and complete novices. They reveal edge-case needs that average users adapt to.
- **Unstated needs and workarounds:** hacks a user invents (sticky notes, screenshots) signal an unmet need.
- **Context:** physical, social and cultural environment shapes expectations.
- **How to discover:**
  - open-ended in-depth interviews
  - observing natural behaviour (shadowing)
  - empathy maps
  - experience/journey mapping
  - affinity mapping of notes into themes
  - personas
- **Examples (from slides):**
  - Agriculture → farmers, wholesalers
  - Weather → sailors, farmers, the common man
  - Healthcare → doctors, hospital staff, patients

**Types of users (asked in [25], [24] — theory 5M):**
Classify users to design for each group properly:
1. **Primary users** use the product directly every day (customer using a banking app).
2. **Secondary users** use it occasionally or through someone else (bank staff, an agent booking for a client).
3. **Tertiary users** are affected by it or influence its purchase (management, family members, regulators).
4. **By skill:** novice, intermediate, expert (power) users.
5. **Extreme users:** the very expert and the very novice, as covered above.

Why it matters: each group has different goals, abilities and context, so the design must serve all of them. This is also the "relevance of user categorisation" asked in [24].

**Need to know the user before designing (7th Q in [21], 5M):**
- Design is for users, not designers.
- Knowing them avoids building the wrong product.
- It reduces rework and cost.
- It improves usability and satisfaction.
- It exposes real pain points and context.
- It gives a shared vision to the team.
- Example: a bank app for senior citizens needs large fonts and simple flows, which only research reveals.

#### B. Pain points
**Short note:** pain points are specific frustrations, obstacles and friction users experience. Finding them tells you what to fix.

| Type | Meaning | Example |
|---|---|---|
| Friction | Where users get stuck, confused or delayed | Too many form fields |
| Financial | Existing solution costs too much money, time or resources | Hidden fees |
| Process / bottleneck | Structural flaws that cause delay or error | Manual approval step |
| Emotional stress | Anxiety, doubt, overload, fatigue | "Did my payment go through?" |
| Accessibility | Physical, technical or cognitive barriers | No screen-reader support |
| Information gap | Missing information needed to decide | No total price shown |
| Trust and safety | User feels vulnerable or unsafe | Unclear data usage |
| Cognitive load | Complex interface → mental fatigue | Cluttered dashboard |

- **Sources:** customer-support logs, bad reviews, survey complaints, observation of workarounds.
- **Prioritise** by *severity × frequency*.
- **Root-cause analysis:** use **5 Whys** to separate the symptom from the true cause.
  - Example: "App is slow" → why? Big images → why? No compression → why? No guideline → fix the guideline.
- **Boundaries:** filter irrelevant complaints and keep high-impact ones.
- **Pain points feed POV statements.**

#### C. Requirements
**Short note:** requirements translate empathetic insights into clear, actionable criteria for the solution.

- **Functional requirements (FR):** what the system must *do* (book a room, send a receipt).
- **Non-functional requirements (NFR):** how well it must do it: performance, usability, accessibility, security, and the look-and-feel of the interface. This is why the [21] MCQ options (order of items, fonts/decoration, alignment, white space) count as non-functional.
- **Prioritise:** must-have vs nice-to-have (core vs secondary enhancements).
- **User stories:** "As a [user], I want to [action] so that [benefit]." Example: "As a business traveller, I want one-click rebooking so that I save time when flights are delayed."
- **Measurable success metrics:** task-completion time, error reduction.
- **Constraints and guardrails:** technical, budget, regulatory.
- **Contextual requirements:** offline mode, hands-free use.
- **Accessibility compliance:** WCAG, ergonomics.
- **Design principles:** e.g. "simplicity over feature density".
- **Minimum Viable Solution (MVS):** the essential features needed to test an idea in the next stage.
- **Stakeholder alignment:** balance user needs with business viability and technical feasibility.
- **Traceability:** every requirement traces back to a user need or pain point.
- **Scope control:** strict boundaries prevent scope creep.
- **Validate** the criteria with users again.

**Likely case question — "Banking app: write assumptions and constraints" ([21] Q3):**
- *Assumptions:* users have smartphones and internet; they are registered customers; KYC is done; they are of mixed digital literacy.
- *Constraints:* RBI/regulatory compliance; two-factor authentication; session time-outs; must work on low bandwidth; budget and timeline limits; accessibility for the elderly.

---

### 3.2 Conducting user research  *(slides 21–34 + user-research deck)*

**Definition (5M):** user research is the process of systematically understanding users, their needs, behaviours and pain points, to support better product design.

**Importance:**
- reduces development risk
- improves usability
- saves cost
- increases customer satisfaction
- supports informed decisions
- replaces assumptions with evidence

**Goals of user research (asked [24], [21]):**
1. Understand who the users are: demographics, skills, context.
2. Understand their needs, goals and motivations.
3. Discover pain points and unmet needs.
4. Understand current behaviour and workarounds.
5. Validate or reject assumptions.
6. Gather evidence to define the problem statement.
7. Measure satisfaction and track improvement.
8. Support design decisions and prioritisation.

**Ways / methodologies (asked [24], [22]):** interviews, surveys/questionnaires, observation, focus groups, contextual inquiry, diary studies (plus usability testing, card sorting and analytics for later stages).

**Tools for user research ([22] Q1 ii):**
- Interview guide / recorder / transcript tools
- Survey tools (Google Forms, SurveyMonkey, Typeform)
- Observation checklist / field notes / video recording
- Analytics and heat-maps
- Affinity diagram / sticky notes / Miro
- Empathy map and persona templates
- Screen recorders / usability tools

#### i) Interviews (qualitative)
- A one-to-one conversation to surface personal stories, emotions and root motivations.
- Ask **open-ended** questions ("What difficulties do you face?"). Avoid yes/no questions.
- Listen actively, record, then analyse.
- **Steps:** define objectives → select participants → prepare questions → conduct → record → analyse.
- **Five practice tips (slides):**
  1. Stories over opinions: ask about the past ("Tell me about the last time…").
  2. Ask "Why?" (5 Whys) to reach the emotional core.
  3. Capture verbatim quotes and cluster them in an empathy map.
  4. Embrace silence and non-verbal cues (body language, hesitation).
  5. Reframe findings into HMW questions.
- **Pros:** rich information, emotions, flexible. **Cons:** time-consuming, small sample, interviewer bias.
- **Sample questions (Smart Teaching-Learning app):**
  - How do you access study material?
  - What difficulties do you face?
  - Which features would help you?

#### ii) Surveys (quantitative)
- A structured questionnaire for many users. It validates qualitative findings, measures prevalence and spots trends.
- **Question types:** multiple choice, rating scale, Likert, open-ended, yes/no.
- **Pros:** large sample, fast, low cost, numbers/charts. **Cons:** low response, shallow depth, can't ask "why" in the moment.
- **Five tips:**
  1. Balance closed and open questions.
  2. Target the right segment (match your persona).
  3. Keep it short (5–10 questions).
  4. Cross-reference statistics with interview stories ("X% of respondents…").
  5. Use percentages and rankings to scope the problem.
- **Good survey design:** simple questions, avoid bias, one idea per question, logical order, pilot test.

#### iii) Observation (behavioural)
- Watch users in their real environment. It reveals the gap between what people **say** and what they **do**.
- **Types:** direct, participant, contextual, shadowing.
- **Five tips:**
  1. Beginner's mindset (no assumptions).
  2. Document workarounds and hacks.
  3. Capture context (lighting, distractions, network).
  4. Use a structured framework, **AEIOU**: Activities, Environments, Interactions, Objects, Users.
  5. Synthesise contradictions between said and observed behaviour. These form the basis of POV statements.
- **Checklist:** user actions, time taken, errors, frustrations, environment, interaction patterns.

#### Comparison table (from deck)
| Method | Participants | Data | Cost | Depth |
|---|---|---|---|---|
| Interview | Few | Qualitative | Medium | High |
| Survey | Many | Quantitative | Low | Medium |
| Observation | Few | Behavioural | Medium | High |

**Qualitative vs Quantitative (asked [25], [21]):**
| Basis | Qualitative | Quantitative |
|---|---|---|
| Answers | *Why / how* | *How many / how much* |
| Data | Words, quotes, behaviours, emotions | Numbers, percentages, statistics |
| Sample | Small (5–15) | Large (100+) |
| Methods | Interviews, observation, focus groups, diary | Surveys, analytics, A/B tests |
| Analysis | Themes, affinity mapping, empathy map | Statistical, charts |
| Strength | Depth and insight | Generalisable, validates |
| Weakness | Not generalisable, subjective | Lacks context and the reason |
| UX use | Discover problems and needs | Measure prevalence and prioritise |

Best practice: **combine both** (triangulation).

**Best practices and challenges:**
- *Practices:* informed consent, privacy, unbiased questions, active listening, accurate recording, thank participants.
- *Challenges:* low survey response, interviewer bias, observer bias (Hawthorne effect), limited participants, time constraints.

---

### 3.3 Creating empathy maps & personas  *(slides 36, plus the persona docs)*

#### A. Affinity mapping (bridge)
Write each observation or quote on a sticky note → group similar ones → name each cluster as a theme → themes reveal core human needs.

#### B. Empathy map
**Definition (5M):** a collaborative visual tool that captures what a user **says, thinks, does and feels**. This builds a shared, holistic understanding of the user. It has **4 quadrants**, is **open-ended**, and is built **bottom-up** from research data. It is useful for creating personas.

**Diagram to draw in the exam:**
```
                     ┌──────────────────────────┐
                     │      USER (name/role)    │
        ┌────────────┴────────────┬─────────────┴────────────┐
        │         SAYS            │          THINKS          │
        │ (quotes, spoken words)  │ (beliefs, worries,       │
        │                         │  unspoken thoughts)      │
        ├─────────────────────────┼──────────────────────────┤
        │         DOES            │          FEELS           │
        │ (actions, behaviours,   │ (emotions: anxious,      │
        │  workarounds)           │  frustrated, happy)      │
        └─────────────────────────┴──────────────────────────┘
        (Optional extension below:  PAINS | GAINS)
```

**Why it is important / useful (asked [24], [25], 5M):**
- builds empathy and a shared understanding across the team
- moves the team from assumptions to evidence
- reveals pain points and unmet needs
- separates what people say from what they do
- helps prioritise features
- is quick and cheap to create
- is the input for personas and POV statements
- helps the team stay user-centred

**Process of building an empathy map (asked [22], 10M):**
1. Define scope and the user/persona to map, and the goal.
2. Gather research (interviews, surveys, observation).
3. Draw the 4 quadrants (Says, Thinks, Does, Feels) with the user in the centre.
4. Write observations on sticky notes (one idea per note, using verbatim quotes) and place them in the right quadrant.
5. Cluster and find patterns/contradictions (e.g. says "easy" but struggles).
6. Add Pains and Gains (fears/frustrations vs wants/successes).
7. Derive insights and needs.
8. Validate with real users and iterate. Use the result for the persona and POV.

#### C. User persona
**Definition (also the [21] fill-in-the-blank):** a *persona is a fictional but research-based archetype that represents a group of real users*, with their goals, needs, behaviours and frustrations.

**Importance (asked [24], 5M):**
- keeps the team focused on real user needs
- avoids designing for yourself ("I am the user" fallacy)
- gives a shared language and speeds up decisions
- helps prioritise features
- builds empathy
- helps in testing and communication
- supports inclusive design (covers diverse users)

**Contents of a persona card:** name, photo, age, occupation/background, devices, **goals**, **frustrations/pain points**, **needs**, behaviours, technology comfort, a **quote**.

**Persona types (asked [25], purpose of any two):**
- **Primary persona:** the main target user. The design is optimised for them.
- **Secondary persona:** has additional needs that the design should accommodate without compromising the primary.
- **Negative (anti) persona:** the user you are *not* designing for. It prevents scope creep and wrong features.
- **Customer / purchaser persona:** the one who pays or decides (e.g. an institution) and is not necessarily the end user.
- **Stakeholder persona:** an internal or supporting role.
- **Served persona:** affected indirectly (e.g. a patient where the doctor is the user).

**Steps in constructing a persona (asked [25], [22], 10M):**
1. Conduct user research (interviews, surveys, observation).
2. Analyse data and find patterns (affinity mapping, empathy maps).
3. Group users into segments by shared goals and behaviours.
4. Identify the key attributes (goals, needs, pain points, behaviours, context).
5. Create a profile for each segment: name, photo, demographics, background, quote.
6. Prioritise: choose the primary, secondary and negative persona.
7. Write a short scenario / "day in the life".
8. Share with the team, validate with real users, and refresh regularly.

**Worked persona example (from the campus-navigation material):**
| Persona | Goals | Pain points | Needs |
|---|---|---|---|
| Riya, 18, first-year | Reach classes on time | Gets lost; confusing maps | GPS navigation, classroom search, reminders |
| Aditya, 21, senior | Find event venues fast | Venue changes; outdated maps | Live map, room search, route optimisation |
| Ahmed, 20, exchange student | Navigate independently | Language barrier, unfamiliar signs | Multilingual, voice guidance, landmarks |
| Sneha, 19, wheelchair user | Move safely between buildings | No accessibility info | Accessible routes, elevator/ramp info |

#### D. Supporting tools — Journey map & Storyboard
- **User journey map:** a table of the user's *complete experience* across stages.
  - Columns are the stages (Discovery → Selection → Checkout → Fulfilment → Post-purchase).
  - Rows are *User action · Touchpoint · Thoughts · Emotion (curve) · Pain point · Opportunity*.
  - Base it on research, watch hand-offs between digital and physical, and involve a cross-functional team.
  - Dips in emotion = pain points → each becomes a backlog item.
- **Storyboard:** a *visual sequence of scenes* (like comic frames) showing how a user interacts with a product or solves a problem. It is narrative and emotional, and good for communicating and testing the idea.
  - Example flow: Student has difficulty → opens app → logs in → app finds weak subject → recommends material → studies → quiz → feedback.
- **Difference:** a storyboard is *visual narrative* of one scenario (what happens, in pictures). A journey map is *analytical grid* (actions, thoughts, emotions, pain points, opportunities) over time.
- **User flow / flowchart:** the step-by-step paths a user takes through the interface (screens and decisions). It benefits the designer by showing logic, dead-ends and the shortest path.

---

### 3.4 Problem framing & POV statements  *(slides 38–51)*

**Why frame the problem (also answers "problem formulation step", [24]):**
A poorly framed problem leads to building the *wrong product*, even if the design itself is flawless.
- **Stops wrong solutions:** you fix the cause rather than the symptom.
- **Saves time and money:** limits scope creep and rework.
- **Aligns the team:** gives a shared vision and goal.
- **Drives innovation:** turns vague frustrations into actionable opportunities.

**5 steps of problem framing:**
1. **Gather user insights:** interviews, observation, empathy maps (what users say, do, think, feel).
2. **Map the system:** trace journeys and touchpoints, find bottlenecks, layer cultural, technical and financial context.
3. **Question the initial brief:** 5 Whys, find the root cause, check whether "known facts" are backed by data.
4. **Write a POV statement.**
5. **Launch generative questions:** flip the POV into HMW questions, check scope (narrow enough to focus, broad enough for creativity) and pick the best 2–3.

**POV statement (definition, 5M):**
A POV statement is a clear, concise problem statement focused on **one specific user**: what they need and the insight that explains why. It gives the team focus, is precise for ideation, and is the source of HMW questions.

**Formula: `[User] needs [Need] because [Insight].`**
- **User:** a specific, researched persona. It is not "everyone".
- **Need:** what the user is trying to achieve, expressed as a **verb** (action), not a noun (a feature).
- **Insight:** the *why*. A deeper, often surprising truth drawn from interviews and observation (behaviour, emotion, constraints).

**Good vs bad POV:**
- ✗ "Users need a mobile app for booking" (solution baked in, generic user).
- ✓ "A frequent business traveller who arrives late at night needs to confirm a room in one tap because flight delays leave them exhausted and anxious about finding a safe place."

**Worked case — Online hotel booking (slides 44–47).** Personas: business travellers, budget travellers, professional planner agents, hotel owners.
| User | Need | Insight |
|---|---|---|
| Business traveller | Rapidly reserve rooms near work venues with expense-ready receipts and flexible cancellation | Uncontrollable meeting delays make speed and friction-free changes more critical than price or luxury |
| Budget traveller | Know the total cost with amenities | Hidden costs aren't included, so the final price is hard to find |
| Professional agent | Know options, availability and commission | Wants better hotels at reasonable rates while still earning commission |

POV (budget): *"A budget-conscious solo traveller needs a clear, transparent way to see the total final price upfront, because hidden fees and checkout charges make them feel deceived and destroy trust in the platform."*

**POV → HMW (How Might We) questions:**
HMW questions are open, optimistic, solution-free questions. They are built from the POV and launch brainstorming. Format: *"How might we [achieve the need] for [user] so that [benefit]?"*
- Business travellers: HMW streamline booking into a one-click experience? HMW simplify receipts and expense reporting? HMW guarantee last-minute availability and flexible cancellation?
- Budget travellers: HMW display all fees and taxes upfront (no checkout shock)? HMW help them compare and lock in the best value? HMW highlight low-cost amenities?
- Agents: HMW build a dashboard for bulk bookings? HMW give instant client-shareable quotes? HMW automate commission tracking?
- Hotel owners: HMW provide tools to manage live inventory and dynamic pricing? HMW help them stand out with verified reviews? HMW minimise checkout drop-offs?

*Good HMW check:* not too broad ("HMW fix travel?") and not too narrow (it should not embed a solution, e.g. "HMW add a button").

---

### 3.5 Translating requirements into design goals  *(slides 53–60)*

**Definition (5M):** raw, unstructured inputs (user feedback, business targets, technical constraints, empathy research) are converted into clear, actionable objectives that direct the design process.

**10-step process:**
1. **Gather requirements:** from user needs, stakeholders and the business, via interviews, surveys and observation.
2. **Analyse** the requirements: problems, expectations, constraints.
3. **Identify user needs:** separate essential from optional.
4. **Prioritise:** by importance, user impact, feasibility, cost and objectives.
5. **Define the problem clearly:** write the problem statement/POV *before* goals.
6. **Convert needs into goals:** each requirement becomes a design objective.
   - *Requirement:* "Users find the app difficult to navigate." → *Design goal:* "Create a simple and intuitive navigation system."
7. **Make goals SMART:** **S**pecific, **M**easurable, **A**chievable, **R**elevant, **T**ime-bound.
   - e.g. "Reduce hotel-booking time to under 3 minutes for 90% of users within the next release."
8. **Align with business objectives:** customer satisfaction, efficiency, cost.
9. **Validate** with users, stakeholders and the team.
10. **Review and refine** using feedback and prototype testing.

**Persona → Requirements → Design goals (hotel booking):**
| Persona | Requirements | Design goals |
|---|---|---|
| Budget traveller | Affordable options; price comparison; filters; genuine reviews; easy cancellation/refund | Easy price comparison; prominent offers; transparent pricing; informed decisions via reviews; simple cancellation |
| Business traveller | Fast search and booking; hotels near work; flexible check-in; Wi-Fi/meeting rooms; secure payment and instant invoice | Minimise booking time; location-based recommendations; highlight business amenities; quick secure payment and auto-invoice; flexible modification |
| Professional planner | Multi-client bookings; bulk booking; client profiles; history and reports; hotel communication | Efficient dashboard; quick client/reservation management; detailed reports; bulk booking with minimal effort; better agent–hotel communication |
| Hotel owner | Update details; manage rooms and price; booking notifications; reviews; sales/occupancy reports | Easy management dashboard; real-time updates; instant notifications; analytics; efficient operations |

**Requirement vs design goal:** a requirement states *what is needed* ("easy cancellation"). A design goal states *what the design must achieve*, measurably ("cancel in ≤ 2 taps").

---

## 4. PYQ SOLUTIONS (module-relevant only, grouped by topic)

> Marks guide: 5M ≈ 6–8 lines or a small table/diagram; 10M ≈ 1.5–2 pages with a diagram and an example.
> Excluded as other modules: wicked problems, UCD/goal-directed design, UI vs UX, AR/VR/XR, usability testing, heuristics, 5S, Gestalt, visual design, information architecture, widgets, prototyping, use case diagrams, interaction design, and so on.
> Borderline items are marked *(adjacent)*.

---

### GROUP A — User needs, types of users, requirements

**A1. [25] Q1(iv) / [24] Q1(iv) — Explain in brief the different types of users / relevance of user categorisation (5M)**

*Types of users:*
1. **Primary users** interact directly with the product regularly (a customer in a banking app).
2. **Secondary users** use it occasionally or via others (bank clerks, agents).
3. **Tertiary users** are affected or influence decisions (management, regulators, family).
4. **By expertise:** novice, intermediate, expert. **Extreme users** (power users and complete beginners) reveal edge-case needs.

*Relevance of categorisation:* each group has different goals, skills and context, so research and personas can target them. Designers can prioritise features for the primary group. It makes the interface inclusive (novices get guidance, experts get shortcuts), reduces usability errors, and improves satisfaction and adoption.
*Example:* an online food app has hungry customers (primary), delivery partners (secondary) and restaurant managers (tertiary).

**A2. [21] Q1(B)(7) — Justify the need to know the user before designing a system (5M)**
Use the bullet list from §3.1-A.
- **Real problem:** designing without knowing users builds assumed, not actual, solutions.
- **Cost:** it prevents costly rework.
- **Usability and satisfaction:** it matches skills, goals and context.
- **Hidden needs:** research exposes unstated needs and workarounds.
- **Inclusion:** it supports accessibility and diverse users.
- **Team alignment:** it gives the team a shared view.
- *Example:* a rail-ticket app for rural users needs vernacular language and low-data mode, which only user knowledge reveals.

**A3. [21] Q1(A)(2) — Which is a non-functional requirement? (1M)**
**Answer: (d) All of above.** Order of items, decoration/fonts/boxes, alignment and white space are all interface qualities (look, feel and layout), not functions the system performs. Non-functional requirements describe how the system behaves or presents itself.

**A4. [21] Q3 — Bank application: write assumptions and constraints; explain types of usability testing and process (10M)**
Only the *assumptions and constraints* part belongs to this module. Write:
- *Assumptions:* customers are registered, own smartphones, have internet and have done KYC; they have mixed digital literacy (including senior citizens); the bank provides secure APIs.
- *Constraints:* regulatory compliance (RBI), two-factor authentication, session time-out, security and encryption, low-bandwidth operation, accessibility, budget and time.
- (The usability testing types and process belong to the usability module. Cover them per that module's notes.)

---

### GROUP B — User research

**B1. [24] Q2A(i) — Importance of the "Research Stage" in designing, with examples (5M)**
- The research stage (Empathise) *discovers who the users are and what problem they really have* before design starts.
- **Reduces risk and cost:** wrong assumptions are caught early.
- **Finds real needs and pain points:** including hidden needs and workarounds.
- **Improves usability and satisfaction.**
- **Supports decisions** with evidence and gives input to personas, empathy maps and POV statements.
- *Example 1:* Airbnb found, through interviews with hosts, that poor property photos hurt trust. They offered professional photography and bookings rose.
- *Example 2:* Interviews with campus students showed that finding classrooms was the main problem, so a campus-navigation app was built rather than another timetable app.

**B2. [24] Q2A(ii) / [22] Q2A(OR) — What are the various ways / methodologies of conducting user research? (5M / 10M)**
Present as: definition, then each method (what, how, pros/cons), then a comparison table, then a combination note.

1. **Interviews:** qualitative 1-to-1; open-ended questions; rich emotional insight; time-consuming, small sample.
2. **Surveys / questionnaires:** structured, MCQ/rating/Likert; many users; quick and low cost; shallow.
3. **Observation:** direct, participant, contextual, shadowing; reveals actual vs reported behaviour; observer bias.
4. **Focus groups:** a moderated discussion of 6–10 users; brings out group opinions; dominant voices can bias.
5. **Contextual inquiry:** observing and questioning users in their own environment while they do the task.
6. **Diary studies:** users log their experiences over days or weeks; long-term behaviour; needs participant commitment.

Then draw the comparison table from §3.2 (interview/survey/observation × participants/data/cost/depth). Conclude: *combining methods (triangulation) gives more reliable findings.* (For 10M add the steps for interviews, tips for surveys, and the observation checklist.)
*Example (Smart Teaching-Learning app):* interview 10 students, survey 100, and observe classroom use of the LMS.

**B3. [24] Q4(iii) / [21] Q1(B)(3) — Goals of user research (10M / 5M)**
List the 8 goals from §3.2 with a one-line explanation each. For 10M, add a diagram:
`Research → Needs & pain points → Insights → Problem statement/POV → Design decisions`
and an example (e.g. a food delivery app: understand why users abandon the cart → find hidden charges → fix the pricing display).

**B4. [22] Q1(ii) — List the tools required for the conduction of user research (5M)**
Give the list from §3.2: interview guides and recorders; survey tools; observation checklists and field notes; analytics; affinity diagram/Miro; empathy-map and persona templates; screen recorders. Add one line on what each is used for.

**B5. [25] Q1(iii) / [21] Q2(a) — Compare qualitative and quantitative research (5M / 10M-part)**
Use the comparison table from §3.2. For the UX context, add:
- *Qualitative example:* interviewing 8 users shows they abandon a bill-payment app because they don't trust it.
- *Quantitative example:* a survey of 200 users finds that 62% abandon at the payment screen.
- Conclude with: use qualitative to *find* problems, quantitative to *size* them, and combine both.

**B6. [22] Q1(iii) / [23] Q2A — "Great questions lead to great design." Explain / map to user research and journey with example (5M / 10M)**
*Explanation (5M):* the quality of design depends on the quality of the questions asked during research. Good open-ended questions ("Tell me about the last time you…") uncover real needs, motivations and pain points. Poor questions ("Would you like a feature X?") give biased, shallow answers. Good questions reveal the *why* behind actions, which leads to an accurate problem statement and relevant design.

*Mapping to user research and journey (10M), with the example of a food-ordering app:*
| Journey stage | User research question asked | What it reveals → design outcome |
|---|---|---|
| Discovery | "How do you decide what to eat?" | Users compare on price/time → show ETA and price on the home screen |
| Selection | "What was hard about choosing a dish?" | Too many options → filters and reviews |
| Checkout | "Describe the last time you abandoned an order." | Hidden fees → show the total upfront |
| Delivery | "What do you do while waiting?" | Anxiety → live tracking |
| Post-order | "What would make you reorder?" | Trust → one-tap reorder and ratings |

Explain: research questions (interviews and surveys) feed the journey map's *thoughts, emotions and pain points*. Each pain point becomes an opportunity. Hence great questions → accurate journey map → great design.

---

### GROUP C — Empathy maps

**C1. [24] Q1(v) / [25] Q1(ii) — Importance / usefulness of an empathy map (5M)**
Definition (1–2 lines) + the 4-quadrant diagram + the importance points from §3.3-B.
Add the example: for a food-ordering app, *Says:* "Delivery is always late". *Thinks:* "Is the restaurant even preparing it?" *Does:* keeps refreshing the app and calls the restaurant. *Feels:* anxious, helpless. The insight is that live tracking is needed.

**C2. [22] Q3(iii) — Describe the process of building an empathy map (10M)**
Draw the diagram, then write the 8 steps from §3.3-B. Add a worked mini-example (e.g. the TV buyer from C4 below). Conclude: *it is bottom-up, and the output feeds personas and POV statements.*

**C3. [21] Q2(c) — How to use the 4 quadrants of the empathy map in the UI design of an online food-ordering application (10M)**
Draw the empty template, then fill it in for the **user = hungry office worker, 28**:
| Quadrant | Content | Design implication |
|---|---|---|
| **Says** | "I just want to order quickly." "Why is the delivery fee so high?" "The app hung at payment." | Faster flows; transparent fees; stable checkout |
| **Thinks** | "Will it arrive hot and on time?" "Is the restaurant good? Are reviews real?" "Is my card safe?" | ETA and tracking; verified ratings; trusted payment badges |
| **Does** | Scrolls many restaurants, filters by rating, compares prices, reorders favourites, calls the delivery person | Smart filters; favourites and one-tap reorder; in-app call/chat |
| **Feels** | Anxious about delays; frustrated by hidden charges; delighted by offers | Reassuring status messages; no surprise costs; visible offers |

*How the quadrants shape the UI:*
- *Says + Does* → content and function (search, filters, reorder).
- *Thinks + Feels* → trust and emotional design (reviews, status, calm tone).
- *Pain* (fees, delays, payment failures) → fix first. *Gain* (offers, speed) → highlight.
- The result becomes the persona and POV: *"A busy office worker needs a quick, predictable order because delays and hidden fees make them anxious."*

**C4. [22] Q3(ii) — A user wants to buy a television. Create an empathy map with justification (10M)**
User: **Rohan, 35, IT professional, buying a 55" smart TV for the family.**
```
          ┌─────────────────────────┬────────────────────────────┐
          │ SAYS                    │ THINKS                     │
          │ "Which brand is most    │ "Will I get cheated on     │
          │  reliable?"             │  price?" "Is 4K worth it?" │
          │ "Is there EMI/exchange?"│ "Will it fit the wall/room?"│
          ├─────────────────────────┼────────────────────────────┤
          │ DOES                    │ FEELS                      │
          │ Reads reviews, watches  │ Confused by specs (OLED/   │
          │ YouTube comparisons,    │ QLED); anxious about the   │
          │ checks prices online &  │ big spend; excited about   │
          │ in stores, asks friends │ the home-theatre; wary of  │
          │ and family              │ after-sales service        │
          └─────────────────────────┴────────────────────────────┘
   PAINS: jargon, price differences, fear of wrong choice, installation/warranty worries
   GAINS: good value, picture quality, smooth smart features, easy return/warranty
```
*Justification:*
- **Says:** comes from interview quotes (price, reliability, EMI).
- **Does:** from observation (research behaviour, comparison across stores).
- **Thinks/Feels:** inferred from hesitation and questions (fear of a bad purchase).
- **Insight/design:** a comparison tool, a plain-language spec guide, transparent price/EMI/exchange, clear warranty and service info → this builds trust and speeds up the decision.

**C5. [23] Q3(i) — Design an empathy map for Alex (10M)** (Alex is the Q2B(ii) persona: timid, academically strong, obedient, inclined to a managerial role. The placement cell wants skill and personality-development sessions.)
Draw the 4-quadrant diagram and fill it with the content below. All entries are assumptions based on the case. State that they would be validated through interviews with Alex, faculty and peers.
```
          ┌───────────────────────────┬──────────────────────────────┐
          │ SAYS                      │ THINKS                       │
          │ "I'm not good at speaking │ "What if I make a mistake in │
          │  in groups."              │  front of everyone?"         │
          │ "I'll do what the faculty │ "Can I ever lead people?"    │
          │  suggests."               │ "Others are more confident." │
          │ "I prefer managerial work."│"I'm good at planning/studies"│
          ├───────────────────────────┼──────────────────────────────┤
          │ DOES                      │ FEELS                        │
          │ Scores well, submits on   │ Nervous in interviews/GDs;   │
          │ time, follows instructions│ anxious about placements;    │
          │ avoids group discussions, │ self-doubting about          │
          │ sits at the back, rarely  │ communication; motivated     │
          │ asks questions or         │ and hopeful about a          │
          │ volunteers                │ managerial career            │
          └───────────────────────────┴──────────────────────────────┘
   PAINS: fear of public speaking, low confidence, lack of leadership exposure, GD/interview anxiety
   GAINS: wants a managerial role, wants confidence, wants recognised leadership skills
```
*Insight/need:* Alex has the capability and the interest, but lacks confidence and communication experience. He needs safe, structured chances to practise leadership and communication.
*POV:* "Alex, a high-scoring but timid engineering student aiming for a managerial role, needs low-pressure opportunities to build communication and leadership skills because his fear of speaking in public hides his real ability from recruiters."

---

### GROUP D — Personas

**D1. [24] Q5(iii) — The term "persona" in designing: explain the importance (5M)**
Definition: a fictional, research-based archetype representing a group of real users (name, photo, background, goals, pain points, needs, quote).
Importance: use the list in §3.3-C (focus on the real user; stops "designing for myself"; shared language; prioritises features; builds empathy; guides testing; supports inclusive design).
*Example:* "Riya, 18, first-year student who gets lost on campus" guides the features of a campus-navigation app (classroom search, GPS, reminders).

**D2. [25] Q5(v) — Purpose of any two persona types (5M)**
- **Primary persona:** the main target user. The design is optimised for their goals, so the core flow works perfectly for them. *Example:* a first-year student in a campus app.
- **Negative (anti) persona:** the user you are *not* designing for. It stops scope creep and keeps the team from adding features for the wrong audience (e.g. a hacker/fraudster in a banking app, or a visitor in a student-only app).
Optionally mention secondary (extra needs, but don't compromise the primary) and customer personas.

**D3. [25] Q2(ii) / [22] Q2B(i) — Steps of constructing / process of creating personas (10M)**
Write the 8 steps from §3.3-C as a flow:
`Research → Analyse patterns → Segment → Key attributes → Build profile → Prioritise → Scenario → Validate/refresh`
Add the **persona card** (name, age, role, devices, background, goals, frustrations, needs, quote) and an example such as *Sneha, a wheelchair user, from the campus-navigation case*. Conclude with the benefits and the reminder that personas are based on **data, not assumptions**.

**D4. [23] Q2B(ii) — Design a persona for Alex so the placement cell can pick a suitable job profile (10M)**
Persona card:
| Field | Content |
|---|---|
| **Name** | Alex Fernandes |
| **Age / Education** | 21, final-year B.Tech Computer Engineering; CGPA ~8.5 |
| **Personality** | Timid, introverted, obedient, disciplined, reliable |
| **Strengths** | Strong academics, planning, organisation, punctual, detail-oriented, follows process |
| **Interests** | Managerial and coordination roles (project/operations/business analysis) |
| **Tech comfort** | High; uses the college LMS, LinkedIn, and online courses |
| **Goals** | Get placed in a managerial-track role; build confidence; be seen as a leader |
| **Pain points / frustrations** | Fear of public speaking; avoids GDs and interviews; low self-confidence; hesitates to take initiative; limited leadership exposure |
| **Needs** | Safe practice for GDs and mock interviews; communication and soft-skill training; leadership roles in small projects; mentoring |
| **Quote** | *"I know I can manage things well — I just can't show it when everyone is watching."* |
| **Scenario** | Placements start in two months. Alex plans well but stays quiet in the pre-placement GD and loses chances. |

*Justification and use for the placement cell (job-profile choice):*
- **Suitable profiles:** *Business/Systems Analyst, Project Coordinator, QA/Process Analyst, Operations or Program Management trainee, Technical Documentation/Scrum Support.* These need planning, discipline and accuracy more than extroversion and offer a path towards management.
- **Sessions to organise:** mock GDs and interviews, public-speaking/Toastmasters-style practice, leadership mini-projects, personality development and mentor sessions.
- *Assumptions:* data would come from interviews with Alex, faculty and peers, and from grade/attendance records.
- The persona helps the cell act on Alex's needs rather than guess, and it generalises to similar students (a "timid high-performer" primary persona).

---

### GROUP E — Journey map / storyboard / flows *(adjacent topics; the study material has dedicated notes for them)*

**E1. [22] Q1(i) — "A storyboard is a great way to tell the stories." Justify (5M)**
A storyboard is a sequence of drawn scenes showing how a user encounters a problem and uses the solution.
- It is visual and quick to understand for all stakeholders.
- It shows context, emotion and the user's goal, not just screens.
- It is cheap to make and easy to change.
- It aligns the team and reveals gaps early.
- It builds empathy and supports testing the concept.

*Example (Smart Teaching-Learning system) — draw 6 frames:* student struggles → opens app → logs in → app detects weak subject → recommends material → quiz and feedback.

**E2. [25] Q5(vi) — Wireframing vs Storyboarding (5M)**
| Basis | Wireframe | Storyboard |
|---|---|---|
| Purpose | Layout and structure of a screen | Story of the user's experience |
| Shows | Placement of elements, navigation, content blocks | Scenes in sequence: context, actions, emotions |
| Fidelity | Low-fidelity skeleton, mostly black and white | Sketches/comic frames |
| Stage | Design/prototyping | Empathy/ideation (earlier) |
| Nature | Static, per-screen | Narrative sequence |
| Used for | Screen design and usability testing | Communicating concept and user scenario |

(The [21] MCQ: *wireframing & storyboard are __ & __ tools* → **(c) Static & Dynamic**.)

**E3. [23] Q3(ii) — What are User Flows in UX? How does it benefit the UX designer in depicting the user journey? (10M)**
*User flow:* a diagram of the path a user takes to complete a task, covering entry point, screens, decisions and exit. Standard symbols: oval = start/end, rectangle = screen/step, diamond = decision, arrows = direction.
*Example: online food order:* Open app → Login? (No → sign up) → Search → Select item → Cart → Address → Payment (Fail → retry) → Confirmation → Track order.
*Benefits:*
- visualises the journey logically
- finds dead ends, extra steps and friction
- helps design the shortest path
- supports communication and team alignment
- bridges research (journey map) to wireframes
- helps test and validate navigation before building

*Note:* a journey map shows *emotions and pain points*, while a user flow shows *screens and steps*.

**E4. [23] Q3(iii) — How UX stories capture attention, provide clarity and inspire designers to take decisions (10M)**
A UX story is a narrative about a user in a context with a goal, a problem and an outcome. Examples are scenarios, storyboards and user stories.
- *Captures attention:* people remember stories more than specs, and emotion engages the team.
- *Provides clarity:* it shows who, what, why and in what context, which removes ambiguity.
- *Inspires decisions:* the team asks "what would help *her* here?" It makes the trade-offs tangible.
- *Example:* *"Riya, a first-year student, is late for her lab because she can't find the building"* → decisions: GPS indoor navigation, classroom search, reminders.
- Also link it to the user story format ("As a student, I want… so that…") and the storyboard.

---

### GROUP F — Problem framing (Define stage)

**F1. [24] Q1(ii) — Justify the problem-formulation step in enhancing user experience (5M)**
Use §3.4.
- Formulation is the **Define** step. It turns research into one clear, user-centred problem.
- Without it, the team builds well-designed but wrong features.
- It focuses on the *root cause* (5 Whys) instead of the symptom.
- It aligns the team and sets scope, saving time and money.
- It leads to POV and HMW questions that give relevant and innovative solutions, so the final UX fits real needs.
- *Example:* "Users want a nicer checkout" becomes, after root-cause analysis, "Budget travellers need to see the total price upfront because hidden fees destroy trust." The fix is price transparency, not just a better colour.

---

### 4.X Pre-empting likely questions (not yet asked, but in the syllabus and slides)

**P1. Write a POV statement and HMW questions for an e-learning app for rural students (10M)**
- **User:** a Class 10 student in a rural area with a shared smartphone and intermittent network.
- **Need:** to *continue* studying without needing a constant connection.
- **Insight:** lessons stop when data drops, and students then abandon study altogether because they cannot resume.
- **POV:** *"A rural Class 10 student with a shared phone and unstable internet needs to keep learning offline because every network drop makes them lose progress and give up."*
- **HMW:**
  - HMW let students download lessons for offline use?
  - HMW save progress automatically and resume instantly?
  - HMW make the app light enough for low-end phones?
- Check: HMWs are not too broad or too narrow, and they have no solution baked in.

**P2. Translate requirements into design goals (10M)** — Use the 10-step list from §3.5, then give one table row, e.g.
- *Requirement:* "Students need to find classrooms quickly."
- *Design goal (SMART):* "Let a new student locate any classroom within 30 seconds, with ≥ 90% success in testing, by the next release."

**P3. Pain-point types / 5 Whys; Needs vs wants; FR vs NFR** — see the tables and examples in §3.1.

---

## 5. LAST-MINUTE REVISION SHEET

| Concept | Remember |
|---|---|
| Empathise | Understand users (interview, survey, observe) |
| Define | One clear problem: POV + HMW |
| Interview | 1-to-1, open-ended, qualitative, stories over opinions, 5 Whys |
| Survey | Many users, quantitative, 5–10 questions, closed + open |
| Observation | Real behaviour, AEIOU, beginner's mindset, workarounds |
| Empathy map | Says · Thinks · Does · Feels (+ Pains/Gains); bottom-up |
| Persona | Fictional, research-based archetype: goals, pains, needs, quote |
| Persona types | Primary · Secondary · Negative · Customer |
| POV | **[User] needs [Need (verb)] because [Insight]** |
| HMW | Open, optimistic question from the POV; pick the best 2–3 |
| Problem framing steps | Insights → Map system → Question brief → POV → HMW |
| Design goal | Requirement → goal; SMART (S-M-A-R-T) |
| Journey map | Stage × (action, touchpoint, thought, emotion, pain, opportunity) |
| Storyboard | Visual scenes of a user story |

**Exam strategy:**
1. For any scenario question (Alex, TV, food app, banking app), start with the persona, then draw the empathy map, then write the POV and HMW. This chain scores in 10M answers.
2. Always **draw** the diagram (empathy map quadrant or persona card).
3. State **assumptions** clearly, since every case-based PYQ asks for them.
4. Give one example for every definition.
