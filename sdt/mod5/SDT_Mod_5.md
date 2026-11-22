# SDT_Mod_5 - Software Design Thinking, Module 5: Testing, Feedback & Implementation (09 hrs, CO3 / CO4 / CO5)

> **Sources I went through (all of them):**
> - `SDT Module 5_Testing and Feedback Implementation v2.pptx` (120 slides). It covers usability testing from the textbook angle: Nielsen attributes, ten principles, six dimensions of usability, ten usability techniques, four test types, moderator skills, the 8-step test process and test-lab setup. It also covers the four families of feedback methods (think-aloud, I Like/I Wish, card sorting, Wizard of Oz, five whys, SUS/SEQ/NPS/A-B/heatmaps), the limitations of iteration, and prototype to architecture in 4 steps. The Capstone slide is a title slide only.
> - `SDT_Module5_Testing and Feedback Implementation Module 5 .pptx` (85 slides). It covers the usability testing definition and ISO 9241-11, elements of testing, moderated/unmoderated/in-person/remote testing, frameworks (RAPID, RTIE and so on), iterative design (7 steps, benefits, challenges, Slack/Airbnb/Instagram), and the full farmer crop-disease worked example (prototype, requirements, architecture, use case, class, sequence) plus four more examples. All diagram-only slides were read directly as images.
> - All 10 scanned PYQ screenshots plus `User Experience Design.PDF` (July 2025 paper, 2 pages) in `../question_papers_all_time/`. All 6 papers were read; which of their questions belong to this module is listed in Section 4.
>
> **Honest note on the PYQs (read this first):**
> - The old papers are for the course *User Experience Design* (UXD), not SDT. The 2023-05-24 paper is for *Software Architecture and Design Thinking* and is 100% architecture (connectors, C2, pipe-and-filter, ADL). It does not map to "Translating prototypes into architecture/design models", which is a UX-to-UML bridge, so I excluded it. If your SDT exam wants "software architecture", use it only as background.
> - Only **usability testing** is heavily and repeatedly asked (6 of 6 papers). Feedback methods, iteration, prototype-to-architecture and the capstone have **zero** direct PYQs. Their notes and questions below are marked `[SELF]` so you know they did not come from an old paper.
> - Excluded because they belong to other modules: empathy map, persona, user research, heuristic principles (the 10 Nielsen heuristics), 5S model, wicked problems, Gestalt, AR/VR/XR, wireframes vs storyboards, widgets, 5 dimensions of interaction design, visual design principles, information architecture.
> - Near misses: "Role of **feedback mechanism** in UI design" (Nov 2023 Q2A-i) is system feedback to the user (progress bars, confirmations), not collecting user feedback. Do not mix the two. "Heuristic evaluation is a method of ___" (Nov 2021, 1 mark) is included in 5.1 because the deck lists Expert/Heuristic Evaluation as one of the 10 usability techniques.
>
> **Markers used in this file (no emojis):**
> - `[PYQ]` = this topic and question type has appeared in a past paper.
> - `[SELF]` = not in notes or papers in this form. I made it from the syllabus or by extending the notes.
> - `[NOTES]` = taken directly from the slides.
> - `-` = not applicable or not expected.

---

## 1. TOPIC MAP

```
MODULE 5 : TESTING, FEEDBACK & IMPLEMENTATION
|
+-- 5.1 Usability Testing Principles
|   +-- What is usability / usability testing
|   |   +-- Definition: real user + realistic task -> observe -> find problems -> improve
|   |   +-- ISO 9241-11 : effectiveness, efficiency, satisfaction in a specified context
|   |   +-- Elements: Facilitator, Participant, Tasks, Facility
|   |   +-- Why it drives conversions (journey vs drop-off examples)
|   +-- Dimensions / Attributes of usability
|   |   +-- Nielsen's 5: Learnability, Efficiency, Memorability, Errors, Satisfaction
|   |   +-- Six dimensions: Usefulness, Efficiency, Effectiveness, Learnability,
|   |                       Satisfaction, Accessibility
|   +-- The 10 Usability Testing Principles
|   |   +-- Learnability . Efficiency . Memorability . Error prevention & recovery
|   |   +-- User satisfaction . Effectiveness . Real user involvement
|   |   +-- Representative tasks . Observation & data collection . Iterative testing
|   +-- Good-practice rules
|   |   +-- Test the task not the user . Clear metrics early (quantitative / qualitative)
|   |   +-- Recruit representative users (5-8 per group) . Think-aloud
|   |   +-- Facilitator neutrality . Iterate & prioritise fixes (Critical/Major/Minor)
|   +-- Why products are less usable (5 reasons) and how to fix (UCD attributes)
|   +-- 10 Techniques for building usability
|   |   +-- Ethnography . Participatory design . Focus group . Surveys . Walk-through
|   |   +-- Open/closed card sorting . Paper prototyping . Expert/Heuristic evaluation
|   |   +-- Usability testing . Follow-up studies
|   +-- Goals of usability testing . Basics of methodology . Limitations
|   +-- TYPES of usability tests
|   |   +-- By lifecycle: Exploratory(Formative) . Assessment(Summative)
|   |   |                 Validation(Verification) . Comparison
|   |   +-- By moderation: Moderated . Unmoderated
|   |   +-- By delivery: In-person . Remote
|   |   +-- User Acceptance Testing (UAT) [SELF]
|   +-- Test Moderator: roles, who can be one, qualities
|   +-- THE USABILITY TESTING PROCESS (8 steps)
|   |   +-- Test plan (9 parts) . Environment (lab vs field) . Participants
|   |   +-- Materials . Conduct sessions . Debrief . Analyse . Report
|   +-- Usability frameworks: RAPID . RTIE . DECIDE . THINK . PACE . TEST
|
+-- 5.2 Methods of Collecting User Feedback
|   +-- A. Qualitative / observation (empathy-driven)
|   |   +-- Think-aloud (concurrent / retrospective)
|   |   +-- Direct observation & shadowing
|   |   +-- I Like - I Wish - What If (feedback capture grid)
|   +-- B. Interactive / co-creation (ideation-driven)
|   |   +-- Prototype critique & card sorting
|   |   +-- Wizard of Oz testing
|   +-- C. Post-task interview & inquiry
|   |   +-- Semi-structured debrief interviews
|   |   +-- Five Whys
|   +-- D. Quantitative / standardised (validation-driven)
|       +-- Task success rate . Time on task . Error rate
|       +-- SUS (0-100, avg 68) . SEQ (1-7) . CSAT . NPS
|       +-- A/B (split) testing
|       +-- Telemetry: heatmaps . funnel drop-off . eye tracking
|
+-- 5.3 Iteration Cycles and Refinement Strategies
|   +-- Iterative design meaning (Test -> Learn -> Refine -> Repeat), sculpting analogy
|   +-- Why design is iterative (needs evolve, tech changes, surprises)
|   +-- 7 steps of iterative design process
|   +-- Merits (quality, risk, happy users, team growth, flexibility)
|   +-- Limitations / challenges (cost, fatigue, local maxima, agile-UX clash,
|   |                              stakeholder resistance, feedback bias, scope, decision)
|   +-- Best practices (act slowly, test, listen, agile, document)
|   +-- Real cases: Slack, Airbnb, Instagram
|   +-- Link with 5 stages of design thinking
|
+-- 5.4 Translating Prototypes into Software Architecture / Design Models
|   +-- Prototype = what user experiences ; architecture = how software delivers it
|   +-- 4-step translation
|   |   +-- 1 Component decomposition (Atoms, Molecules, Organisms, Templates; state)
|   |   +-- 2 Data modelling (forms -> schema, keys, validation)
|   |   +-- 3 API & sequence modelling (UML sequence, OpenAPI contract)
|   |   +-- 4 Architecture style (Client-server/SPA, Microservices/Event-driven, MVC/MVVM)
|   +-- Worked flow: prototype -> feedback -> requirements -> architecture -> UML
|   +-- UML used: Use case . Class . Sequence . State . Activity . ER . Component . Deployment
|   +-- Worked examples: Crop disease, Food delivery, Campus attendance,
|                        Hospital booking, AI study assistant
|
+-- 5.5 Capstone Project: Design Thinking on a Real-World Software Problem
    +-- (slide is title only - everything here is [SELF])
    +-- Phase map: Empathize -> Define -> Ideate -> Prototype -> Test -> Iterate -> Architect
    +-- Deliverables per phase . Report structure . Viva questions
```

---

## 2. TOPIC-WISE ASKED QUESTION TYPES

Legend: **PYQ(n)** = appeared n times across the 6 papers. `[S]` = not asked yet but likely, from syllabus and notes. `-` = not applicable.
Frequency summary: usability testing process/types appears in all 6 papers.

| Topic | Short note (5M) | Long theory (10M) | Diagram / flow | Numerical | Case / scenario-based | Fill-in / MCQ (1M) | Compare / differentiate |
|---|---|---|---|---|---|---|---|
| 5.1 Usability testing process (8 steps) | `[S]` | **PYQ(2)** Jul 2024 Q3-iii, Jul 2025 Q4-i; also with Q3 Nov 2021 | **PYQ** (flow of steps expected) | - | **PYQ(1)** Nov 2021 bank app | - | - |
| 5.1 Types of usability testing | **PYQ(2)** Jul 2024 Q5-v, (Nov 2023 as 10M) | **PYQ(3)** Nov 2023 Q4-ii, Dec 2022 Q4-iii, Nov 2021 Q3 | table / lifecycle diagram | - | **PYQ** (with examples) | - | `[S]` formative vs summative |
| 5.1 Dimensions / attributes of usability | **PYQ(1)** Jul 2025 Q1-vi | **PYQ(1)** Jul 2024 Q4-ii (10M) | `[S]` | - | `[S]` | - | `[S]` |
| 5.1 Importance / need / goals of usability testing | `[S]` | **PYQ(1)** Nov 2023 Q4-ii (first half) | - | - | - | **PYQ(1)** Nov 2021 "Usability testing refers to ___" | - |
| 5.1 Heuristic / expert evaluation (as a technique) | `[S]` | `[S]` | - | - | - | **PYQ(1)** Nov 2021 "Heuristic evaluation is a method of ___" | `[S]` heuristic eval vs usability test |
| 5.1 User Acceptance Testing (UAT) | **PYQ(1)** Nov 2023 Q5-vi | - | - | - | - | - | `[S]` UAT vs usability testing |
| 5.1 Principles, techniques (10), moderator skills, test plan, lab vs field | `[S]` | `[S]` | `[S]` | - | `[S]` | - | `[S]` moderated vs unmoderated |
| 5.1 Quantitative metrics (completion rate, error rate, time, SUS) | `[S]` | - | - | `[S]` SUS/NPS/rates | `[S]` | - | - |
| 5.2 Feedback collection methods | `[S]` | `[S]` | `[S]` I Like/I Wish grid | `[S]` SUS, NPS, completion % | `[S]` choose method for given app | - | `[S]` qualitative vs quantitative |
| 5.3 Iteration cycles / refinement | `[S]` | `[S]` | `[S]` loop diagram | - | `[S]` (Slack, Airbnb, Instagram) | - | `[S]` iterative vs waterfall |
| 5.4 Prototype -> architecture / design models | `[S]` | `[S]` | `[S]` use case, class, sequence, architecture diagram | - | `[S]` apply to given app | - | `[S]` prototype vs architecture |
| 5.5 Capstone | - | `[S]` | `[S]` end-to-end phase diagram | - | `[S]` | - | - |

How to read the table: the examiner has asked **usability testing types and process** almost every year and has never (so far) asked the other four syllabus items. A fixed pattern shows up: 10M = "types + process" or "dimensions"; 5M = "types of usability testing" or "UAT"; 1M = definition. Because the SDT syllabus differs from the UXD papers (5.2 to 5.5 are new for this subject), expect the SDT paper to ask 5.2 to 5.5 in `[S]` forms, so I wrote full answers for them below.

---

## 3. TOPIC BY TOPIC: DETAILED BREAKDOWN

General exam rule for this module: usability testing answers want (1) a definition line, (2) a list or numbered steps, (3) a small diagram or table, (4) one example. Ten-mark answers need about 2 pages: definition, diagram, 6 to 8 points with one line of explanation each, example, conclusion.

---

### 3.1 Usability Testing Principles  [PYQ]

#### 3.1.1 What is usability and usability testing  [NOTES][PYQ: Nov 2021 1M]

**Usability** is the absence of frustration in using a product. A product is usable when the user can do what they want, the way they expect, without hindrance, hesitation or questions.

**ISO 9241-11 definition (quote in exam):** usability is the extent to which *specified users* can achieve *specified goals* with *effectiveness, efficiency and satisfaction* in a *specified context of use*.

**Usability testing** is a user-centred evaluation technique in which representative users perform realistic tasks on a system while an evaluator observes behaviour, difficulties, errors, completion time and feedback.

One-line formula to memorise:
`Give a real user a realistic task -> observe what they do -> identify problems -> improve the design.`

What it discovers:
- where users face difficulty
- why they make errors
- whether they can complete important tasks
- how efficiently they complete them
- whether they are satisfied
- where the design can be improved

Fill-in-the-blank answer (1M): "Usability testing refers to **evaluating a product by testing it with representative users who perform realistic tasks, to find usability problems and improve the design**."
"Heuristic evaluation is a method of **expert (inspection-based) review of an interface against accepted usability principles, done without end users**." (The deck lists it as technique 8.)

**Elements of a usability test (Nielsen Norman Group):**
1. Facilitator: guides, creates tasks, sets the tone.
2. Participant: the real user.
3. Tasks: the practical journeys to complete.
4. Facility: tools, prototype, digital assets (the slide heading says three elements but lists four).

**Why it drives conversion:** users who move smoothly continue the journey, and users who hit confusion drop off. Example:
- E-commerce: search shoes -> filter -> view -> add to cart -> pay (continues). The drop-off version has a slow or confusing checkout.
- Food delivery: drop-off when unexpected delivery charges appear at checkout.
- Online banking: drop-off with unclear error messages or too many steps.
- App download: drop-off when the download button is hard to find.

#### 3.1.2 Dimensions / attributes of usability  [NOTES][PYQ: Jul 2024 Q4-ii 10M, Jul 2025 Q1-vi 5M]

There are two lists in the notes. Quote both. For a 10M answer, give the six dimensions as the main answer and mention Nielsen's five.

**A. Six dimensions (usability is an appropriate blend of these):**

| Dimension | Meaning | How measured |
|---|---|---|
| Usefulness | Does the product let the user achieve their goals; will they want to use it at all. Without it, a product will not be used even if free | feature fit, willingness to use |
| Efficiency | Speed with which the goal is reached accurately and completely. A few seconds saved per use adds up | time on task |
| Effectiveness | Extent to which the product behaves the way the user expects; ease of doing what they intend | error rate (% of total usage) |
| Learnability | Ability to operate the system to a defined competence after minimal training (ideally none); infrequent users can relearn after inactivity. Part of effectiveness | time/trials to learn |
| Satisfaction | User perceptions, feelings, opinions, captured by questioning (written and oral); users rate and rank | questionnaires, SUS, interviews |
| Accessibility | Usable by people with varied abilities and conditions | accessibility checks |

**B. Nielsen's five usability attributes:** Learnability, Efficiency, Memorability, Errors, Satisfaction.
- Memorability: can a returning user use the system again without relearning everything.
- Errors: how many errors, how severe, how easily recovered.

**C. ISO 9241-11 trio:** Effectiveness, Efficiency, Satisfaction. This is the short answer for "key attributes: effectiveness, efficiency and satisfaction" (Jul 2025).

Diagram (draw this in the exam):

```
                      USABILITY
 +-----------+-----------+-----------+-----------+-----------+-----------+
 | Usefulness| Efficiency|Effective- | Learn-    | Satisfac- | Accessi-  |
 |           |  (time)   | ness      | ability   | tion      | bility    |
 |           |           | (errors)  |           |           |           |
 +-----------+-----------+-----------+-----------+-----------+-----------+
   "Does it    "How fast?"  "As user    "Easy to    "Feels      "Can all
    help?"                  expects?"   learn?"      good?"      use it?"
```

Example to use: a railway ticket app that is fast and learnable but lacks "season-ticket renewal" fails on usefulness, so users go elsewhere.

#### 3.1.3 The 10 usability testing principles  [NOTES]

| # | Principle | Core idea |
|---|---|---|
| 1 | Learnability | matches the user's mental model; a new user can quickly learn tasks |
| 2 | Efficiency | less time and fewer steps once learned |
| 3 | Memorability | system remembers where the user left off; resembles real world and other systems; no relearning |
| 4 | Error prevention and recovery | predefined values, dropdowns, date pickers prevent errors; clear messages let users recover |
| 5 | User satisfaction | user-centric design; collect questionnaires and interviews after use |
| 6 | Effectiveness | measure task completion rate and accuracy |
| 7 | Real user involvement | test with actual target users (not developers) at the actual place of use, to remove presumptions and bias |
| 8 | Representative tasks | realistic tasks, use metaphors |
| 9 | Observation and data collection | observe, record actions, note difficulties, gather quantitative and qualitative data |
| 10 | Iterative testing | test throughout development, improve based on findings |

**Good-practice rules (the second batch of principle slides):**
- **Test the task, not the user.** Frame instructions as natural scenarios, do not give step-by-step guidance, and criticise the design, never the participant.
- **Define clear metrics early.**
  - Quantitative: task completion rate, time-on-task, error rate, SUS score.
  - Qualitative: frustration points, confusion, verbal comments, spatial navigation flow.
- **Decide the goal of testing** before you start.
- **Recruit representative users** who match the persona and technical literacy. 5 to 8 users per distinct group uncover about 80 to 85% of issues.
- **Think-aloud protocol:** participants speak thoughts, expectations and hesitations. Focus on what users do rather than what they say they prefer.
- **Facilitator neutrality:** avoid leading questions ("How was that process?" not "Was that easy?"). Do not rescue participants immediately.
- **Iterate and prioritise fixes** by severity:
  - Critical: blocks task completion.
  - Major: significant delay or frustration.
  - Minor: cosmetic or minor inconvenience.
  - Test early with low-fidelity prototypes and often with high-fidelity builds.

#### 3.1.4 Why products are less usable, and how to make them usable  [NOTES][SELF as question]

Five reasons:
1. Development focuses on the machine or system, not the end user. Assumptions: humans will adapt, users are as technical as developers.
2. Target audiences change and adapt. The old users were forgiving; new users have less technical knowledge, less patience and different expectations.
3. Designing usable products is difficult. It is not commonsense and needs behavioural and social science background.
4. Specialist teams do not work in integrated ways. UI, help system and written materials are built by separate teams who do not synchronise.
5. Design and implementation do not match. Design is how the product communicates, implementation is how it works. Technical implementation has become easier while the design challenge has grown.

How to fix: focus on the end user, research users, bridge design and implementation, use an integrated approach, focus early on users and tasks, evaluate and measure usage, iterate.

Attributes of organisations that practise user-centred design (UCD): phases that include user input, multidisciplinary teams, concerned and enlightened management, a "learn as you go" perspective, defined usability goals and objectives.

#### 3.1.5 Ten techniques for building usability  [NOTES]

| # | Technique | One-line explanation | When / key point |
|---|---|---|---|
| 1 | Ethnographic research | observe users in their real place of use; build profiles, personas, scenarios, task descriptions | qualitative, early |
| 2 | Participatory design | representative users join the design team; or short workshops of users, designers, developers | in-house systems |
| 3 | Focus group | several users together judge preliminary concepts (paper drawings, storyboards, prototypes); "proof of concept" | very early; depth of feelings |
| 4 | Surveys | broad base of users, larger samples, generalisable | language must be crystal clear; asking is no substitute for observing |
| 5 | Walk-through | envision the user's route through an early concept; roles such as moderator and recorder; bring in a real user | structured, max about 2 hours |
| 6 | Open / closed card sorting | open: users name the categories; closed: users sort into given categories | cheap; content organisation and labels |
| 7 | Paper prototyping | paper or wireframe screens, one per state | quick, cheap, repeatable |
| 8 | Expert / heuristic evaluation | specialist with little project involvement reviews against usability principles; a "double specialist" (usability plus domain) is best | no end users involved |
| 9 | Usability testing | empirical data while representative users do realistic tasks; (I) formal true experiments to confirm or refute hypotheses, (II) less formal iterative cycles to expose deficiencies | core technique |
| 10 | Follow-up studies | after release; surveys, interviews, observations; truest appraisal since real user, product and environment interact | feeds the next release |

Important distinction: techniques that do not involve representative users (expert evaluation, walk-through) are **not** called usability testing.

#### 3.1.6 Goals, methodology and limitations of usability testing  [NOTES]

**Goals:**
- Inform design with data from representative users, to fix deficiencies before release. The product should be useful and valued, easy to learn, effective and efficient, and satisfying.
- Eliminate design problems and frustration: sets a positive relationship with customers, signals quality and ease of use, shows the organisation values customer goals.
- Improve profitability:
  - keeps a historical record of usability benchmarks
  - cuts support and service calls
  - raises sales and repeat sales
  - gives a competitive edge

**Basic elements (informal usability test):**
- Research questions or test objectives (not hypotheses).
- Representative sample of users (not necessarily random).
- Representation of the actual work environment.
- Observation of users using the product (or a representation of it).
- Controlled interviewing and probing by the moderator.
- Quantitative and qualitative performance and preference measures.
- Recommendations to improve the design.

Compare with **classical experiment methodology:** formulate a hypothesis, random assignment of participants, tight control, control groups, large sample for statistical significance.

**Limitations:**
- Testing is always an artificial situation.
- Results do not prove that a product works (statistical significance only means the result is probably not due to chance).
- Participants are rarely fully representative.
- Testing is not always the best technique.

#### 3.1.7 TYPES of usability testing  [NOTES][PYQ x4: Jul 2024 5M, Nov 2023 10M, Dec 2022 10M, Nov 2021 10M]

This is the single most repeated question. Know **two classifications** and give both when marks are 10.

**Classification 1: by position in the development lifecycle (the textbook answer; use it as the main one)**

```
 Requirements        Design starts         Mid-cycle              Close to release
 & specs done
     |                   |                     |                        |
     v                   v                     v                        v
 EXPLORATORY  ----->  ASSESSMENT  ------>  (more detail)  -------> VALIDATION
 (Formative)          (Summative)                                  (Verification)
 "Is the concept      "Can they do the     
  right?"              tasks?"                                      "Does it meet the
                                                                     benchmark?"
 COMPARISON test cuts across all three: A vs B (or vs competitor)
```

| | Exploratory (Formative) | Assessment (Summative) | Validation (Verification) | Comparison |
|---|---|---|---|---|
| When | very early, requirements done, design about to begin | early to mid cycle, after high-level design is set | late, close to release | any stage |
| Aim | check effectiveness of preliminary design concepts: supports tasks, communicates workflow, navigation from screen to screen | expand findings by testing lower-level operations ("the meat and flesh") | measure against a benchmark, or confirm earlier problems are fixed and no new ones introduced | compare two or more designs, or against a competitor |
| Prototype | static screens, paper drafts, partial mock-up showing enough functionality for the objective | working or semi-working prototype | near-final or final product | whichever is being compared |
| Moderator interaction | very high; informal collaboration; think aloud; almost an ongoing interview | reduced; fewer thought-process questions, more observed behaviour | very little or none; no think-aloud | depends on the base test |
| Data | mostly qualitative | quantitative collected; user always performs tasks | quantitative is central; reasons for failure still noted; more experimental rigour | performance and preference data side by side |
| Example | farmers try a paper mock-up of a crop-disease app to see if flow is understood | users must actually upload a photo and get a result; completion time recorded | check that 90% of users complete checkout in under 2 minutes (benchmark) | old checkout vs redesigned checkout |

Notes on each, one line to add for 10M answers:
- Exploratory is called "formative" because it forms the design.
- Assessment is the most typical test and the simplest for a novice to run; it is a cross between exploratory (informal) and validation (tightly controlled).
- Validation needs benchmarks defined before the test (specific error or time measures, or simply "problems found earlier are eliminated").
- Comparison can be an informal exploratory test or a tightly controlled classical experiment.

**Classification 2: by moderation and delivery**

| Type | What happens | Best for | Weakness |
|---|---|---|---|
| Moderated | researcher gives a task ("Book a hotel for two"), watches clicks and hesitation, asks "Why did you click here?", participant explains reasoning | complex or long workflows, new users | time-consuming, fewer users |
| Unmoderated | participants complete tasks alone via an automated platform (online usability test, survey, branching questionnaire, self-guided module) | quick feedback, broad user base | cannot ask follow-up questions |
| In-person | researcher physically present | observing facial expressions, body language, hesitation | logistics |
| Remote | online via screen sharing or usability platforms | distributed teams, global users | lose non-verbal cues |

In-person and remote are **delivery modes**, not separate test types; each combines with moderated or unmoderated.

**Classification 3: User Acceptance Testing (UAT)  [PYQ: Nov 2023 Q5-vi 5M; slides do not cover it, so this answer is `[SELF]`]**
- UAT is the final testing phase in which the actual client or end users check, in a near-real environment, whether the software meets agreed business requirements and is acceptable for release (sign-off).
- Types: alpha (internal users, developer site), beta (real users, user site), business acceptance, contract acceptance, regulatory acceptance, operational acceptance.
- Steps: plan and define acceptance criteria -> prepare test cases from business scenarios -> select users -> execute -> log defects -> fix and retest -> sign-off.
- Difference from usability testing: UAT asks "Does it meet the requirements and can we accept it?" (pass/fail against agreed criteria, run by the client). Usability testing asks "How easy, efficient and satisfying is it?" (run by the design team, finds friction, mid-development). Validation test in the deck is the closest usability equivalent to UAT.

#### 3.1.8 Test moderator: roles, who can be one, qualities  [NOTES][SELF as question]

Role: prepare material, arrange participants, coordinate the team; administer the session (greet, collect data, assist and probe, debrief); after the test, collate the day's data, debrief the team and check progress against test objectives.

Who can moderate: human factors specialist, marketing specialist, technical communicator, rotating team members (colleagues not on the same product), external consultant (guarantees objectivity).

Qualities (12 listed in the deck): aware of UCD basics, quick learner, instant rapport, excellent memory, good listener, comfortable with ambiguity, flexible, long attention span, empathic "people person", "big picture" thinker, good communicator, good organiser and coordinator. For a 5M answer, write the best 6 with a one-line reason each.

#### 3.1.9 THE USABILITY TESTING PROCESS (8 steps)  [NOTES][PYQ x4: Jul 2024 Q3-iii, Jul 2025 Q4-i, Nov 2021 Q3, Nov 2023 Q4-ii]

Flow (draw this; it is the expected diagram):

```
 1 Develop     2 Set up a      3 Find & select   4 Prepare
   test plan -> testing     ->   participants -> test materials
                environment                          |
                                                     v
 8 Report      7 Analyse       6 Debrief         5 Conduct
   findings <-   data &     <-   participant  <-   test sessions
   & recommend   observations    and observers
        |                                              
        +--------> fix design -> re-test (iterate)
```

**Step 1: Develop the test plan.** It is the blueprint, the main communication vehicle between designer, developer, moderator and management, defines required resources (what, when, where, who, why, how, how much) and is a milestone. Parts of a plan:
1. Purpose, goals and objectives
2. Research questions
3. Participant characteristics
4. Method (test design)
5. Task list
6. Test environment, equipment and logistics
7. Test moderator role
8. Data to be collected and evaluation measures
9. Report contents and presentation

**Step 2: Set up the testing environment.** Choose the location, lab or the user's site, based on test type, logistics, company public relations, participant availability, and multiple geographic locations if the market needs it.
- Minimalist portable lab (equipment carted to users). Pros: sees user context, easy for participants, cost-effective, reconfigurable. Cons: complex logistics, field sessions take longer, little observer space.
- Permanent fixed lab (single-room set-up). Pros: moderator has an excellent sense of the participant and can interact closely. Cons: participant may behave unrealistically in a comfort zone, very limited observer space.
- Gather equipment and tools, props, biometric data devices, and identify co-researchers: note taker or data gatherer, product expert, test observers.

**Step 3: Find and select participants.** Representative of the target audience (by persona and technical literacy), 5 to 8 per distinct user group, not developers or designers.

**Step 4: Prepare test materials.** Screening questionnaire, consent and non-disclosure forms, orientation script, background questionnaire, task scenarios, prototype or product, data collection sheets, pre- and post-test questionnaires, debriefing guide. (Slide names the step only; the list is standard practice, `[SELF]`.)

**Step 5: Conduct the test sessions.** Greet, brief, user performs realistic tasks; use think-aloud; the moderator stays neutral and does not rescue; record clicks, time, errors and comments.

**Step 6: Debrief the participant and observers.** Semi-structured interview, "What surprised you?", "Why did you do that?", ratings questionnaire (SUS), and a team debrief the same day.

**Step 7: Analyse data and observations.** Collate quantitative data (completion rate, time, errors) and qualitative notes (frustration points); group issues; rate severity (Critical, Major, Minor); find root causes.

**Step 8: Report findings and recommendations.** Summary, method, results, prioritised problems with evidence, recommended design changes. Then iterate: fix and re-test.

Exam tip: if the paper gives a case ("bank app", "ride-booking app"), keep the same 8 headings and attach one concrete line to each. Section 4 shows this done for the bank app.

#### 3.1.10 Usability testing frameworks  [NOTES]

| Framework | Main focus | Best for |
|---|---|---|
| RAPID | Recruit -> Assign -> Observe -> Analyse -> Improve | general usability testing |
| RTIE | rapid testing and iterative fixes | agile / iterative development |
| DECIDE | planning and evaluation | academic / research usability studies |
| THINK | user thoughts and reasoning | think-aloud testing |
| PACE | simple testing process | classroom / project activities |
| TEST | end-to-end evaluation | beginner-friendly teaching |

#### 3.1.11 Numerical problems on usability metrics  [SELF - no numericals in notes or PYQs, but the notes name the metrics so these can be asked]

**Formulas:**
- Task completion (success) rate = (users who completed the task / total users) x 100
- Error rate = (number of errors / number of task attempts, or total actions) x 100
- Average time on task = (sum of times) / (number of users)
- Efficiency (simple) = tasks completed per unit time
- SUS score: for each of 10 items (scale 1 to 5), odd items score = response - 1; even items score = 5 - response; sum of the 10 scores x 2.5 gives 0 to 100. Industry average is 68.
- NPS = % promoters (9-10) - % detractors (0-6); passives (7-8) are ignored.
- Nielsen's problem-discovery model: proportion found = 1 - (1 - L)^n, with L about 0.31. With n = 5: 1 - 0.69^5 = 1 - 0.156 = 0.844, about 85% (this is the "5 users find 85%" fact in the deck).

**Worked example 1 (completion, time, errors).** 10 users try "pay a bill". 8 succeed. Times (s) of all users: 40, 55, 38, 62, 45, 50, 70, 42, 48, 50. There were 12 errors in total across 10 attempts.
- Completion rate = 8/10 x 100 = 80%.
- Average time = (40+55+38+62+45+50+70+42+48+50) / 10 = 500 / 10 = 50 s.
- Error rate = 12 / 10 = 1.2 errors per attempt (or 120%).
- Interpretation: if the benchmark is 90% completion in 45 s, this fails a validation test on both counts, so iterate on the payment flow.

**Worked example 2 (SUS).** One participant's answers to items 1 to 10: 4, 2, 5, 1, 4, 2, 5, 2, 4, 1.
- Odd items (1,3,5,7,9) give response - 1: 3, 4, 3, 4, 3, total = 17.
- Even items (2,4,6,8,10) give 5 - response: 3, 4, 3, 3, 4, total = 17.
- Sum = 34; SUS = 34 x 2.5 = **85**, which is above the average of 68, so the system is judged highly usable.

**Worked example 3 (NPS).** 100 respondents: 50 gave 9-10, 30 gave 7-8, 20 gave 0-6. NPS = 50% - 20% = **+30**.

**Worked example 4 (how many users).** Using L = 0.31, find n for at least 95%: 1 - 0.69^n >= 0.95 so 0.69^n <= 0.05, n >= ln 0.05 / ln 0.69 = (-2.996) / (-0.371) = 8.07, so **9 users**. This shows why "5 users" is for iterative rounds, and why the deck says 5 to 8 per group.

---

### 3.2 Methods of Collecting User Feedback  [NOTES; no PYQ; all question forms `[SELF]`]

Why it matters: feedback during usability testing is not just bug-finding. It validates user needs, emotional reactions and mental models so the prototype can be refined and the team can loop back to earlier phases.

Four families (draw as a table in the exam):

```
 FEEDBACK METHODS
 |
 +-- 1 Qualitative & observation (empathy-driven)   -> WHY users behave so
 +-- 2 Interactive & co-creation (ideation-driven)  -> users as co-designers
 +-- 3 Post-task interview & inquiry                -> confirm observations
 +-- 4 Quantitative & standardised (validation)     -> HOW MUCH / benchmarks
```

| Family | Method | How it is carried out | What it reveals |
|---|---|---|---|
| 1 Qualitative | Think-aloud (concurrent) | user verbalises thoughts, feelings, expectations, frustrations while doing tasks | mental model, hidden assumptions, emotional friction in real time |
| 1 Qualitative | Think-aloud (retrospective) | user works silently, then talks through a video playback | avoids disturbing the task; good for timing measures |
| 1 Qualitative | Direct observation and shadowing | facilitator watches non-verbal cues, body language, expressions, hesitation, gestures without interrupting | unconscious behaviour users forget to mention |
| 1 Qualitative | I Like, I Wish, What If grid | four quadrants: I Like (delights), I Wish (pain points), Questions (not understood), What If / Ideas (new suggestions) | structures feedback into ideation seeds |
| 2 Co-creation | Prototype critique and card sorting | after tasks, users arrange cards (navigation categories or features) or annotate printouts with sticky notes | rebuilds information architecture from real intuition |
| 2 Co-creation | Wizard of Oz | low-fidelity prototype looks automated but a human secretly drives the responses (simulating AI or search) | tests complex concepts early without backend code |
| 3 Post-task | Semi-structured debrief interview | open questions right after the task ("What surprised you?", "How did you expect that button to respond?") | broader perspective, prevents solution-led bias |
| 3 Post-task | Five Whys | on confusion or complaint, ask "Why?" up to five times | root emotional or cognitive cause |
| 4 Quantitative | Task success rate | % completing flow without critical help or errors (pass/fail) | effectiveness |
| 4 Quantitative | Time on task | seconds or minutes to complete | efficiency |
| 4 Quantitative | Error rate and frequency | wrong clicks, wrong navigation, input errors | friction |
| 4 Quantitative | SUS | 10-item Likert survey after the test; score 0 to 100, average 68 | overall usability |
| 4 Quantitative | SEQ | one question after each task, "How easy or difficult was it?" on 1 to 7 | per-task ease |
| 4 Quantitative | CSAT and NPS | satisfaction score; likelihood to recommend | satisfaction and loyalty |
| 4 Quantitative | A/B (split) testing | users randomly see variant A or B; compare conversion, friction or speed under identical conditions | statistically valid winner |
| 4 Quantitative | Telemetry: click/scroll heatmaps | coordinates of interaction | whether the CTA button gets attention |
| 4 Quantitative | Funnel drop-off analysis | logs where users leave multi-step flows (checkout, onboarding) | UX bottlenecks |
| 4 Quantitative | Eye tracking | fixations, gaze duration, visual order on high-fidelity screens | what is seen and in what order |

**I Like / I Wish / Questions / What If grid (draw in exam):**

```
 +---------------------------+---------------------------+
 |  I LIKE                   |  I WISH                   |
 |  "Photo upload is quick"  |  "Result had a local      |
 |                           |   language option"        |
 +---------------------------+---------------------------+
 |  QUESTIONS                |  WHAT IF / IDEAS          |
 |  "What does 87% mean?"    |  "What if it sent an SMS  |
 |                           |   alert for next spray?"  |
 +---------------------------+---------------------------+
```

**Qualitative vs quantitative (likely compare question) `[SELF]`:**

| | Qualitative | Quantitative |
|---|---|---|
| Asks | Why and how | How many and how much |
| Sample | small (5 to 8) | large, statistical |
| Output | quotes, observations, themes | numbers, rates, scores |
| Methods | think-aloud, observation, interviews, I Like grid | SUS, completion rate, A/B, heatmaps |
| Risk | subjective, small sample | tells you what, not why |
Best practice: combine both (mixed methods). Quantitative finds the problem spot, qualitative explains it.

**Choosing a method `[SELF]` scenario answer, for example "A food delivery app's checkout has a 40% drop-off. How will you collect feedback?":**
1. Funnel drop-off analysis shows which checkout step loses users.
2. Heatmaps and session recordings show where taps go.
3. Moderated think-aloud on 5 users at that step reveals the cause (for example hidden delivery charge).
4. Five Whys on a complaint to find the root cause.
5. SEQ after the checkout task and SUS after the session to quantify.
6. A/B test the redesigned step against the old one, then validate again.

**Bias to watch (from the deck, links 5.2 and 5.3):** vocal minority bias, and polite or overly favourable answers in labs.

---

### 3.3 Iteration Cycles and Refinement Strategies  [NOTES; no PYQ; all `[SELF]` as question forms]

**Definition (use as the opening line):** Iterative design is a process in which each new version of a product learns from the previous version and improves it, through repeated cycles of design, testing, feedback and improvement. The core loop is **Test -> Learn -> Refine -> Repeat**. The key principle is continuous improvement rather than immediate perfection.

Sculpting analogy: start with a basic shape, remove or modify parts, refine based on observation, continue until the desired result.

Diagram:

```
          +------------------------------------------+
          |                                          |
          v                                          |
     DESIGN / PROTOTYPE --> TEST WITH USERS --> ANALYSE FEEDBACK
          ^                                          |
          |                                          v
          +------------------ REFINE <---------------+
                       (repeat until goals met)
```

**Why the design process is iterative:**
- User needs evolve, so what feels intuitive today may not tomorrow.
- Technology changes fast and opens new opportunities.
- Unexpected challenges appear; real-life testing shows problems you missed.

**7 steps of the iterative design process (from the DreamX diagram in the deck):**
1. Research and define: understand audience, frustrations, competitors; set clear goals.
2. Ideate and prototype: sketch concepts, quick wireframes, simple prototypes (imperfect is fine).
3. User testing: ask users directly; behaviour tells more than words. Testing with 5 users can uncover about 85% of usability issues.
4. Analyse and refine: step back and look at the big picture; which feedback points remain unsolved; simplify.
5. Design and implement: build it, keeping an open line of communication so adjustments can be made.
6. Launch and monitor: watch real use, drop-offs, unexpected issues (Google Analytics, Hotjar, user surveys).
7. Iterate and improve: needs evolve, so keep improving (A/B test headlines and buttons).

```
 (1) Research   (2) Ideate &   (3) User    (4) Analyse   (5) Design &   (6) Launch &  (7) Iterate
   & define  ->  prototype  ->  testing -> & refine   -> implement  ->  monitor   ->  & improve
      ^                                                                                  |
      +----------------------------------------------------------------------------------+
```

**Merits (benefits):**
- Higher-quality products (each cycle improves).
- Lower risk (flaws are caught early when they are cheap).
- Happier users (feedback shapes real needs, not assumptions).
- Stronger team growth (collaboration brings insight and skills).
- More flexibility (new ideas and market shifts are absorbed without starting over).

**Limitations / challenges (two slides sets, merged):**
1. Resource, time and budget drain: building, testing, discarding and rebuilding prototypes is costly; participant fatigue and recruitment bottlenecks.
2. Local maxima trap: you optimise button colours and copy while the core concept or architecture may be flawed; users react to what is in front of them rather than expressing latent needs.
3. Agile engineering vs UX timelines: 1 to 2 week sprints outrun research; technical debt from constant refactoring when architecture is neglected.
4. Stakeholder and organisational resistance: prefer fixed-scope predictability; view discarded prototypes as waste instead of learning.
5. Feedback bias and noise: vocal minority bias; false positives (polite or overly favourable behaviour in labs).
6. Scope overload (new ideas inflate the project) and decision struggle (when is it "done"?). Stakeholder fatigue is also named.

**Best practices (refinement strategies):**
1. Act slowly, one problem at a time (fix checkout first on an e-commerce site).
2. Test as much as you can, even prototypes.
3. Do not ignore feedback (users, stakeholders, team).
4. Use Agile principles (small tasks; redesign homepage, gather feedback, then move on).
5. Document all changes (feedback, changes, decisions).

Add from the notes, as refinement logic: prioritise by severity (Critical, Major, Minor), fix core structural issues early with low-fidelity prototypes, and re-run a validation test before release.

**Real-world examples (write one with numbers):**
- **Slack:** first year had 8 major design updates; processed over 400 requested features; search upgrade cut search time by 62%; threaded conversations were updated 14 times; now about 38.8 million daily active users and 95% satisfaction (figures as given in the deck).
- **Airbnb (2009):** revenue stuck at about $200 per week; founders saw poor listing photos, took professional photos, tested; revenue reportedly doubled in a week; later a professional photography programme.
- **Instagram:** started as Burbn, a cluttered check-in app; observed that photo sharing was the only well-liked feature; removed the rest; launched Instagram in October 2010; acquired by Facebook in 2012 for about $1 billion. This is a pivot driven by iteration.

**Link with design thinking:** the five stages (Empathize, Define, Ideate, Prototype, Test) are an iterative loop. Test results send you back to Empathize, Define or Ideate. Iterative design and design thinking both mean test, learn and improve.

**Iterative vs waterfall `[SELF]`:**

| | Iterative design | Waterfall |
|---|---|---|
| Flow | cycles, feedback loops | one-way sequence |
| User feedback | every cycle | at the end |
| Change cost | low, early | high, late |
| Risk | found early | found late |
| Scope | flexible | fixed |

---

### 3.4 Translating Prototypes into Software Architecture / Design Models  [NOTES; no PYQ; all `[SELF]` as question forms]

**Core idea:** this bridges UX and system engineering. The **prototype represents what the user experiences**; the **architecture and design models represent how the software will technically deliver that experience**.

Master pipeline (draw this):

```
 PROTOTYPE      USER TESTING        SOFTWARE           ARCHITECTURE        DESIGN MODELS
 (screens,  ->  FEEDBACK        ->  REQUIREMENTS   ->  (components,    ->   (UML: use case,
  flows)        (needs, pains)      (functional +       layers, style,       class, sequence,
                                     non-functional)    deployment)          state, ER)
```

**The 4-step translation process (from the v2 deck):**

**Step 1: Component decomposition (UI -> component architecture).**
- Break high-fidelity screens into reusable modular components using the atomic design levels: Atoms (buttons, inputs), Molecules (form groups, search bars), Organisms (navbars, data tables), Templates (page structures).
- Decide which state is local (a dropdown toggle) and which is global (logged-in user session, shopping cart) and keep global state in a state store.

**Step 2: Data modelling (UI forms -> database schemas).**
- Extract entities, attributes and relationships from forms and views.
- Convert forms to SQL tables or MongoDB documents with primary and foreign keys.
- Derive validation constraints (required fields, regex, data types) from the prototype's input specs.

**Step 3: API and sequence modelling (user interactions -> system messages).**
- Map action triggers (clicking "Submit Payment") to backend interactions.
- Draw UML sequence diagrams: chronological messages among Client UI, API Gateway, microservices, third-party APIs, database.
- Define API contracts (OpenAPI/Swagger): HTTP methods, request parameters, response headers, status codes, error payloads.

**Step 4: Architectural style and pattern selection (driven by non-functional requirements implied by the prototype).**
- Client-server / SPA: web and mobile dashboards with heavy client-side state.
- Microservices / event-driven: real-time processing, asynchronous jobs (notifications), independent service scaling.
- MVC or MVVM: separates View (presentation), Model (data) and Controller/ViewModel (business rules).

**Worked example (the deck's main case): Smart Crop Disease Detection System.**

*1. Start with the prototype.* Farmer opens app -> takes a leaf photo -> gets the disease name -> gets recommended action. Example output: tomato leaf, "Early Blight detected, 87% confidence", recommendation "Remove infected leaves and follow treatment". Questions asked at prototype stage: can the farmer take or upload the photo; is the result understandable; is the recommendation useful; can the farmer use it with limited technical knowledge.

*2. Convert user needs to requirements.*

| Farmer need | Software requirement |
|---|---|
| Take leaf photograph | Camera / image upload module |
| Quickly identify disease | AI/ML prediction service |
| Understand result | Simple result dashboard |
| Get treatment advice | Recommendation module |
| Poor internet | Offline / edge inference |
| Maintain crop history | Database |
| Receive alerts | Notification service |

*3. Prototype -> architecture (draw this):*

```
 FARMER
   |
   v
 MOBILE APP  (login, capture image, view result, crop history)
   |
   v
 IMAGE PROCESSING
   |
   v
 AI/ML MODEL (disease classifier)
   |                         \
   v                          v
 DISEASE DATABASE        RECOMMENDATION ENGINE
 (disease, symptoms,     (treatment, prevention)
  severity)                   |
         \                    v
          +-------------> FARMER DASHBOARD
```

*4. Architecture -> design models (UML):*
- **Use case diagram:** actor Farmer; use cases Login/Authenticate, Capture Leaf Image, Detect Crop Disease (includes View Disease Result and Advice), View Crop History. Detect Crop Disease `<<include>>` Consult Disease Database and Consult Recommendation Engine.

```
        +------------ Crop Disease Detection System ------------+
        |   ( Login / Authenticate )                            |
  [Farmer]-( Capture Leaf Image )                               |
        |   ( Detect Crop Disease ) --<<include>>--> ( Consult  |
        |        |  <<include>>                    Disease DB ) |
        |        +--> ( View Result & Advice ) --> ( Consult    |
        |   ( View Crop History )              Recommendation ) |
        +--------------------------------------------------------+
```

- **Class design (prototype concepts become classes):** Farmer (farmerId, name, location) 1 owns N Crop (cropId, cropName, cultivationDate); Farmer has LeafImage (imageId, imagePath, captureDate); LeafImage is analysed by DiseasePredictionAnalysis (diseaseName, confidence: Float, severity); it generates Recommendation (treatment, prevention, precautions).

```
 +-----------+ 1     N +----------+        +-------------+ analysed by +---------------------+
 | Farmer    |<>------>| Crop     |        | LeafImage   |------------>| DiseasePrediction   |
 | farmerId  |         | cropId   |        | imageId     |             | Analysis            |
 | name      |         | cropName |        | imagePath   |             | diseaseName         |
 | location  |-------->| cultiv.. |        | captureDate |             | confidence, severity|
 +-----------+  has    +----------+        +-------------+             +---------------------+
                                                                                  | generates
                                                                                  v
                                                                        +-------------------+
                                                                        | Recommendation    |
                                                                        | treatment,        |
                                                                        | prevention,       |
                                                                        | precautions       |
                                                                        +-------------------+
```

- **Sequence design ("Take photo -> Get result"):** lifelines Farmer, Mobile App, AI Model, Database.
  1. Farmer -> App: Take Photo; App -> Farmer: App Ready
  2. Farmer -> App: Input Crop Details
  3. App -> AI Model: Send Image and Crop Info; AI Model -> App: Analysis Prediction Result
  4. App -> Database: Store Full Diagnosis Result (farmer ID, crop ID, image path, disease, severity, recommendation); Database -> App: Success Confirmation
  5. App -> Farmer: View Disease Result and Advice

```
 Farmer        Mobile App         AI Model        Database
   |--Take Photo-->|                  |               |
   |<--App Ready---|                  |               |
   |--Crop details>|                  |               |
   |               |--Image+crop info->|              |
   |               |<--Prediction------|              |
   |               |--Store diagnosis----------------->|
   |               |<--Success------------------------|
   |<--Result + advice                |               |
```

**Four more examples from the deck (write any one with the same 6 headings: prototype, feedback, requirements, architecture, models):**

| Example | Prototype | Feedback | Requirements | Architecture | Design models |
|---|---|---|---|---|---|
| Food delivery | clickable screens: browse, cart, payment, live tracking | "Where is my order?", "slow at dinner time" | real-time tracking (functional); peak-hour load (non-functional) | client-server, API gateway, separate Order, Restaurant, Payment, Notification services; message queue for peaks; WebSockets for live location | use case (Customer, Restaurant, Rider), sequence "place order", class (Order, Cart, Payment), state (Placed -> Preparing -> Out for delivery -> Delivered) |
| Campus attendance | paper or Figma mock: tap names to mark, students see percentage | marking must take under 2 minutes; Wi-Fi unreliable | offline marking with later sync; bulk "mark all present" | layered or MVC with local device cache, sync service, REST backend | class (Student, Course, Session, AttendanceRecord), activity (mark and sync), deployment (mobile app, server, DB) |
| Hospital appointment | five-step booking flow tested with elderly users | got lost midway; want reminders; privacy worry | three-step booking, SMS reminders, role-based access | layered with authentication and authorisation module, external SMS gateway | sequence (booking and reminder), ER (Patient, Doctor, Slot, Appointment), state (Booked -> Confirmed -> Completed or Cancelled) |
| AI study assistant | Wizard of Oz chat with a hidden human | trust only if cites course material; some questions need a teacher | grounded answers, citations, escalation path | RAG pipeline: UI -> API -> retrieval service -> vector DB -> LLM -> response with citations; feedback logging | component diagram of pipeline, sequence (ask, retrieve, answer, escalate), class (Query, Document, Answer, Feedback) |

**Which UML model for what `[SELF]`:**

| Model | Question it answers | Derived from |
|---|---|---|
| Use case | who does what with the system | prototype flows and actors |
| Class / ER | what data and objects exist | forms and screens |
| Sequence | in what order do components talk | one user action (a button click) |
| State | what states does an object pass through | statuses visible in the prototype (order status) |
| Activity | workflow with decisions | multi-step user journeys |
| Component | major building blocks | decomposed UI and services |
| Deployment | what runs where | non-functional needs (offline, scale) |

**Mapping non-functional requirements to architecture `[SELF]`:** peak load -> queue and horizontal scaling; offline use -> local cache and sync; privacy -> authentication, role-based access; real time -> WebSockets or event-driven; low skill users -> simple UI but not an architecture issue, so it goes to the usability requirement.

---

### 3.5 Capstone Project: Applying Design Thinking to a Real-World Software Problem  [syllabus only; the slide is a title page; everything is `[SELF]`]

**What it is:** an end-to-end mini project where you run the whole design-thinking cycle on one real problem and end with a tested prototype plus architecture and design models. It ties Modules 1 to 5 together.

**Phase map with deliverables:**

| Phase | What you do | Deliverable |
|---|---|---|
| Empathize | interview and observe 5 to 8 real users | notes, empathy map, persona |
| Define | synthesise; write POV statement and "How Might We" | problem statement |
| Ideate | brainstorm, mind-map, morphological chart; select by criteria | shortlisted concept |
| Prototype | paper sketches, wireframes, storyboard, then clickable prototype | low and high-fidelity prototypes |
| Test | usability test (8-step process); collect feedback (think-aloud, SUS, SEQ) | test report with severity-ranked issues |
| Iterate | fix critical and major issues, re-test | version log and change log |
| Architect | requirements, architecture style, UML (use case, class, sequence), data model | design document |
| Present | demo, metrics, lessons learned | report and presentation |

```
 EMPATHIZE -> DEFINE -> IDEATE -> PROTOTYPE -> TEST -> ITERATE -> ARCHITECT & BUILD
     ^                                           |         |
     +-------------------------------------------+---------+  (feedback loops)
```

**Sample capstone (answer-ready): "Reduce missed medicine doses for elderly patients living alone."**
1. Empathize: 6 interviews and 2 home observations; finding: they forget, fear complex apps, rely on family. Persona: "Mr Sharma, 72, basic phone user".
2. Define: "Elderly patients living alone need a simple way to be reminded and to confirm doses because missed doses cause hospital visits. How might we make reminders effortless?"
3. Ideate: voice alarm, pill box with sensor, WhatsApp reminders, family dashboard; chosen by criteria (simplicity, cost, reliability).
4. Prototype: paper flow, then Figma with 3 screens and a large "Taken" button.
5. Test: 5 users, moderated think-aloud, tasks "set a reminder" and "confirm a dose"; metrics: completion 60% on first test, time 90 s, SUS 55.
6. Iterate: issues found (small font, hidden menu = Critical); fixed; re-test: completion 100%, SUS 82.
7. Architect: requirements (reminders, confirmation, family alert, offline), layered mobile architecture plus notification service and SMS gateway; UML use case (Patient, Caregiver), sequence (reminder -> confirm -> alert), class (Patient, Medicine, Schedule, DoseLog), state (Scheduled -> Notified -> Taken or Missed).

**Capstone report structure (10M answer outline):** problem and context; stakeholders and users; research findings; problem definition; ideas and selection; prototypes; test plan and results; iterations; architecture and design models; outcomes and metrics; limitations and future work.

**Likely viva questions:** which stage found the most useful insight; how many users and why; what changed between iterations; how did a usability finding change the architecture (for example offline sync); what would you do with more time.

---

## 4. PYQ SOLUTIONS (module-related only)

Papers covered: Jul 2024 ESE, Nov 2023 ESE (30.11.2023), Dec 2022, Nov-Dec 2021, Jul 2025 (PDF). May 2023 (Software Architecture and Design Thinking) has no question that maps to this module.

Grouping: A. Usability testing process; B. Types of usability testing; C. Dimensions / attributes of usability; D. Importance and short/fill-in; E. UAT.

Exam answer rule I follow below: definition first, then a diagram or table, then points, then an example. Marks guide: 10M is about 2 pages.

---

### A. Usability testing process

#### A1. "Explain the steps in Usability Testing Process." (10M) [Jul 2024 Q3-iii]
#### A2. "Explain the usability testing process in User Experience Design." (10M) [Jul 2025 Q4-i]

(Same answer. Use for both.)

**Introduction (2 lines).** Usability testing is the process of observing representative users perform realistic tasks on a product to find problems and improve the design. It is run as a planned sequence of eight steps, repeated in cycles.

**Diagram:**

```
 [1 Test plan] -> [2 Environment] -> [3 Participants] -> [4 Materials]
                                                              |
 [8 Report] <- [7 Analyse] <- [6 Debrief] <- [5 Conduct sessions]
     |
     +--> redesign --> re-test (iterate)
```

**Steps:**
1. **Develop the test plan.** The blueprint and main communication document for designers, developers, moderator and management. It states purpose and objectives, research questions, participant characteristics, method, task list, environment and logistics, moderator role, data and measures, and report format.
2. **Set up the testing environment.** Choose lab (permanent single-room set-up, where the moderator has close control) or the user's site (portable lab, which shows real context). Arrange cameras, screen recorder, props, and assign roles: moderator, note-taker, observers, product expert.
3. **Find and select participants.** Real, representative users matching the target persona and technical literacy (not developers); 5 to 8 per user group finds about 80 to 85% of problems.
4. **Prepare test materials.** Screening questionnaire, consent form, orientation script, task scenarios, prototype, data sheets, pre- and post-test questionnaires, debrief guide.
5. **Conduct the test sessions.** Greet and brief the participant ("we test the system, not you"), give realistic tasks, use think-aloud, stay neutral, avoid leading questions, record time, errors, completion and comments.
6. **Debrief the participant and observers.** Short interview ("What surprised you?"), satisfaction rating such as SUS, plus a team debrief the same day.
7. **Analyse data and observations.** Compute completion rate, time on task, error rate; collate qualitative notes; group problems and grade severity as Critical, Major or Minor; identify root causes.
8. **Report findings and recommendations.** Summary, method, prioritised issues with evidence, and recommended design changes; then iterate by fixing and re-testing.

**Example (one line each is enough):** testing a ride-booking app: tasks "book a cab to the airport" and "cancel a ride"; 6 users; found that the pickup pin is hard to move (Major) and fare estimate unclear (Critical); redesigned and re-tested.

**Conclusion.** Because usability testing is repeated with each design version, it is most effective when part of an iterative process.

---

#### A3. Nov 2021 Q3 (10M): bank application, "Write down clearly the assumptions and constraints of the system. Explain the types of usability testing and process."

**Assumptions:**
- Online bank application (mobile and web) for retail customers with typical facilities: login, balance, fund transfer, bill payment, statements.
- Users range from tech-savvy youth to senior citizens with low digital literacy; Indian context, English and regional language.
- Prototype exists at several fidelities; the bank can recruit its own customers.
- Security and regulatory rules (RBI, two-factor authentication) apply.

**Constraints:**
- Test sessions cannot use real money or real customer data (use a test sandbox and dummy accounts).
- Security and privacy: consent and anonymised recordings.
- Limited time and budget: 5 to 8 users per group; seniors may need in-person sessions.
- Cannot weaken security (OTP, session timeouts) just to improve usability.
- Network variability; accessibility needs.

**Types of usability testing (applied to the bank app):**

| Type | Applied to the bank app |
|---|---|
| Exploratory (formative) | early, with paper or clickable mock of "Transfer money"; 5 users think aloud; checks whether the flow and labels (for example "Beneficiary") are understood |
| Assessment (summative) | working prototype; users really add a payee and transfer; completion rate and time recorded; moderator interferes less |
| Validation (verification) | before release; benchmark such as 90% of users transfer money in under 90 s with no more than 1 error; no moderator help; confirms earlier problems are fixed |
| Comparison | old vs redesigned transfer screens (A/B), or against a competitor bank app |
| Moderated / unmoderated | moderated for seniors and complex tasks; unmoderated remote tests for quick checks of many customers |
| In-person / remote | in-person for non-verbal cues, remote for customers in other cities |

**Process:** show the 8-step diagram from A1 with a bank line each: plan (objective "reduce transfer drop-off", tasks, metrics); environment (branch usability room plus remote tool); participants (youth, working adults, seniors); materials (dummy accounts, consent, tasks); conduct (think-aloud, neutral facilitator); debrief (SUS and interview); analyse (completion %, errors at OTP step, severity); report and iterate (simplify beneficiary form, clearer error messages, re-test).

---

### B. Types of usability testing

#### B1. "Types of Usability Testing." (5M) [Jul 2024 Q5-v]

**Answer in 5M form.** Usability tests are classified by the stage of development they serve:
1. **Exploratory (formative) test:** very early, when requirements are done and design is about to start. Uses paper or static prototypes and heavy moderator-participant interaction with think-aloud. Checks whether the concept, workflow and navigation make sense. Mostly qualitative.
2. **Assessment (summative) test:** early to mid cycle, once high-level design is fixed. Users actually perform tasks, moderator interacts less, quantitative measures are collected. Evaluates lower-level operations.
3. **Validation (verification) test:** late, close to release. Measures the product against predefined benchmarks and confirms earlier problems are fixed with no new ones. Little or no moderator interaction; quantitative data is central.
4. **Comparison test:** any stage; compares two or more designs, or with a competitor, side by side, using performance and preference data.

Also by method: moderated vs unmoderated, and in-person vs remote.

Small diagram:

```
 Exploratory --> Assessment --> Validation        Comparison (any stage)
  (concept)      (tasks)        (benchmark)
```

#### B2. "Discuss why usability testing is an important part of UI/UX process. Elaborate on different types of usability testing." (10M) [Nov 2023 Q4-ii]

**Part 1: Importance (about 5 marks).**
1. Finds real problems before launch, when fixes are cheap; a design that looks right to designers often fails real users.
2. Replaces assumptions with evidence from representative users.
3. Improves usability dimensions: effectiveness, efficiency, learnability, memorability, error handling, satisfaction.
4. Reduces frustration and drop-off, so conversions and repeat sales rise (for example a confusing checkout loses buyers).
5. Cuts support calls and rework; builds a record of usability benchmarks for future releases.
6. Gives competitive edge, since usability is a market differentiator.
7. Builds a positive customer relationship by showing the organisation values users.
8. Supports the iterative UCD loop: test -> learn -> refine -> repeat.

**Part 2: Types (about 5 marks).** Give the classification and table from 3.1.7 (Exploratory, Assessment, Validation, Comparison; add moderated/unmoderated and in-person/remote in two lines). Use the lifecycle diagram from B1 and a one-line example for each (for example for an e-commerce app: exploratory = paper mock of the cart; assessment = users really check out; validation = 90% complete checkout in under 2 minutes; comparison = old vs new checkout).

#### B3. "Explain different types of usability testing with supporting examples." (10M) [Dec 2022 Q4-iii]

Use the full table in 3.1.7 (Classification 1, all four types with when, aim, prototype, moderator, data, example) plus Classification 2 (moderated, unmoderated, in-person, remote). Use these supporting examples:

| Type | Example |
|---|---|
| Exploratory | team shows paper sketches of a college-website menu to 5 students; asks them to think aloud |
| Assessment | students must actually "find the exam timetable"; time and clicks recorded |
| Validation | before launch: 90% of students must find the timetable in under 30 s; verified with 10 students without help |
| Comparison | top-navigation vs side-navigation layouts tested side by side |
| Moderated | researcher asks "Book a hotel for two people" and probes "Why did you click here?" |
| Unmoderated | participants complete an online usability test or survey alone via a platform |
| In-person | observe facial expression and hesitation on a kiosk |
| Remote | users in another city share the screen over video call |

Add the diagram from B1 and a one-line conclusion: choose the type by the lifecycle stage and what you need to learn.

---

### C. Dimensions / attributes of usability

#### C1. "Describe dimensions of Usability." (10M) [Jul 2024 Q4-ii]

**Definition.** Usability is the degree to which a product can be used by specified users to achieve specified goals with effectiveness, efficiency and satisfaction in a specified context (ISO 9241-11). It is made of several dimensions that must be blended appropriately.

**Diagram:** the six-box diagram from 3.1.2.

**Explain each (2 lines plus example):**
1. **Usefulness:** the product lets the user achieve their goals and they are willing to use it. A system that is easy but misses the user's goal is not used even if free. Example: a banking app without bill pay.
2. **Efficiency:** speed with which a goal is achieved accurately and completely; measured as time. Small savings per use add up. Example: one-tap repeat payment.
3. **Effectiveness:** the product behaves as the user expects; measured by error rate as a percentage of usage. Example: the "Back" button returns to the previous screen.
4. **Learnability:** ability to operate to a competent level with minimal training; infrequent users can relearn after a gap. Example: first-time user books a ticket without a manual.
5. **Satisfaction:** user feelings and opinions captured through questioning and rating (for example SUS). Example: rating the app after the task.
6. **Accessibility:** people of varied abilities can use it. Example: screen-reader support and high contrast.

Then add: Nielsen's five attributes are learnability, efficiency, memorability, errors and satisfaction; memorability means a returning user need not relearn.

**Conclusion.** A usable product balances all dimensions; usability testing measures them through completion rate, time, errors and questionnaires.

#### C2. "List and explain the key attributes of usability: effectiveness, efficiency and satisfaction." (5M) [Jul 2025 Q1-vi]

- **Effectiveness:** can users complete their tasks accurately and completely? Measured by task completion rate and error rate. Example: 9 of 10 users successfully book a ticket.
- **Efficiency:** the resources, mainly time and steps, needed to reach the goal once the user knows the system. Measured by time on task and number of steps. Example: booking in 3 taps instead of 7.
- **Satisfaction:** how comfortable and positive the user feels; measured through questionnaires such as SUS (0 to 100, average 68), SEQ, interviews and ratings. Example: users rate checkout 4.5/5.
- Together they form the ISO 9241-11 definition: a specified user, with specified goals, in a specified context of use. Other attributes: learnability, memorability, error recovery and accessibility.

---

### D. Importance and 1-mark questions

#### D1. "Usability testing refers to ___" (1M) [Nov 2021 Q1A-7]
**Answer:** the technique of evaluating a product by observing representative users perform realistic tasks to identify usability problems and improve the design.

#### D2. "A heuristic evaluation is a method of ___" (1M) [Nov 2021 Q1A-8]
**Answer:** usability inspection in which one or more experts review an interface against recognised usability principles (heuristics) to find problems, without involving end users. (It is one of the ten usability techniques in this module.)

---

### E. User Acceptance Testing

#### E1. "User Acceptance Testing." (5M) [Nov 2023 Q5-vi]  (answer is `[SELF]`; the slides do not cover UAT)

**Definition.** User Acceptance Testing (UAT) is the final phase of testing in which the actual client or end users verify, in a real or near-real environment, that the software meets the agreed business requirements and is fit for release. Passing UAT gives formal sign-off.

**Purpose:** confirm business needs are met, find gaps that developers and testers missed, reduce post-release risk, and build user confidence.

**Types:** alpha (internal users at the developer site), beta (real users at their own site), business acceptance, contract acceptance, regulatory acceptance, operational acceptance.

**Process (flow):**

```
 Define acceptance  ->  Prepare test cases  ->  Select users  ->  Execute  ->  Log defects
 criteria              from business cases                                          |
                                                                                    v
                                      Sign-off  <-  Retest  <-  Fix defects  <------+
```

**Example:** before a college ERP goes live, faculty and the exam cell run real scenarios (create timetable, enter marks, issue hall tickets); the exam controller signs off when all acceptance criteria pass.

**UAT vs usability testing:** UAT checks "does it meet requirements; accept or reject" with pass/fail criteria and is done at the end; usability testing checks "how easy, efficient and satisfying" and is done throughout, in iterations.

---

## 5. EXTRA PRACTICE QUESTIONS (all `[SELF]`; not from any PYQ)

Short answer points for each (5M unless noted).

1. **Nielsen's five usability attributes (5M).** Learnability, efficiency, memorability, errors, satisfaction, with a one-line meaning and an example each (see 3.1.2).
2. **Think-aloud protocol (5M).** Participants verbalise thoughts while performing tasks. Concurrent: live; retrospective: talk through a video replay. Reveals mental model and emotional friction. Facilitator stays neutral and does not rescue. Limits: can alter natural behaviour; some users go silent.
3. **Moderated vs unmoderated testing (5M).** Use the table in 3.1.7 (Classification 2). Choose moderated for complex flows and new users, unmoderated for speed and scale.
4. **Formative vs summative evaluation (5M).** Formative: early, shapes the design, qualitative, high moderator interaction. Summative: later, measures performance, quantitative, less interaction.
5. **Five Whys in user feedback (5M).** Ask "Why?" up to five times to reach the root cause. Example: "Checkout is confusing" -> hidden fee -> user expected the total earlier -> mismatch with other apps -> show the final price on the cart page.
6. **Explain SUS and compute a score (5M).** Ten statements, 1 to 5 scale, odd minus 1, even 5 minus response, total x 2.5; average 68 (see worked example 2).
7. **Explain A/B testing (5M).** Randomly show variants A and B to comparable users; compare a metric such as conversion; use statistical significance; change only one element at a time.
8. **Why is design iterative? List the benefits and limitations (10M).** Use 3.3 (why, 7 steps, merits, limitations, practices, one case).
9. **Local maxima trap (5M).** Iterative feedback keeps optimising small details (colour, copy) and misses a fundamentally better concept. Remedy: occasionally test radically different concepts (comparison test) and listen for latent needs.
10. **Translate a food-delivery prototype into design models (10M).** Use the 4-step translation plus the food-delivery row; draw the use case and one sequence diagram ("place order").
11. **Prototype vs architecture (5M).** The prototype shows what the user experiences; the architecture shows how the software delivers it; models (UML) document the structure and behaviour of each component.
12. **Role of sequence diagram in translating prototypes (5M).** Each user action in the prototype (such as "Submit payment") becomes a message sequence among UI, API gateway, services, third-party API and database; it also helps to define the API contract.
13. **Capstone (10M).** Apply the full cycle to one real problem: use the phase table and the elderly medicine reminder sample in 3.5.
14. **Choosing an architectural style from non-functional requirements (5M).** Use the Step 4 list: SPA or client-server for rich client state; microservices or event-driven for real time, async jobs, independent scaling; MVC or MVVM for clean separation of concerns.
15. **Limitations of usability testing (5M).** Artificial situation, does not prove a product works, participants rarely fully representative, not always the best technique.
16. **Walk-through vs usability test (5M).** Walk-through envisions the user's route through a concept and may be done by team members, so it is not a usability test; a usability test requires representative users performing tasks.

---

## 6. LAST-MINUTE REVISION SHEET

- **Usability test in one line:** real user + realistic task -> observe -> find problems -> improve.
- **ISO 9241-11:** effectiveness, efficiency, satisfaction (specified users, goals, context).
- **Nielsen 5:** Learnability, Efficiency, Memorability, Errors, Satisfaction. **Six dimensions:** Usefulness, Efficiency, Effectiveness, Learnability, Satisfaction, Accessibility.
- **Types:** Exploratory (formative) -> Assessment (summative) -> Validation (verification); Comparison cuts across. Also moderated/unmoderated and in-person/remote.
- **8-step process:** Plan -> Environment -> Participants -> Materials -> Conduct -> Debrief -> Analyse -> Report.
- **Test plan 9 parts:** purpose, research questions, participants, method, tasks, environment, moderator role, data and measures, report.
- **Severity:** Critical (blocks), Major (delays), Minor (cosmetic).
- **5 to 8 users per group = about 80 to 85% of issues.**
- **Feedback families:** qualitative (think-aloud, observation, I Like/I Wish), co-creation (card sorting, Wizard of Oz), post-task (debrief, Five Whys), quantitative (completion, time, errors, SUS, SEQ, CSAT, NPS, A/B, heatmaps, funnels, eye tracking).
- **SUS:** 10 items, 0 to 100, average 68. **SEQ:** one question, 1 to 7.
- **Iteration loop:** Test -> Learn -> Refine -> Repeat; 7 steps: Research, Ideate and prototype, User test, Analyse and refine, Design and implement, Launch and monitor, Iterate.
- **Iteration limitations:** cost, fatigue, local maxima, agile vs UX timelines and technical debt, stakeholder resistance, feedback bias.
- **Cases:** Slack (8 updates, 400 features, search time -62%), Airbnb ($200/week, photos, doubled), Instagram (Burbn pivot, 2010, $1B in 2012).
- **Prototype to architecture:** 1 Component decomposition (Atoms, Molecules, Organisms, Templates) -> 2 Data modelling -> 3 API and sequence modelling -> 4 Architecture style (Client-server/SPA, Microservices/Event-driven, MVC/MVVM). Then UML: use case, class, sequence, state, ER, activity, component, deployment.
- **Crop disease case:** photo -> mobile app -> image processing -> AI/ML model -> disease DB and recommendation engine -> dashboard; needs: camera, AI service, offline inference, history DB, alerts.
- **Most asked in PYQs:** usability testing types (4 papers), usability testing process (4 papers), dimensions/attributes (2 papers), UAT (1 paper).
