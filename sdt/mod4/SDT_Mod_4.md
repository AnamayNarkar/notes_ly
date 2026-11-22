# SDT_Mod_4 — Software Design Thinking, Module 4: Prototyping Techniques (09 hrs, CO3 / CO4 / CO5)

> **Sources I went through (all of them):**
> - `SDT Module 4_Prototyping TechniquesV3.pptx` (110 slides). I read the slide text and also looked at the image-only slides: wireframe samples for YouTube, login, homepage and dashboard; the mockup samples; the Agile login-screen output; the Hick's, visual-hierarchy, mental-model, feedback and error-prevention infographics; the Gestalt icon sheet; the localisation comic; and the iPhone police-sketch case-study diagram.
> - All PYQ papers in `../question_papers_all_time/`: 10 scanned screenshots and `User Experience Design.PDF`. These are User Experience Design (UXD) papers for Nov-Dec 2021, Dec 2022, Nov 2023, Jul-Nov 2024 and Jul-Nov 2025, plus one *Software Architecture & Design Thinking* paper (May 2023). The SADT paper is 100% architecture and is not used for this module.
> - I also looked at `../mod1`, `../mod2`, `../mod3` and `../mod5` to see what belongs where.
>
> **Honest note on the PYQs:** the old papers are for *User Experience Design*, not for this exact syllabus. Only questions that overlap with Module 4 are solved in Section 4. Overlap means wireframes, storyboards vs wireframes, prototyping tools, visual design principles, Gestalt, screen layout, information architecture, interaction design, interaction styles, widgets, feedback, UI vs UX and intuitive design/affordance. Questions on empathy maps, personas, user research, wicked problems, 5S model, heuristics, AR/VR/XR, use cases and usability testing belong to Modules 1, 2 and 5 (or other units). They are excluded and listed in Section 4.J so you can see I did not miss them.
>
> **Markers used everywhere (no emojis):**
> - **[PYQ]** = this topic and question type has appeared in an official PYQ (year given).
> - **[--]** = not asked yet in the PYQs, but possible or likely from the syllabus and slides.
> - **[ADDED]** = content or question that is NOT in the notes or official PYQs. I added it myself because the syllabus mentions the topic, or because a PYQ asked something the slides do not cover. Treat it as extra and verify against your own class notes if your faculty is strict.
> - **[NOTES]** = taken directly from the slides.

---

## 1. TOPIC MAP

```
MODULE 4 : PROTOTYPING TECHNIQUES
|
+-- 4.1 Types of prototypes : low-fidelity vs high-fidelity
|   +-- Classification basis : Fidelity (rough <-> realistic) and Purpose/form (what is tested)
|   +-- By FIDELITY
|   |   +-- Low-fidelity    : quick, cheap, rough (sketch, paper, storyboard, simple wireframe, role-play)
|   |   +-- Medium-fidelity : structure + some interactivity (greyscale wireframe with limited clicks, basic mockup)
|   |   +-- High-fidelity   : realistic look, feel, interaction (interactive prototype, real content, animation)
|   +-- By TYPE / PURPOSE (9 types)
|   |   +-- Sketches & diagrams        +-- Paper prototypes
|   |   +-- Storyboards                +-- Wireframes
|   |   +-- Clickable digital protos   +-- Physical models
|   |   +-- Role-playing / service     +-- Wizard-of-Oz
|   |   +-- User-driven / co-creation
|   +-- Low-fidelity in depth
|       +-- Forms : sketches, paper, storyboards, digital wireframes
|       +-- Characteristics (6)
|       +-- Merits (4)
|       +-- When to use / Not ideal for
|       +-- Limitations (5)
|
+-- 4.2 Tools for software prototyping
|   +-- Tool chain : Sketch -> Wireframe -> Mockup -> Clickable prototype -> Test -> Iterate
|   +-- Wireframes
|   |   +-- Definition; represents (placement, hierarchy, user journey)
|   |   +-- Does NOT focus on (visual styling, real interaction)
|   |   +-- Examples : mobile login | website homepage | dashboard (+ YouTube wireframe)
|   +-- Mockups
|   |   +-- Definition; represents look and feel
|   |   +-- Used for (visual validation, design-system alignment, bridge to interactive, branding test,
|   |   |             stakeholder buy-in, consistency check, developer handoff, A/B visual testing)
|   |   +-- Merits (4) | Limitations (4)
|   |   +-- Examples : food-delivery app | e-commerce checkout
|   +-- Clickable (interactive) prototypes
|   |   +-- Definition; features (simulated interactivity, no production code, variable fidelity)
|   |   +-- Merits (4) | Limitations (2)
|   |   +-- Software tools : Figma, Adobe XD, Axure RP, InVision, Sketch
|   +-- Comparison table : Wireframe vs Mockup vs Clickable (presents, fidelity, interaction,
|                          suitable for, audience, cost/time)
|
+-- 4.3 Agile and iterative prototyping
|   +-- Agile prototyping
|   |   +-- Definition; prototype = living artifact (build-measure-learn)
|   |   +-- Fidelity progression : low -> mid -> high (production-ready, MVP)
|   |   +-- Characteristics : hypothesis-driven, fail fast, throwaway vs evolutionary, cross-functional
|   |   +-- Example : login screen over Sprint 1 / 2 / 3
|   +-- Iterative prototyping
|       +-- Definition (build -> test -> feedback loop)
|       +-- Helpful in : unclear needs, usability testing, PoC, MVP
|       +-- Characteristics : cyclic refinement, progressive fidelity, hypothesis-driven,
|       |                     user-centric feedback loops, flexible scope
|       +-- Merits (5) | Limitations (6)
|
+-- 4.4 Interaction design and UI/UX considerations
|   +-- Interaction (integration) design  [slide 62-67]
|   |   +-- Definition; 4 principles (journey integration, cross-functional empathy,
|   |   |                             systemic feasibility, ecosystem consistency)
|   |   +-- Link with design-thinking phases (Empathise/Define, Ideate, Prototype, Test)
|   +-- Interaction design (classical)  [ADDED, asked in PYQ]
|   |   +-- 5 dimensions (1D words, 2D visuals, 3D space/objects, 4D time, 5D behaviour)
|   |   +-- Interaction styles | Widgets
|   +-- UI vs UX
|   +-- A. Usability and psychological principles
|   |   +-- Cognitive load : Hick's law, Miller's law
|   |   +-- Visual hierarchy & scanning : F-pattern, Z-pattern, levers
|   |   +-- Mental models : Jakob's law
|   |   +-- Feedback & system status : Nielsen heuristic #1
|   |   +-- Error prevention & recovery
|   +-- B. UI design principles
|   |   +-- Clarity, consistency, hierarchy, feedback, forgiveness, accessibility
|   |   +-- Visual elements : typography, colour system, grid & spacing
|   |   +-- Gestalt principles : proximity, similarity, continuity, closure,
|   |                            figure-ground, common region, common fate
|   +-- C. Visual design & interface foundations
|   |   +-- Colour theory (60-30-10) | Typography | Layout, grid, negative space | Micro-interactions
|   +-- D. Navigation, architecture & touch points
|   |   +-- Information architecture (card sorting, tree testing)
|   |   +-- Navigation patterns (wayfinding, breadcrumbs)
|   |   +-- Mobile-first & responsive (Fitts's law, 44x44 pt)
|   |   +-- Accessibility & inclusivity (WCAG 2.1 AA, 4.5:1)
|   +-- E. Workflow, conversion & content
|   |   +-- Form design | CTA | Onboarding & time-to-value | UX copywriting & microcopy
|   +-- F. Governance, testing & optimisation
|       +-- Design systems & component libraries
|       +-- Usability testing & analytics (5 users -> ~85%)
|       +-- Internationalisation & localisation (text expansion 40%, RTL, culture)
|       +-- Formatting standards (dates, numbers, currency, addresses, phones)
|
+-- 4.5 Rapid prototyping : case study in software development
    +-- Rapid prototyping concept : bridge between abstract ideas and human testing
    +-- Build (lowest fidelity) -> Test (real users) -> Learn (refine / pivot)
    +-- Principles : avoid debate, uncover flawed assumptions cheaply, hypothesis-driven, disposable
    +-- Case study : iPhone police-sketch software wireframes (6-stage process)
    +-- Supporting mini-case : mobile login screen (wireframe -> mockup -> agile prototype)
```

**Cross-module note:** usability testing in detail (types, process, UAT) belongs to Module 5 (Testing and Feedback). Storyboarding in detail and ideation tools belong to Module 3. In Module 4 you only need to know them as *prototype types*, and use them to answer comparison questions such as "wireframe vs storyboard".

---

## 2. TOPIC-WISE QUESTION TYPES

This subject has **no real numericals or derivations**. Question types seen in the PYQs are:
- short theory (5 M)
- long theory / explain (10 M)
- compare / differentiate
- illustrate with an example (often with a diagram)
- case / scenario application (10 M)
- list-and-describe
- "justify" statements
- MCQ / fill-in (1 M, 2021 paper)

Module 4 has a few "numeric-flavoured" facts: Hick's law, Fitts's law, 60-30-10, 4.5:1, 8-pt grid, 44x44 pt, 200-400 ms, 40% text expansion, 5 users = 85%. A short formula and number sheet is in Section 3 so you can quote them.

Legend: **PYQ(year)** = appeared. `.` = not asked yet but plausible. `--` = not applicable.

| Topic | Short note (5 M) | Long / explain (10 M) | Compare / differentiate | Case / scenario application | Diagram / illustrate | Justify / reason | MCQ / fill-in |
|---|---|---|---|---|---|---|---|
| 4.1 Types of prototypes (low vs high fidelity) | . | . | . (low vs high, very likely) | . | . (fidelity ladder) | . | . |
| 4.1 Low-fidelity: forms, merits, limits | . | . | . | . | . | . | . |
| 4.1 Storyboard as a prototype type | **PYQ(2022: "storyboard is a great way to tell stories")** | . | **PYQ(2025: wireframing vs storyboarding)** | . | . (frames) | **PYQ(2022: justify)** | **PYQ(2021 MCQ: wireframe & storyboard are static/dynamic tools)** |
| 4.2 Wireframes | **PYQ(2023 short note; 2021 advantages)** | . | **PYQ(2025 vs storyboard)** | . | **PYQ-implied: "draw neat diagrams"** | -- | **PYQ(2021 MCQ)** |
| 4.2 Mockups | . | . | . (wireframe vs mockup, very likely, slides 32/34/43-45) | . | . | . | . |
| 4.2 Clickable prototypes / prototyping tools | . | **PYQ(2023: characteristics of any two prototyping tools, 10 M)** | . (3-way table) | . | . | . | . |
| 4.3 Agile prototyping | . | . | . (agile vs iterative; throwaway vs evolutionary) | . (login screen sprints) | . (sprint loop) | . | . |
| 4.3 Iterative prototyping | . | . | . | . | . (build-test-learn loop) | . | . |
| 4.4 Interaction design: 5 dimensions | **PYQ(2024 short note; 2025 Q4iii 2+8 M with example)** | **PYQ(2025: illustrate its role with example)** | -- | **PYQ(2025: example)** | . | -- | -- |
| 4.4 Interaction styles | **PYQ(2023 list 5; 2024 importance; 2025 list 3)** | . | . | . | . | **PYQ(2024: "importance ... to improve UX")** | -- |
| 4.4 Widgets | **PYQ(2022 short note)** | **PYQ(2025: importance of widgets with example, 10 M)** | . | . | . | -- | **PYQ(2021 MCQ)** |
| 4.4 UI vs UX | **PYQ(2023: five points of difference; 2024: UX vs UI designer)** | . | **PYQ(2023, 2024)** | . | . | -- | **PYQ(2021 MCQ: UX design defined as)** |
| 4.4 UI design and goals | **PYQ(2022: what is UI design and its goals)** | . | . | . | . | . | -- |
| 4.4 Affordance / intuitive design | **PYQ(2023: affordance with example; intuitive design)** | . | . | . | . | -- | -- |
| 4.4 Feedback / system status | **PYQ(2023: role of feedback mechanism, 5 M)** | . | . | **PYQ(2023: download vs installation, time factor, 5 M)** | . (progress bar) | . | -- |
| 4.4 Cognitive load, Hick, Miller, Jakob | . | . | . | . | . | . | . |
| 4.4 Visual design principles / UI design principles | **PYQ(2024 Q1: design principles in brief; 2021 two principles)** | **PYQ(2024 Q4i 10 M; 2022 Q4i 10 M)** | -- | **PYQ(2021: ticket vending machine; 2025: Uber ride panel accessibility, 10 M)** | **PYQ-implied** | **PYQ(2021 Q1B)** | -- |
| 4.4 Gestalt principles | **PYQ(2022, 2023, 2025 - three papers)** | . | -- | -- | **PYQ(2025: illustrate any two with examples)** | -- | -- |
| 4.4 Colour, typography, grid, micro-interactions | . | . | . | . (embedded in visual-design answers) | . | . | . |
| 4.4 Screen design and layout | **PYQ(2024: importance of screen design and layout)** | . | . | . | . | . | -- |
| 4.4 Information architecture & navigation | . | **PYQ(2022 Q4ii: IA with bookstore sitemap; 2023 Q4i: user-context-content)** | . | **PYQ(2022: bookstore sitemap)** | **PYQ(2022: sitemap diagram)** | -- | -- |
| 4.4 Accessibility (WCAG), i18n/l10n | . | **PYQ(2025: visual design principles for accessibility, Uber)** | . | **PYQ(2025)** | . | . | . |
| 4.5 Rapid prototyping case study | . | . (very likely: "explain rapid prototyping with a case") | . | . | . (6-stage flow) | . | . |

**Hot-spot summary (by PYQ frequency, Module-4-relevant only):**
1. **Visual design principles**: 4 papers (2021, 2022, 2024, 2025). Often 10 M and often scenario based. This is the top priority.
2. **Gestalt principles**: 3 papers (2022, 2023, 2025).
3. **Wireframes**: 3 papers (2021, 2023, 2025), including wireframe vs storyboard.
4. **Interaction styles**: 3 papers (2023, 2024, 2025).
5. **Widgets**: 3 papers (2021 MCQ, 2022, 2025).
6. **Information architecture**: 2 papers (2022, 2023).
7. **5 dimensions of interaction design**: 2 papers (2024, 2025).
8. **UI vs UX**: 2 papers (2023, 2024).
9. Prototyping tools (2023), screen design and layout (2024), feedback mechanism (2023), affordance and intuitive design (2023), UI design and its goals (2022): 1 paper each.

**Exam pattern note:** every paper is "solve any 4 of 6 short" + "any 2 of 3 long (10 M)". Short notes at 5 M want about 5 crisp points plus a tiny diagram. Long answers at 10 M want an intro, a diagram, 6-8 points with an example and a conclusion. The instruction "Draw neat diagrams" is on every paper, so always sketch something.

---

## 3. TOPIC-BY-TOPIC DETAILED BREAKDOWN

### 3.0 What a prototype is, and why this module matters (read first)

A **prototype** is an early, inexpensive, testable version of a product. It is built to **ask a question** (for example, "Will users understand this checkout flow?"). It is not built to show off a finished solution. It is the "Prototype" stage of the Empathize -> Define -> Ideate -> **Prototype** -> Test loop. [NOTES, slide 106]

Why we prototype:
- Cheap to fix. Mistakes found on paper cost minutes, and mistakes found in code cost weeks.
- Replaces opinions with evidence from real users.
- Makes an abstract idea tangible so the team and stakeholders talk about the same thing.

Exam sentence you can reuse: *"A prototype is a tool to learn, not a product to ship. The lowest fidelity that answers the current question is the right fidelity."*

---

### 3.1 Types of Prototypes: Low-fidelity vs High-fidelity  (CO3)

#### 3.1.1 Classification basis [NOTES, slide 3]

Prototypes are classified on two bases:
1. **Fidelity**: how rough or realistic they are.
2. **Purpose / form**: what aspect of the solution is being tested.

#### 3.1.2 By fidelity [NOTES, slide 4]

```
 LOW FIDELITY ------------------> MEDIUM FIDELITY ------------------> HIGH FIDELITY
 sketch, paper, storyboard        greyscale wireframe,                 interactive app/web prototype,
 simple wireframe, role-play      limited clickable areas,             real content, animations,
                                  basic digital mockup                 near-final UI
 quick, cheap, rough              more structure, some interaction     detailed, realistic
 early idea exploration           refine flows & info. architecture    usability testing, stakeholder sign-off

 <-- faster, cheaper, easier to throw away          more realistic, costlier, harder to change -->
```

| Level | What it is | Examples | Used for |
|---|---|---|---|
| Low-fidelity | Quick, cheap, rough | Sketches, paper interfaces, storyboards, simple wireframes, role-plays | Early exploration of ideas, fast feedback |
| Medium-fidelity | More structure and some interactivity, not polished | Greyscale wireframes with limited clickable areas, basic digital mockups | Refining flows and information architecture |
| High-fidelity | Detailed and realistic in look, feel and interaction | Interactive app/web prototypes with real content, animations, near-final UI | Usability testing and stakeholder sign-off |

#### 3.1.3 By type / purpose (9 types) [NOTES, slides 5-7]

| # | Type | One-line meaning | Fidelity |
|---|---|---|---|
| 1 | Sketches and diagrams | Hand-drawn screens, flows or system maps to communicate concepts quickly | Low |
| 2 | Paper prototypes / paper interfaces | Hand-drawn screens that a facilitator "operates" while the user interacts | Low |
| 3 | Storyboards | Sequence of drawings showing the user's journey before, during and after using the solution | Low |
| 4 | Wireframes | Structural layouts of screens (often greyscale) to test hierarchy and layout without visual design | Low to Medium |
| 5 | Clickable digital prototypes | Linked screens in tools like Figma to simulate navigation and basic interactions | Medium to High |
| 6 | Physical models | 3D objects from cardboard, foam, 3D printing to test form, fit and handling | Varies |
| 7 | Role-playing / service prototypes | Acting out a service with real people and spaces to test the end-to-end experience | Low |
| 8 | Wizard-of-Oz prototypes | System looks automated, but a human performs the "backend" to validate the concept before building | Looks high, built cheap |
| 9 | User-driven / co-creation prototypes | Users help create or modify the prototype so designers learn their mental models | Varies |

Memory trick: **S-P-S-W-C-P-R-W-U** ("Super Paper Storyboards, Wireframes, Clickable, Physical, Role-play, Wizard, User-driven").

*Quick example for Wizard-of-Oz [ADDED]:* a "smart assistant" chatbot where a hidden team member types the replies. It tests whether users want the feature before an AI is built.

#### 3.1.4 Low-fidelity prototypes in depth [NOTES, slides 8-12]

- **Forms:** sketches, paper prototypes, storyboards, digital (greyscale) wireframes with placeholders.
- **Characteristics:**
  - Low visual detail.
  - Minimal or placeholder content.
  - Limited interaction.
  - Quick and inexpensive.
  - Easy to discard or modify.
  - Encourages discussion about structure rather than visual polish.
- **Merits:**
  - Fast and cost-effective, which enables rapid iteration.
  - Encourages collaboration, because non-designers can contribute.
  - Validates core concepts and user flows before investing in detailed design or code.
  - Reduces risk by exposing major usability issues and wrong assumptions early.
- **When to use:**
  - Early in the project (ideation, concept validation).
  - When you need to explore many alternatives quickly.
  - When testing information architecture and task flows.
- **Not ideal for:**
  - Testing detailed visual design, micro-interactions or performance.
  - Final stakeholder sign-off, or usability tests that need realistic interaction.
- **Limitations:**
  - Limited realism.
  - Cannot fully test visual design.
  - May not reveal detailed interaction issues.
  - Users may find it hard to imagine the final product.
  - Not suitable for final animations or micro-interactions.

#### 3.1.5 Low-fidelity vs High-fidelity: comparison table [ADDED, synthesised from slides 4, 8-12, 39-42; the syllabus title says "low vs high"]

| Aspect | Low-fidelity | High-fidelity |
|---|---|---|
| Look | Rough, greyscale, placeholders | Polished, brand colours, real content |
| Interaction | None or faked by a facilitator | Realistic (clicks, transitions, animation) |
| Tools | Pen and paper, sticky notes, whiteboard, wireframing tools | Figma, Adobe XD, Axure RP, InVision, coded HTML/React |
| Time and cost | Minutes to hours, very cheap | Days, costly |
| Ease of change | Redraw in minutes | Re-linking screens or re-coding |
| Stage of use | Early: ideate, concept check | Late: usability test, sign-off, developer handoff |
| Feedback you get | Structure, flow, concept, "does this idea make sense?" | Visual appeal, micro-interactions, realistic usability |
| Who can contribute | Anyone, including non-designers | Mostly designers and developers |
| Risk | Users cannot imagine the final product | Users and stakeholders think it is finished (scope drift) and fixate on trivial visual details |
| Best question to ask | "Are we building the right thing?" | "Is it usable and does it look right?" |

#### 3.1.6 How to write it in the exam
- **5 M "Types of prototypes":** a definition line, the fidelity ladder diagram (above), 3 rows (low, medium, high) with examples, and one line on purpose-based types.
- **10 M "Low vs high fidelity":** definition, ladder diagram, the comparison table (at least 8 rows), merits and limits of each, and a conclusion: "start low, increase fidelity as learning increases."

---

### 3.2 Tools for Software Prototyping: Wireframes, Mockups, Clickable Prototypes  (CO3/CO4)

#### 3.2.1 The tool chain [NOTES, slide 13]

```
 SKETCH ----> WIREFRAME ----> MOCKUP ----> CLICKABLE PROTOTYPE ----> TEST ----> ITERATE
 rough idea   structure &     polished     connected screens &       observe     improve and
              layout          visual       interactions              users,      test again
                              design                                 collect
                                                                     feedback
  low fidelity ------------------------------------------------------> high fidelity
```

One line to remember: **sketch = idea, wireframe = skeleton, mockup = skin, clickable prototype = behaviour.**

#### 3.2.2 Wireframes [NOTES, slides 14-24]

**Definition:** a simple, **static blueprint** showing the **structure and layout** of a screen or page before visual design and detailed interactions are added.

- Shows placement of navigation, content, controls and major components.
- Usually minimises colour, decoration and final imagery (boxes, lines and labels in greyscale).
- Represents three things: **Placement, Hierarchy, Users' Journey.**
- Does NOT focus on:
  - Visual styling (colours, fonts, branding, detailed graphics).
  - Real interactions or animations. Most wireframes are static, and any "clicks" are just links between screens.

**Example 1: Mobile login screen** (top to bottom) [NOTES, slides 18-19]

```
+----------------------------------+
|            [ LOGO ]              |  <- logo placeholder, top centre
|        Welcome back              |  <- headline
|                                  |
|  Email                           |
|  [ ______________________ ]      |  <- input with label
|  Password                        |
|  [ ______________________ ] (o)  |  <- show/hide option
|                  Forgot password?|  <- link under password
|  [        L O G   I N         ]  |  <- primary CTA, full width
|  ------ or continue with ------  |  <- divider
|  [  Google  ]   [  Facebook  ]   |  <- social login
|  Don't have an account? Sign up  |
|  Terms  |  Privacy               |  <- footer links
+----------------------------------+
```

**Example 2: Website homepage** [NOTES, slides 20-21]

```
+--------------------------------------------------------+
| [logo]   Product  Pricing  About        [Log in][Sign up]|  Header
+--------------------------------------------------------+
|          BIG HEADLINE  /  subheading                    |  Hero
|                 [ Get Started ]  (primary CTA)          |
+--------------------------------------------------------+
| [icon]      [icon]       [icon]       [icon]            |  Feature
|  title       title        title        title            |  highlights
|  text        text         text         text             |
+--------------------------------------------------------+
|   client logos  .  testimonials  .  key metrics         |  Social proof
+--------------------------------------------------------+
|      secondary headline     [ CTA button ]              |  CTA section
+--------------------------------------------------------+
| contact info   |  important links  |  social icons      |  Footer
+--------------------------------------------------------+
```

**Example 3: Dashboard** [NOTES, slides 22-23]

```
+--------------------------------------------------------+
| App name / logo                  Notifications | Profile |  Top bar
+----------+---------------------------------------------+
| Navigation| [Total Users] [Revenue] [Active Sessions]   |  Summary cards
|  Dashboard|                                              |
|  Reports  | +-----------------------------------------+ |
|  Settings | |  Chart title                [legend]    | |  Chart placeholder
|           | |     ~~~~ line / bar placeholder ~~~~    | |
|           | +-----------------------------------------+ |
|  (left    | | Name | Status | Date | Amount           | |  Table placeholder
|  sidebar) | | ---- | ------ | ---- | ------           | |
+----------+---------------------------------------------+
```

(The deck also shows a **YouTube wireframe** on slide 16: a header with search and upload buttons, a left menu, a large featured video box with an X placeholder, and rows of thumbnails as crossed boxes with grey text bars.)

**Merits of wireframes** [NOTES-derived and ADDED where marked]:
- Fastest and cheapest to create and iterate (slide 45).
- Focuses everyone on layout and content priority, not colours.
- Maps user paths and defines screen layouts (slide 44).
- Good for rapid brainstorming; product managers, UX designers and system architects can use them (slides 44-45).
- Communicates structure to developers and stakeholders [ADDED].
- Saves rework: changing a box costs minutes [ADDED].

**Limitations** [ADDED, consistent with slides 12 and 15]: no visual design or branding feedback, no real interaction, and users may find placeholders hard to imagine.

#### 3.2.3 Mockups [NOTES, slides 25-38]

**Definition:** a **static, detailed visual representation** of an interface (medium-to-high fidelity). It shows **colours, typography, images, spacing and visual hierarchy.** It usually has no functional interaction (no programming or interactive logic). It represents the **look and feel**.

**Mockups are used in / for:**
1. **Visual validation:** stakeholders and clients approve the exact look and feel before engineers write front-end code.
2. **Design-system alignment:** consistent typography scales, component libraries, spacing rules and brand guides.
3. **Bridge to interactive prototypes:** designers import mockups into Figma, Sketch or Adobe XD to add click transitions, hover states and animations. This turns a static mockup into a dynamic medium-to-high-fidelity prototype.
4. **Testing visual hierarchy and branding:** feedback on aesthetics, colour schemes, typography and clarity rather than interaction flow.
5. **Securing stakeholder buy-in:** non-technical stakeholders, clients and investors can visualise the product early.
6. **Validating design-system consistency:** buttons, cards and forms against design tokens, spacing rules and brand guidelines across viewports.
7. **Preparing assets for developers:** the visual blueprint at handoff, with pixel specifications, colour codes and padding.
8. **A/B visual testing:** quick preference tests between two visual directions (dark vs light mode, CTA placement).

**Merits** [slide 29]:
- Visual realism (branding, typography, colour scheme and hierarchy before development).
- Stakeholder alignment (a shared vision across design, product, engineering and marketing).
- Usability and aesthetics indication (visual clarity, readability, CTA contrast, trust signals such as client logos and testimonials).
- Cost-effective: editing static visuals is cheaper than rewriting HTML/CSS.

**Limitations** [slide 30]:
- Can distract stakeholders with minor visual details (icon style, exact colour shade) instead of core layout logic.
- May set unrealistic expectations if the visuals are hard for developers to implement.
- Lacks interactivity: no real-time testing of user behaviour, responsiveness, scroll behaviour or micro-interactions.
- Needs more time and effort than paper sketches or basic wireframes.

**Examples:**
- **Food-delivery app** [slide 35]: a pixel-perfect home screen inside a device frame, with high-resolution food photos, styled navigation bars, brand typography, a brand-orange "Order Now" button and accurate price layout. The purpose is to test aesthetic appeal, visual hierarchy and brand perception before front-end code.
- **E-commerce checkout rebrand** [slide 37]: high-fidelity desktop screens for cart, payment and confirmation, with real icon sets (shopping bag, lock), real product titles and prices (no Lorem Ipsum), full navigation headers and responsive breakpoints. The purpose is to validate trust, security cues and a clear CTA.

**Wireframe vs Mockup, the same login screen** (slide 32 shows both side by side): the wireframe is grey boxes and "Log in" in a dark bar, and the mockup has a brand logo, blue buttons, real Google/Apple icons and a phone frame.

#### 3.2.4 Clickable (interactive) prototypes [NOTES, slides 39-42]

**Definition:** a **functional simulation** of a digital product that lets users and stakeholders **interact with the design before any backend code is written.** It connects static UI screens (often derived from high-fidelity mockups) using **interactive hotspots, transitions and logic** to emulate a real experience.

**Features:**
- **Simulated interactivity:** tapping buttons, links or nav bars triggers screen transitions, overlays, dropdowns or modal pop-ups.
- **No production code:** built in Figma, Adobe XD, Axure RP or InVision with built-in triggers, not HTML/CSS/JS.
- **Variable fidelity:** from mid-fidelity (clickable greyscale wireframes testing navigation logic) to high fidelity (pixel-perfect with micro-animations and realistic data).

**Merits:**
- Easy user testing and validation (see where users get confused, stumble or fail tasks).
- A hands-on demo for stakeholders, which makes abstract ideas tangible.
- Developer handoff: an interactive reference for flows, modal behaviour and micro-interactions, better than static specs.
- Cost reduction: UX and architectural flaws caught now cost a fraction of refactoring production software.

**Limitations:**
- Dummy data and logic constraints: dynamic logic, complex inputs, real-time backend updates and DB queries cannot be fully simulated.
- Scope-drift risk: a high-fidelity clickable prototype looks finished, so stakeholders may mistake it for ready software.

**Software tools named in the slides** [NOTES]: **Figma, Adobe XD, Axure RP, InVision, Sketch.**

**Quick tool characteristics** (for the PYQ "characteristics of any two prototyping tools") [partly ADDED; see PYQ solution 4.B for the full answer]:
- **Figma:** browser-based, real-time collaboration, vector design, reusable components and auto-layout, prototype mode (hotspots, transitions, overlays), and developer handoff with inspect and specs.
- **Axure RP:** a desktop tool for high-fidelity interactive prototypes with conditional logic, variables, dynamic panels and form behaviour. It is more powerful but has a steeper learning curve.
- **Balsamiq** [ADDED, not in notes]: a sketch-style low-fidelity wireframing tool that deliberately looks hand-drawn so that people comment on structure, not looks.

#### 3.2.5 Comparison: Wireframe vs Mockup vs Clickable prototype [NOTES, slides 43-45]  [--]

| Aspect | Wireframe | Mockup | Clickable Prototype |
|---|---|---|---|
| Presents | Layout, structure, information architecture | Visual design, branding, typography, colour aesthetics | User experience, screen flows, interactive behaviour |
| Fidelity level | Low (greyscale, basic lines, simple shapes, placeholder text) | Medium to High (pixel-perfect graphics, brand colours, real content) | High (visuals combined with interactive micro-animations) |
| Interaction | None (static blueprint) | None (static image) | High (clickable hotspots, modal triggers, dynamic state changes) |
| Suitable for | Rapid brainstorming, mapping user paths, defining screen layouts | Aligning visual identity, stakeholder reviews, design-system setup | Usability testing with target users, developer handoffs |
| Suitable audience | Product managers, UX designers, system architects | Visual designers, marketing teams, brand stakeholders | Target users, usability testers, front-end developers |
| Creation cost and time | Fastest and cheapest to create and iterate | Moderate time for visual precision | Higher time to link screens, logic and state transitions |

How to write it: always reproduce the table (6 rows) and add a closing line: *"Hence the progression is wireframe (what goes where) -> mockup (how it looks) -> clickable prototype (how it behaves)."*

---

### 3.3 Agile and Iterative Prototyping  (CO4/CO5)

#### 3.3.1 Agile prototyping [NOTES, slides 46-53]

**Definition:** a quick, interactive model of a product (or feature) built **early** to test ideas, gather user feedback and refine requirements, then **iteratively improved within short Agile cycles (sprints).**

- Links two things: the human-centred design-thinking loop (Empathize -> Define -> Ideate -> **Prototype** -> Test) and Agile, which delivers working software in short cycles.
- The Prototype becomes a **living artifact** that evolves **sprint by sprint**, not a throw-away mockup. It is continuously tested with users and updated, matching Agile's **build-measure-learn** rhythm.
- Instead of a static design artifact made before coding, it is a **living, evolving asset** built to test hypotheses and refine features in sprints.

**Fidelity progression inside Agile** [slide 48]:

```
 LOW-FIDELITY FIRST         MID-FIDELITY                    HIGHER-FIDELITY (production-ready)
 sketches, paper,           figma wireframes &              working code, APIs, staging environments,
 storyboards, simple        clickable prototypes ->         MVPs  -> validate technical feasibility,
 clickable wireframes       test navigation flow,           live data integration, performance
 -> validate core idea      layout, info architecture;
    quickly                 React/HTML/CSS -> test visual
                            design, micro-interactions,
                            front-end usability
```

**MVP (Minimum Viable Product)** [slide 48]: the simplest version of a new product with just enough features to satisfy early users.

**Characteristics of an Agile prototype** [slide 49]:
1. **Hypothesis-driven:** built to answer a specific design or technical question (e.g. "Will users understand this two-step checkout flow?").
2. **Fail fast, learn faster:** UX friction and technical roadblocks are found in early sprints instead of after launch.
3. **Throwaway vs evolutionary:**
   - *Throwaway:* built quickly to test a radical idea and discarded after learning.
   - *Evolutionary:* refined sprint by sprint until the code becomes part of the final release.
4. **Cross-functional collaboration:** UX designers, product managers and engineers build and evaluate together so the design matches technical feasibility.

**Worked example: Login screen across 3 sprints** [slides 50-53]

```
 Wireframe (grey boxes) --> Mockup (branded, phone frame) --> Agile prototype (working HTML page)

 Sprint 1 : Validate basic visual layout, input fields, password toggle, social-button arrangement
 Sprint 2 : Validation and feedback -> field focus states, keyboard overlays on mobile,
            error messages (e.g. "Invalid Email format")
 Sprint 3 : Integration -> real authentication backends (OAuth for Google/Apple, JWT tokens for Email/Password)
```

(Slide 52 shows the output: an actual coded HTML login page, "AgilePrototypeExample1.html".)

**Sprint loop diagram** [ADDED, to draw in the exam]:

```
        +--> BUILD (smallest prototype that answers the hypothesis)
        |         |
        |         v
     LEARN <--- MEASURE / TEST with real users  <-- sprint (1-4 weeks)
   (refine, pivot,
    or promote to production)
```

#### 3.3.2 Iterative prototyping [NOTES, slides 54-61]

**Definition:** a **living model** of a product that undergoes **continuous refinement through repeating loops of building, testing and feedback.** Instead of trying to get the design perfect in one pass, teams build early, test with real users, gather insights and put them straight into the next iteration.

```
   BUILD ---> TEST ---> LEARN ---> ADAPT ---> (next version) ---> BUILD ...
   (cyclic refinement : Build -> Test -> Learn -> Adapt)
```

**Helpful in** [slide 55]:
- **Exploring unclear user needs:** vague, complex or fast-changing requirements.
- **Usability and UX testing:** new interaction patterns, navigation hierarchies or layouts before full front-end development.
- **Feasibility proofs (Proof of Concept, PoC):** can the design integrate with back-end APIs, databases or performance limits?
- **MVP development:** refining core features through beta releases before a wider rollout.

**Characteristics** [slides 56-57]:
- **Cyclic refinement:** repeated Build -> Test -> Learn -> Adapt loops that reduce development risk.
- **Progressive fidelity:** evolves from low-fidelity wireframes or paper sketches into high-fidelity, coded interfaces.
- **Hypothesis-driven:** each release tests a specific assumption about user behaviour, navigation flow or feature usability.
- **User-centric feedback loops:** decisions are validated by real users, not internal assumptions.
- **Flexible scope:** features and UI adapt without heavy refactoring or financial sunk costs.

**Merits** [slides 58-59]:
1. **Reduces development risk:** usability flaws and technical limits show up early, when fixes are cheap.
2. **Eliminates assumptions:** replaces subjective opinions with empirical evidence from user behaviour.
3. **Accelerates time-to-market:** core functionality is validated and launched incrementally while secondary features keep iterating.
4. **Aligns design and engineering:** continuous collaboration between designers, developers and product managers.
5. **Higher user adoption:** end users test throughout, so the product matches their mental models and workflows.

**Limitations** [slides 60-61]:
1. **Scope creep and feature bloat:** endless feature requests blur the vision.
2. **Higher resource and time overhead:** constant redesign, re-test and re-code.
3. **Refactoring and code debt:** coded prototypes modified across sprints leave messy front-end architecture.
4. **Stakeholder and user fatigue:** repeatedly showing raw or half-built prototypes.
5. **Local-maxima trap:** incrementally polishing a flawed concept stops the team from finding a radically better one.
6. **Difficulty in fixed-budget planning:** final requirements emerge only over time, so cost and date estimates are hard.

#### 3.3.3 Agile vs Iterative prototyping, and Throwaway vs Evolutionary [ADDED, synthesised from slides 46-61; very likely compare questions]

| Basis | Agile prototyping | Iterative prototyping |
|---|---|---|
| Core idea | Prototype evolves sprint by sprint inside Agile delivery | Repeated build-test-feedback loops until the design is right |
| Time-box | Fixed-length sprints | Loops of any length; no fixed time-box required |
| Link to delivery | Tied to working software increments, MVP, production | Can be purely a design activity (paper, wireframes) |
| Team | Cross-functional (UX, PM, engineers) | Mostly designers and testers, with developers joining later |
| Fidelity | Low -> mid -> high across sprints | Progressive fidelity |
| Main risk | Rushing; prototype code becoming production code | Scope creep, fatigue, local-maxima trap |

| Basis | Throwaway prototype | Evolutionary prototype |
|---|---|---|
| Purpose | Test a radical idea or a risky requirement | Become the final product by refinement |
| After testing | Discarded | Refined sprint by sprint |
| Code quality | Quick and dirty is acceptable | Must be clean enough to ship |
| Typical fidelity | Low (paper, sketch) | Mid to high (working code) |

#### 3.3.4 How to write it in the exam
- **5 M "Agile prototyping":** definition, "living artifact / build-measure-learn", the low -> mid -> high progression, and the 4 characteristics.
- **10 M "Explain Agile and iterative prototyping":** both definitions, the sprint loop diagram, the login 3-sprint example, merits and limits of iterative, and the comparison table. Close with: *"Prototyping in Agile is a continuous, hypothesis-driven loop, not a one-time deliverable."*

---

### 3.4 Interaction Design and UI/UX Considerations  (CO4/CO5)

This is the biggest sub-topic in the slides (slides 62-105) **and it carries the highest PYQ density** (visual design principles, Gestalt, interaction styles, widgets, IA).

#### 3.4.1 Interaction design as "integration design" [NOTES, slides 62-67]

In this module's slides, "Interaction design" is presented as **integration design**:
- It focuses on how distinct software systems, subsystems, microservices or third-party APIs **connect and exchange data seamlessly.**
- Good integration design ensures data flows **reliably, securely and scalably** without breaking the user experience or system stability.
- It **bridges human-centred user experiences with technical, operational and system-level execution.**
- Design thinking centres on user needs and software architecture centres on system connections. Integration design **synthesises both**, so complex back-end connections give frictionless, cohesive user touchpoints.

**Four fundamental principles:**
1. **User journey integration:** map how data moves across channels, devices or microservices so the user sees one seamless flow, not disconnected silos.
2. **Cross-functional empathy:** design integrations with empathy for end users and also for developers, business partners and system administrators who maintain the ecosystem.
3. **Systemic feasibility:** validate early whether third-party APIs, legacy databases or hardware can deliver the required experience in real time.
4. **Ecosystem consistency:** consistent logic, visual design tokens and user expectations across all touchpoints (mobile app, web dashboard, third-party extensions).

**Design-thinking phase vs integration focus** [slides 66-67]:

| Phase | Integration focus |
|---|---|
| Empathise and Define | Identify friction points where users switch between disconnected systems or repeat data entry because of poor integration |
| Ideate | Brainstorm solutions that use API capabilities, automation and real-time data synchronisation across platforms |
| Prototype | Build connected prototypes using mock APIs, webhooks or integration tools to test multi-system user flows early |
| Test | Evaluate real-world network latency, data-delay effects on UX, error-state recovery and edge cases with actual users |

#### 3.4.2 Interaction design in the classical sense [ADDED: not in slides, but PYQ-asked in 2024 and 2025]

**Interaction Design (IxD)** is the design of how a user and a product communicate: what the user does, how the system responds and how the exchange feels.

**The Five Dimensions of Interaction Design** (Crampton Smith and Silver) [PYQ 2024 Q5vi (5 M), 2025 Q4iii (2 + 8 M)]:

| Dimension | Meaning | Example (online food-ordering app) |
|---|---|---|
| 1D: Words | Text, labels, button text, messages | "Add to cart", "Order placed" |
| 2D: Visual representations | Graphics, icons, images, layout, typography | Food photos, cart icon, rating stars |
| 3D: Physical objects or space | The device or physical context the user interacts with | Phone held in one hand, thumb reach, a smartwatch, a kiosk |
| 4D: Time | How the interface changes over time: animation, progress, sound, response speed | Order-tracking progress bar, loading animation, notification sound |
| 5D: Behaviour | How the user acts and how the system reacts; feedback and the emotional exchange | Tap "Place order" -> button changes to "Processing" -> confirmation screen; undo within 10 s |

Mnemonic: **W-V-P-T-B** ("Words, Visuals, Physical, Time, Behaviour").

**Interaction styles** (the ways a user instructs the system) [PYQ 2023 Q1iv list five; 2024 Q5i importance; 2025 Q5i list three]:

| Style | Description | Example | Good for / drawback |
|---|---|---|---|
| Command-line | The user types commands | Linux terminal, `git commit` | Powerful and fast for experts; hard for novices |
| Menu selection | The user chooses from a list of options | ATM menu, restaurant-app menus | Easy to learn, low memory load; slow for deep menus |
| Form fill-in | The user fills fields | Registration, bank-transfer form | Structured data entry; tedious if long |
| Direct manipulation | The user acts on visible objects (drag, drop, pinch, resize) | Dragging files, pinch-to-zoom, Figma canvas | Intuitive, immediate feedback; needs good graphics |
| Natural language / voice | The user speaks or types free text | Alexa, Siri, chatbots | Very natural; ambiguity and errors |
| WIMP / touch / gesture | Windows, Icons, Menus, Pointer; touch swipes and taps | Desktop GUI, smartphone | Familiar; limited by screen size |

Why they matter (importance for UX, the 2024 wording): the right style reduces learning time and errors, matches user expertise (expert -> command or shortcut, novice -> menu or form), supports efficiency and satisfaction, and ensures accessibility (voice for visually impaired users).

**Widgets** [ADDED; PYQ 2022 Q5iii, 2025 Q4ii (10 M), 2021 MCQ Q6]:
- A **widget** is a reusable on-screen interface element that lets a user perform a function or access a service (the 2021 MCQ definition).
- **Examples:** button, text box, checkbox, radio button, drop-down list, slider, toggle switch, date picker, tab bar, progress bar, tooltip, carousel, search box.
- **Importance in interaction:**
  - Familiarity (Jakob's law): users already know how a checkbox or slider behaves.
  - Affordance: a slider invites dragging, a button invites pressing.
  - Speed and accuracy: a date picker prevents format errors.
  - Consistency across the product through component libraries and design systems.
  - Feedback: hover, pressed, disabled and error states.
  - Faster development: reuse reduces cost.
- **Choosing the right widget (example):** radio buttons for 2-5 mutually exclusive options, checkboxes for multi-select, a dropdown for long lists, a toggle for on/off, a slider for ranges.

#### 3.4.3 UI vs UX [NOTES, slide 69]  [PYQ 2023 Q1i, 2024 Q1iii, 2021 MCQ]

- **UI (User Interface):** the visual layout, typography, colour palettes, micro-interactions and aesthetics. It connects the user to the system.
- **UX (User Experience):** the user's **journey** while using the system: information architecture, user flows, accessibility, usability and emotional impact.
- Design thinking is **user-centric (human-centric)**; the focus is on user **needs, goals, expectations and feelings** (slide 70).

| Point | UI | UX |
|---|---|---|
| Meaning | Look and interactive layer of the product | Whole experience before, during and after use |
| Focus | Visual layout, typography, colour, micro-interactions | Information architecture, user flows, usability, accessibility, emotion |
| Scope | Narrow: the screens and controls | Broad: includes research, flows, support, service |
| Question answered | "How does it look and respond?" | "How does it feel to achieve my goal?" |
| Main activities [ADDED] | Style guides, mockups, component design, branding | User research, personas, journey maps, wireframes, usability testing |
| Deliverables [ADDED] | Mockups, design system, icon sets | Research reports, flows, wireframes, test results |
| Analogy [ADDED] | Car's dashboard, seats and body | The entire driving experience |

#### 3.4.4 A. Usability and Psychological Principles [NOTES, slides 71-81]

**A1. Cognitive load management**
- **Hick's Law:** the more choices, the longer the decision time, so minimise options per screen. (Infographic on slide 73: a 20-option pricing table with high cognitive load vs a clean 3-option "Select Your Subscription" screen.)
- **Miller's Law:** an average person holds about **7 +/- 2 items** in working memory, so chunk information.

**A2. Visual hierarchy and scanning**
- **Reading patterns:** the **F-pattern** for text-heavy content; the **Z-pattern** for landing and promotional pages.
- **Levers** (what you adjust to control what the user looks at first, second and last): **scale, contrast, weight and white space.**

**A3. Mental models and familiarity**
- **Jakob's Law:** users spend most of their time on other sites, so leverage existing design patterns. *Application:* do not reinvent common UI elements (shopping carts, search bars).

**A4. Feedback and system status**
- **Nielsen's Heuristic #1 (visibility of system status):** keep users informed in real time.
- **Techniques:** loading spinners, progress indicators, active-state animations, immediate input validation.

**A5. Error prevention and recovery**
- **Prevention:** smart defaults, sensible constraints, confirmation modals for destructive actions (for example "Delete account?").
- **Recovery:** human-readable error messages with explicit steps to fix the issue (not "Error 404. Good luck.", as the slide 81 infographic mocks).

**Formula and number sheet** [ADDED, for quick quoting and for numerical-flavoured questions]:

| Law / rule | Formula or number | Meaning |
|---|---|---|
| Hick's law | T = b x log2(n + 1) | Decision time T grows with the number of equally likely choices n; b is a constant |
| Fitts's law | T = a + b x log2(2D / W) | Time to hit a target grows with distance D and shrinks with target width W; make targets big and close |
| Miller's law | 7 +/- 2 | Items of working memory |
| Touch target | minimum 44 x 44 pt | Ergonomic touch target (slide 98) |
| Contrast | at least 4.5 : 1 | WCAG AA text contrast |
| Colour split | 60 / 30 / 10 | Dominant / secondary / accent |
| Grid | 8-pt or 4-pt base | Spacing and sizing multiples |
| Line height | 1.4 to 1.6 x font size | Readability |
| Line length | 45 to 75 characters | Readability |
| Type scale | 1.250 ("major third") | Each size = previous x 1.25 |
| Animation | 200 to 400 ms | Micro-interaction duration |
| Text expansion | up to 40% | Translated text growth |
| Usability test | 5 users ~ 85% of issues | Diminishing returns |

**Mini-numerical [ADDED]:** *Using Hick's law with b = 0.2 s, compare a menu with 7 options and a menu with 15 options.*
- n = 7: T = 0.2 x log2(8) = 0.2 x 3 = **0.6 s**
- n = 15: T = 0.2 x log2(16) = 0.2 x 4 = **0.8 s**
- Cutting 15 options to 7 saves about 0.2 s per decision, which is a 25% reduction. The principle is to chunk and prioritise.

**Mini-numerical on type scale [ADDED]:** body 16 px on a 1.250 scale. H3 = 16 x 1.25 = 20 px, H2 = 20 x 1.25 = 25 px, H1 = 25 x 1.25 = 31.25 px (about 31 px).

#### 3.4.5 B. UI Design Principles [NOTES, slides 82-88]  **[PYQ-heavy: 4 papers]**

**Core principles** (slides 82-83):
1. **Clarity and simplicity:** remove visual noise so users can reach their primary goal without cognitive overload.
2. **Consistency:** uniform typography, colour, spacing and interaction patterns (buttons, navigation) across all screens.
3. **Visual hierarchy:** use size, scale, contrast, weight and placement to direct attention to the most important element first.
4. **Feedback and response:** immediate visual or haptic feedback (spinners, active button states, success messages).
5. **Forgiveness and error prevention:** confirmation dialogs, input validation and easy **undo**.
6. **Accessibility (a11y):** proper colour-contrast ratios, screen-reader compatibility and accessible touch targets.

**Visual elements to standardise** (slide 84):
- **Typography:** a clear hierarchy using distinct font sizes, line heights and weights for headings, subheadings and body.
- **Colour system:** a primary brand colour, secondary supporting colours, neutral background tones and explicit **status colours** (success, warning, error).
- **Grid and spacing:** a consistent grid (4 px or 8 px base) for proportional alignment and padding.

**Additional visual-design principles that exams often list** [ADDED, not in these slides but standard in UXD syllabi]:
- **Contrast:** differences in size, colour or weight make key elements stand out.
- **Balance:** symmetrical or asymmetrical distribution of visual weight.
- **Alignment:** elements aligned to a common edge or grid look ordered.
- **Proximity and grouping:** related items are placed together (also a Gestalt principle).
- **White (negative) space:** breathing room that improves comprehension.
- **Repetition / rhythm:** repeating patterns create unity.
- **Emphasis / focal point:** one dominant element per screen.

**Gestalt principles** (slides 85-88): "the whole is other than the sum of the parts." The human brain organises individual visual elements into a **structured, unified whole** rather than seeing disconnected parts. In UI design these principles dictate how users perceive relationships, hierarchy and grouping.

| Principle | Meaning | UI example |
|---|---|---|
| Proximity | Objects close together are perceived as a group | Label placed just above its input field; related settings kept together |
| Similarity | Elements sharing colour, shape, size or style are seen as having the same function | All primary buttons are blue and rounded; all links are underlined |
| Continuity (good continuation) | The eye follows smooth, continuous paths or lines | Carousel or horizontal card list that runs off the edge; a progress stepper line |
| Closure | The brain fills in missing parts to see a complete shape | The WWF panda logo, a loading ring with a gap, a card list cut off at the edge |
| Figure-ground | The mind separates foreground (focus) from background | Modal dialog over a dimmed page; white card on a grey background |
| Common region | Elements inside the same enclosed boundary belong together | Items in a card or a bordered box (shipping address block) |
| Common fate | Elements that move in the same direction or at the same speed are grouped | Menu items sliding in together; list items swiping off together |

(The slide 88 icon sheet also shows **Good Figure / Pragnanz** (simplest form), **Proximity, Similarity, Continuation, Closure and Symmetry**. If asked for "any two Gestalt principles", proximity and similarity are the safest picks.)

**How to draw Gestalt in the exam** [ADDED]:
```
 Proximity                 Similarity                 Common region
 o o o     o o o           o x o x o                  +---------+  +---------+
 o o o     o o o           x o x o x                  | o  o  o |  | x  x  x |
 (two groups)              (rows by shape)            +---------+  +---------+
```

#### 3.4.6 C. Visual Design and Interface Foundations [NOTES, slides 89-95]

1. **Purposeful colour theory:**
   - *Function over form:* use colour to indicate state (success, warning, error) and visual importance.
   - **60-30-10 rule:** 60% dominant colour, 30% secondary structure colour, 10% high-contrast accent colour.
   - *Colour psychology (slide 90):* blue = calm, trust, competence; red = strength, energy; green = nature, freshness; yellow = joy, warmth; black = style, elegance; pink = femininity, compassion, and so on.
2. **Typography and hierarchy:**
   - *Readability:* high contrast, line height 1.4-1.6x, line length 45-75 characters.
   - *Scale:* use a modular type scale (for example 1.250 major third) for consistent sizing. (Slide 92 shows Title / Subheading / Text levels.)
3. **Layout, grids and spatial cadence** (the rhythm, flow and structural repetition of elements in a space):
   - *Grid systems:* 8-pt or 4-pt grids align margins, padding and component sizes.
   - *Negative space:* active white space groups related items and reduces clutter.
4. **Micro-interactions and animation:**
   - *Purpose:* instant feedback, show spatial relationships, delight the user.
   - *Constraint:* keep animations short (**200-400 ms**) with realistic easing; never delay the user's task.

#### 3.4.7 D. Navigation, Architecture and Touch Points [NOTES, slides 97-98]

**D1. Information Architecture (IA)**
- *Structural clarity:* group related concepts logically using intuitive labels and categories.
- *Testing:* validate IA with **card sorting** and **tree testing** with real users.
- **IA = how content is organised, labelled and connected.** It is shown as a **sitemap** [ADDED explanation].
- **IA is built from three inputs: Users, Context, Content** (the classic Morville and Rosenfeld IA Venn diagram) [ADDED, PYQ 2023 Q4i]:

```
          +-----------+
          |   USERS   |   who they are, needs, tasks, vocabulary
          +-----+-----+
          (  GOOD   )
   +------+  IA   +-----+
   |CONTEXT|       |CONTENT|
   +-------+       +-------+
   goals, business,   type, volume, structure,
   constraints,       ownership of content
   culture
```

- **IA components** [ADDED]: organisation systems (how content is grouped), labelling systems (names), navigation systems (how to move) and search systems.

**D2. Navigation patterns**
- *Wayfinding:* users always know where they are, where they have been and where they can go next.
- Achieved with **top bars, bottom tab bars (mobile), sidebars (dashboards) and breadcrumbs.**
- **Breadcrumb:** a secondary navigation trail showing the user's location in the site hierarchy (Home > Books > Fiction > Novel).

**D3. Mobile-first and responsive design**
- **Fitts's Law:** ergonomic touch targets must be easy to reach (minimum **44 x 44 pt**).
- **Adaptability:** scale gracefully across breakpoints (mobile, tablet, desktop, ultra-wide).

**D4. Accessibility and inclusivity**
- **WCAG** (Web Content Accessibility Guidelines): target **WCAG 2.1 AA** as a baseline.
- *Core criteria:* screen-reader support, keyboard navigation, colour contrast of at least **4.5 : 1**, and dynamic text sizing.

#### 3.4.8 E. Workflow, Conversion and Content Strategies [NOTES, slides 99-100]

- **Form design and input efficiency:**
  - *Friction reduction:* single-column layouts, inline validation, clear labels, smart autocomplete.
  - *Progressive disclosure:* break complex forms into multi-step wizards.
- **Call-to-action (CTA) optimisation:**
  - *Clarity:* action verbs ("Start Free Trial", "Submit").
  - *Hierarchy:* one primary action per screen view; visually demote secondary actions.
- **Onboarding and time-to-value:**
  - *First impressions:* deliver value before asking for heavy data entry or sign-up.
  - *Methods:* interactive walkthroughs, empty states with clear actions, progressive profiling.
- **UX copywriting and tone:**
  - *Clarity first:* replace jargon with concise, conversational language.
  - *Microcopy:* helpful tooltips, placeholder text, reassuring security cues near high-friction steps.

#### 3.4.9 F. Governance, Testing and Optimisation [NOTES, slides 96, 101-105]

- **Design systems and component libraries:**
  - *Scalability:* UI consistency and faster developer handoff using atomic design systems.
  - *Artifacts:* defined colour values, reusable component libraries, pattern guidelines.
- **Usability testing and analytics:**
  - *Qualitative:* moderated or unmoderated task-based sessions (**5 users reveal about 85% of usability issues**).
  - *Quantitative:* event telemetry, conversion funnels, heatmaps, task-completion metrics.
  - (Full usability-testing process is Module 5.)
- **Internationalisation (i18n) and localisation (l10n):**
  - *Text expansion:* design for languages that expand up to **40%**.
  - *UI flexibility:* avoid fixed-width buttons or cards; use auto-layout (Flexbox/Grid).
  - *Cultural considerations:* adapt flow for **right-to-left (RTL)** languages (Arabic, Hebrew, Urdu, Persian). The **entire layout mirrors horizontally**, not just the text: navigation bars, sidebars, form labels and back/forward indicators. Respect local iconography. (Slide 103 shows the same comic in English and Arabic, mirrored.)

| UX aspect | Consideration | Risk of misalignment |
|---|---|---|
| Colour semantics | Red = danger or loss in Western finance apps, but good fortune or gain in Chinese markets | Confusing feedback or accidental anxiety |
| Imagery and symbols | Avoid culture-specific metaphors (piggy bank for savings, flagged mailbox) | Misread icons, alienated users |
| Form fields and names | Avoid rigid First/Last name; use "Full name" or flexible forms | Users cannot sign up or identify themselves |

- **Formatting standards (locale sensitivity):** do not hard-code formats; use browser or system locale APIs.
  - *Dates and times:* MM/DD/YYYY (US), DD/MM/YYYY (EU), YYYY-MM-DD (ISO/Asia); 12-hour vs 24-hour.
  - *Numbers and currency:* $1,000.00 (US) vs 1.000,00 EUR (DE); symbol placement ($100, 100 kr).
  - *Addresses and phones:* postal codes differ in length and type; phone validation must support dynamic country codes with no rigid length masks.

#### 3.4.10 Extra UX concepts the PYQs asked that the slides only imply [ADDED]

**Affordance** (Norman) [PYQ 2023 Q1ii]: the relationship between what something *looks like* and how it is *used*. A raised, shadowed rectangle looks pressable. A door plate suggests "push" and a handle suggests "pull". *Signifiers* are the visible cues that reveal the affordance.

**Intuitive design** [PYQ 2023 Q1iii]: a design a user can understand and use *without instructions*, because it uses familiar patterns (Jakob's law), matches the user's mental model, gives clear cues (affordance and signifiers), is consistent and gives immediate feedback. Example: the shopping-cart icon and the pinch-to-zoom gesture.

**Screen design and layout** [PYQ 2024 Q5iv]: see the solved answer in Section 4.F.

**The five elements of UX (Garrett's five planes)** [ADDED; asked as MCQ in 2021]: Strategy -> Scope -> Structure -> Skeleton -> Surface. The **skeleton** plane is exactly where wireframes live (interface, navigation, information design) and the **surface** plane is where mockups live (visual design).

---

### 3.5 Rapid Prototyping and Case Study in Software Development  (CO5)

#### 3.5.1 Rapid prototyping [NOTES, slides 106-108]

- Rapid prototyping is the **bridge between abstract ideas and human testing.**
- In traditional product development, a prototype is built to *demonstrate a solution*. In design thinking, prototypes are **experimental tools used to ask questions.**

**The Build -> Test -> Learn loop** (slide 107):

```
        +------------------+
        |     PROTOTYPE    |  BUILD : keep fidelity as low as possible
        +--------+---------+         to answer the specific question
                 |
     +-----------v-----------+
     |   TEST (real users,   |  TEST : put the artifact in front of real users in a
     |   realistic context)  |         realistic context; observe BEHAVIOUR over verbal feedback
     +-----------+-----------+
                 |
        +--------v---------+
        |  LEARN : refine  |  LEARN : refine understanding of the problem, refine the idea,
        |  idea / pivot    |          or pivot back to ideation
        +--------+---------+
                 |
            (REFINE AND ITERATE -> back to BUILD, or DELIVER)
```

**Principles of rapid prototyping** (slide 108):
1. Avoid lengthy discussion or theoretical debate. Building a physical or visual artifact forces instant clarity on vague concepts.
2. Uncover flawed assumptions when the cost of iteration is negligible, not after engineering investment.
3. Build specifically to test a hypothesis ("Will users understand this layout?", "How does this form factor feel in hand?").
4. Prototypes are **disposable.** If user testing invalidates an approach, discard or pivot without hesitation.

**Why use it** [ADDED synthesis]: speed, low cost, early user evidence, risk reduction, better stakeholder communication.
**When it can mislead** [ADDED]: users may judge a rough prototype as the final product, the team can fall in love with the prototype and resist change, and a quick-and-dirty prototype must never silently become production code.

#### 3.5.2 Case study: wireframes for an iPhone version of police-sketch software [NOTES, slides 109-110]

**Background:** a team of designers and developers had to create an **iPhone version of a police-sketch (facial-composite) software.** Several prototypes were required.

**The six-stage process** (slide 110 diagram):

```
 STAGE 1                 STAGE 2                    STAGE 3
 Paper-based       --->  Mechanics & limitations --> Team brainstorming &
 exploration             test                        presentations
 phone-sized paper       test the software           each member presents wireframes and
 sheets, pencils,        mechanics (computer),       navigation alternatives; many
 erasers, markers;       limitations and             alternatives generated;
 hand-sketch screens     characteristics of a        collaborative critique
 and flows               graphics interface for a
                         native iPhone app
                                                         |
 STAGE 6                 STAGE 5                    STAGE 4
 Final assertive   <---  User validation       <--- Merging best solutions
 design                  protocol                   best ideas merged into TWO distinct
 graphic detailing       protocol of problems       paths (Path A, Path B)
 by designers,           and tasks validated
 implemented by          through meetings with
 developers              iPhone users with several
                         different profiles
```

**Stage-wise narrative (what the deck says):**
1. **Paper-based exploration:** the team received paper sheets with the same format and size as a mobile phone screen, with pencils, erasers and marker pens, and started hand-sketching.
2. **Mechanics and limitations test:** they tested the software mechanics and the limits of the graphics interface for a native iPhone app. Each person then started designing **screen wireframes and the navigation flow.**
3. **Team brainstorming and presentation:** with many alternatives generated, each participant presented their ideas to the team.
4. **Merging the best solutions:** the best solutions were merged, incorporating different ideas into **two distinct paths.**
5. **User validation protocol:** a protocol with different problems and tasks was designed and validated through several meetings with iPhone users of **different profiles.**
6. **Final assertive design:** after testing and improving the wireframes and navigation flow, they reached a **final, more assertive solution**, which designers detailed graphically and developers implemented.

**Lessons from the case (use as the conclusion):**
- Start with the cheapest medium (paper) and move up in fidelity only as learning demands.
- Diverge (many alternatives) and then converge (merge into two paths).
- Validate with real users of **different profiles**, not just the team.
- Designer-developer collaboration from the start avoids a gap at handoff.
- The deck frames this as a wireframe-based rapid prototyping workflow: paper -> wireframes -> merge -> user test -> refine -> implement.

#### 3.5.3 Supporting mini-case: login screen, from wireframe to working prototype [NOTES, slides 18, 32, 50-53]

Wireframe (greyscale boxes) -> mockup (brand colours, phone frame) -> Agile coded prototype -> 3 sprints (layout -> validation and feedback -> backend integration). This is a ready 5 M case study if the question says "case study in software development", and it combines Sections 3.2 and 3.3.

#### 3.5.4 Extra case study you can use [ADDED: my own illustrative example, not from notes]

**Food-delivery app "order tracking" feature (rapid prototyping in 3 days):**
- Day 1, hypothesis: "Users will check order status more if it shows a live map." Build: paper sketch plus a wireframe of the tracking screen (low-fi).
- Day 2, test: 5 users, the facilitator flips paper screens (paper prototype). Observation: users ignored the map and looked for "minutes left".
- Day 3, learn and pivot: the new version puts a large ETA at the top (visual hierarchy), and the map goes below. Build a clickable Figma prototype and re-test with 5 users. Result: the ETA is found in under 3 seconds.
- Outcome: a flawed assumption was killed in 3 days at near-zero cost. Only then does the Sprint start for the real build.

---

## 4. PYQ SOLUTIONS (Module-4-relevant only)

Papers used: **Nov-Dec 2021 (50 M)**, **Dec 2022**, **Nov 2023 (30.11.2023)**, **Jul-Nov 2024**, **Jul-Nov 2025 (19.11.2025)**. Format of each solution: the **question text with year, marks**, then the **answer written the way it should be written in the exam**. Where a question needs a scenario, assumptions are stated (the papers say "assume suitable data").

---

### A. Wireframes, Storyboards (prototype types)

#### A1. Write a short note on Wireframes. (Nov 2023 Q5(v), 5 M)

**Wireframes**

**Definition:** a wireframe is a simple, **static, low-fidelity blueprint** of a screen or page that shows the **structure and layout**: where navigation, content and controls sit, before colours, fonts and detailed interaction are added.

**Diagram (mobile login wireframe):**
```
+--------------------------+
|        [ LOGO ]          |
|     Welcome back         |
| Email    [____________]  |
| Password [____________]  |
|             Forgot pwd?  |
| [       LOG IN        ]  |
| --- or continue with --- |
| [Google]    [Facebook]   |
|   New here? Sign up      |
+--------------------------+
```

**Key points:**
1. Represents **placement, hierarchy and user journey**, drawn with boxes, lines and labels in greyscale.
2. Does **not** show colours, fonts, branding, real interaction or animation. "Clicks" are only links between screens.
3. Types: hand-sketched (paper) and digital (Figma, Balsamiq), and low, medium or high fidelity wireframes.
4. Used for brainstorming, mapping user paths and defining layouts, and by product managers, UX designers and architects.
5. **Merits:** fastest and cheapest to create and change, non-designers can contribute, and flaws are found before costly design or code.
6. **Limitations:** no visual or interaction feedback.

**Conclusion:** the wireframe is the skeleton of the interface. Get the structure right first, then add the look (mockup) and the behaviour (clickable prototype).

#### A2. Mention advantages of wire-framing in user interface design. (Nov-Dec 2021 Q1(B)5, part of 5-of-7, about 2 M)

**Advantages of wireframing:**
1. **Fast and cheap:** layouts can be drawn and changed in minutes.
2. **Focus on structure:** colours and fonts do not distract, so discussion stays on layout, hierarchy and flow.
3. **Early problem detection:** navigation and usability problems are caught before design or coding, which saves rework.
4. **Common language:** designers, developers, clients and managers agree on what goes where.
5. **Content prioritisation:** shows what is most important on each screen.
6. **Supports user-flow mapping:** screens can be linked to test the journey.
7. **Easy collaboration:** non-designers can contribute.
8. **Smooth handoff:** developers get a clear structural blueprint.

#### A3. Illustrate the difference between Wire-framing and Storyboarding in User Experience Design. (2025 Q5(vi), 5 M)

| Basis | Wireframing | Storyboarding |
|---|---|---|
| What it is | Static blueprint of **one screen's** layout and structure | A **sequence of drawn frames** telling a story of how a user uses the product in context |
| Focus | Placement, hierarchy, content and controls | User's journey, situation, goals, emotions, before/during/after |
| Question answered | "What goes where on this screen?" | "Why, when and in what situation does the user use it?" |
| Format | Boxes, lines and labels, usually greyscale | Comic-strip drawings with captions |
| Includes people and context? | No | Yes (user, environment, emotion) |
| Fidelity / form | Low to medium, static, digital or paper | Low-fidelity, hand-drawn |
| Stage | Prototype phase (structure) | Ideation and early prototype (empathy and concept) |
| Output used by | Designers, developers | Whole team and stakeholders |
| Example (cab-booking app) | Layout of the "choose ride" screen | 4 frames: user late at night -> opens app -> sees driver arriving -> reaches home safely |

**Illustration:**
```
 WIREFRAME (one screen)             STORYBOARD (a sequence)
 +-------------------+              +------+  +------+  +------+  +------+
 | [Search box]      |              |late &|->|opens |->|driver|->|home  |
 | [map  ........ ]  |              |wait  |  |app   |  |comes |  |safe  |
 | [Book ride]       |              +------+  +------+  +------+  +------+
 +-------------------+
```
**Conclusion:** the storyboard explains the *why and when*; the wireframe defines the *what and where*. They complement each other.

#### A4. "A storyboard is a great way to tell the stories." Justify. (Dec 2022 Q1(i), 5 M)  [partial overlap: storyboards are a low-fidelity prototype type; the technique is Module 3]

**Storyboard** = a series of sketched frames, like a comic strip, showing how a user meets a problem, uses the product and reaches an outcome. It is listed in Module 4 as a low-fidelity prototype (slides 5, 8).

**Justification:**
1. **Visual and quick:** a story is understood in seconds without long documents. It is cheap to draw, and stick figures are enough.
2. **Puts the user at the centre:** it shows context, emotions, goals and pain points (before, during and after use).
3. **Shared understanding:** designers, developers and clients all see the same story, which reduces misunderstanding.
4. **Finds gaps early:** missing steps or illogical flows become obvious while sketching.
5. **Encourages empathy and discussion:** people react to people, not to feature lists.
6. **Low-risk testing:** the concept is tested before any build.

**Example:** a storyboard for a bus-ticket app: Frame 1 rushing commuter in a queue -> 2 opens app -> 3 scans QR and pays -> 4 boards without waiting. It shows the value in 4 pictures.

#### A5. MCQ: "Wireframing and storyboard are ______ & ______ tools used for designing interface." (Nov-Dec 2021 Q1(A)9, 1 M)

**Answer: (c) Static & Dynamic** [my best-judged answer; the paper gives options a: Dynamic & Static, b: Dynamic & Dynamic, c: Static & Dynamic, d: Static & Static]. Reasoning: a wireframe is a static layout of a screen, and a storyboard shows a sequence (flow over time). If your faculty's key differs, follow the key. Both are low-fidelity prototype tools.

---

### B. Prototyping tools

#### B1. Illustrate on the characteristics of any two prototyping tools used in the UI/UX process. (Nov 2023 Q4(iii), 10 M)

The slides name **Sketch, Wireframe, Mockup and Clickable Prototype** as the tool chain, and **Figma, Adobe XD, Axure RP, InVision, Sketch** as software. I take **Figma** (a tool for all the stages) and **Axure RP** (a logic-heavy high-fidelity tool). *The detailed tool features below go beyond the slides [ADDED]; they are standard industry facts.*

**Introduction:** prototyping tools turn ideas into testable screens without writing production code. They move the design along: sketch -> wireframe -> mockup -> clickable prototype -> test -> iterate.

**Tool 1: Figma**
1. **Browser-based and cloud-hosted:** runs on any OS, with no installation. Files are shared by link.
2. **Real-time collaboration:** several designers, PMs and developers edit and comment on the same file at once.
3. **Vector design plus wireframe to mockup in one place:** frames, auto-layout (responsive), shapes, typography and image tools.
4. **Components and design systems:** reusable components, variants, styles and tokens keep UIs consistent.
5. **Prototype mode:** link frames with hotspots, transitions, overlays, and smart-animate micro-interactions to build a clickable prototype with no code.
6. **Developer handoff:** an inspect panel gives measurements, colours, CSS and assets.
7. **Large plugin ecosystem and free tier.**
- Best for: wireframes, mockups and mid- to high-fidelity clickable prototypes, and team work.
- Limits: needs a connection for full features, and cannot simulate real backend logic.

**Tool 2: Axure RP**
1. **Desktop tool for high-fidelity, logic-rich prototypes.**
2. **Conditional logic and variables:** "if the password is empty then show an error" can really be simulated.
3. **Dynamic panels** for tabs, carousels, modals and state changes.
4. **Form and data behaviour:** input validation, repeaters (lists with dummy data).
5. **Adaptive views** for different screen sizes.
6. **Auto-generated documentation:** specification and annotation exports for developers.
- Best for: complex enterprise workflows, forms, banking and admin tools.
- Limits: steeper learning curve and less real-time collaboration than Figma.

**Comparison table:**

| Feature | Figma | Axure RP |
|---|---|---|
| Platform | Browser, cloud | Desktop (plus cloud share) |
| Collaboration | Excellent, real-time | Moderate |
| Fidelity | Low to high | Mainly high-fidelity |
| Logic and variables | Basic transitions | Advanced conditions and variables |
| Learning curve | Easy | Steeper |
| Best use | Team design, UI mockups, quick prototypes | Complex, data-driven interactions |

**Diagram:** draw the tool chain (sketch -> wireframe -> mockup -> clickable prototype -> test -> iterate) and mark where each tool sits.

**Conclusion:** choose by purpose. Figma for collaborative speed and visual polish, Axure for logic and complex flows. Neither replaces paper sketches in the earliest ideation.

(Alternative pair if you prefer: Figma and Adobe XD, but see the note: slides list both. Adobe XD has been in maintenance mode, so Axure RP is the safer second tool.)

---

### C. Visual / UI Design Principles

#### C1. Explain Design Principles in brief. (2024 Q1(i), 5 M)  /  Explain any TWO design principles in brief. (2021 Q1(B)1, about 2 M)

**Design principles** are guidelines that help designers create interfaces that are usable, consistent and attractive (slides 82-84).
1. **Clarity and simplicity:** remove unnecessary visual noise so users reach their goal without cognitive overload. Example: a search bar and one primary button on a Google-style home page.
2. **Consistency:** the same fonts, colours, spacing and patterns on every screen, so users learn once and reuse the knowledge.
3. **Visual hierarchy:** size, scale, contrast, weight and position direct attention to the most important element first. Example: a large "Order Now" button.
4. **Feedback and response:** the system tells the user what is happening (spinner, pressed state, success message).
5. **Forgiveness and error prevention:** confirmations, validation and undo.
6. **Accessibility:** contrast of at least 4.5:1, screen-reader support and large touch targets.
(+ standardise typography, colour system and grid and spacing; + Gestalt principles.)

*If the question asks for only TWO (the 2021 version): write Clarity and Simplicity and Consistency, each with a definition of 1-2 lines and an example.*

#### C2. What are Visual Design Principles? Explain them using example(s). (2024 Q4(i), 10 M)  /  Explain the visual design principles in UX. (Dec 2022 Q4(i), 10 M)

**Definition:** visual design principles are the fundamental rules governing how elements such as colour, shape, typography, space and imagery are arranged on an interface so that it looks organised, communicates clearly and guides the user to act. They make the interface functional (it works), usable (it is easy) and desirable (it looks good).

**Principles, explained with examples** (the first six from the slides, the others [ADDED]):

1. **Visual hierarchy:** using size, scale, contrast, weight and position to order what the eye sees first. *Example:* on an e-commerce page, the product image is largest, the price second and the "Add to cart" button boldest.
2. **Contrast:** differences in colour, size or weight separate elements and make key actions stand out. *Example:* a bright accent "Pay Now" button on a neutral page. Text needs at least 4.5:1 contrast against its background.
3. **Consistency:** uniform typography, colour palette, spacing, icons and interaction patterns on all screens. *Example:* all primary buttons are the same blue rounded rectangle across the app.
4. **Balance** [ADDED]: even distribution of visual weight, symmetrical or asymmetrical. *Example:* a login card centred on the page.
5. **Alignment and grid** [ADDED, with grid from the slides]: elements aligned to a common grid (4 or 8 px base). *Example:* labels and fields left-aligned in a form.
6. **Proximity and grouping (Gestalt):** related items are placed close together. *Example:* a label right next to its input and the "Shipping address" block separated from "Payment".
7. **White (negative) space:** empty space reduces clutter and improves readability. *Example:* generous margins around a card.
8. **Colour:** purposeful palette, with the 60-30-10 rule (60% dominant, 30% secondary, 10% accent) and status colours (green success, amber warning, red error).
9. **Typography:** a clear hierarchy of sizes, weights and line heights (H1 > H2 > body), with readable line length (45-75 characters) and line height 1.4-1.6x.
10. **Feedback, forgiveness and accessibility:** immediate response, undo and confirmation, contrast ratios, screen-reader support, and touch targets of at least 44 x 44 pt.
11. **Other Gestalt principles:** similarity, continuity, closure, figure-ground, common region, common fate (see Section E).

**Diagram (visual hierarchy on a product card):**
```
+---------------------------+
| [ PRODUCT IMAGE - large ] |   1st: biggest
| Wireless Headphones       |   2nd: bold title
| Rs. 2,499                 |   3rd: price, strong colour
| [  ADD TO CART  ]         |   4th: high-contrast CTA (accent 10%)
| ratings, details (grey)   |   last: small, low contrast
+---------------------------+
```

**Conclusion:** applied together, these principles make interfaces clear, consistent, accessible and attractive. They guide the user's attention, reduce effort and build trust.

#### C3. You are required to design an interface for a Ticket Vending Machine at a railway station. Explain how Visual Design principles will be used in the same. (Nov-Dec 2021 Q2(b), 10 M)

**Assumptions and constraints** (as the paper asks): a touchscreen kiosk in a crowded, noisy railway station; users of all ages and literacy levels, often hurried; outdoor or bright light causes glare; supports Hindi, English and a local language; payment by UPI, card and cash; the screen is about 15-19 inches with a physical emergency button.

**Principle -> how it is applied:**

| Principle | Application on the ticket-machine screen |
|---|---|
| Visual hierarchy | Home screen shows 3 big options first: "Buy single ticket", "Season pass", "Top-up smart card". The destination and fare are the largest elements, the confirm button is the strongest |
| Clarity and simplicity | One task per screen: destination -> number of passengers -> fare -> payment -> ticket. Remove ads and decoration |
| Contrast and colour | Light text on a dark background or the reverse, contrast of at least 4.5:1 to beat glare. 60-30-10 palette: neutral background (60%), brand colour for panels (30%), bright accent (10%) for "Pay / Confirm". Green = confirm, red = cancel, amber = warning |
| Typography | Large sans-serif font, 20 pt or more, bold for fares, line length short, icons with labels (multilingual) |
| Consistency | Same button shape, position and colour on every screen. "Back" and "Cancel" always in the same corner |
| Grouping (proximity, common region) | Fare summary in a boxed card, payment methods grouped as icons with labels |
| Touch targets (Fitts) | Buttons of at least 44 x 44 pt (larger at 15 mm or more), spaced apart to avoid mis-taps, placed in easy reach for wheelchair users |
| Feedback | Button pressed state, beep, progress spinner "Printing ticket...", success tick, error message in plain words |
| Error prevention and forgiveness | Confirm-screen summary "Mumbai to Pune, 2 adults, Rs. 340", an easy Back button, a timeout warning before reset |
| Accessibility | Multiple languages, audio guidance, a high-contrast mode, an adjustable height, large icons, a screen reader or earphone jack |
| Hick's law | Show only popular destinations first, with search for the rest |
| White space | Enough spacing between buttons to avoid errors |

**Layout sketch:**
```
+--------------------------------------------------+
| [Language: EN | HI | MR]            Station name  |
+--------------------------------------------------+
|              WHERE ARE YOU GOING?                |
|   [ Dadar ]  [ Thane ]  [ Pune ]  [ Search... ]  |
|--------------------------------------------------|
| Passengers:  ( - )  2  ( + )     Fare: Rs. 340    |
|--------------------------------------------------|
| [ CANCEL (red) ]            [ PAY (green, big) ] |
|   UPI icon | Card icon | Cash icon               |
+--------------------------------------------------+
```

**Conclusion:** by applying hierarchy, contrast, consistency, grouping, large touch targets and clear feedback, the ticket machine can be used in seconds by any traveller, even under pressure.

#### C4. List and Evaluate the application of key Visual Design Principles for Accessibility in Uber's ride selection panel user interface. (2025 Q3(iii), 10 M)

**Scenario:** the ride selection panel lists service options (e.g. Go, Premier, XL, Auto), prices and estimated arrival times for a user booking a ride.

**Assumptions:** mobile app (portrait), outdoor use with glare, users include people with low vision, colour blindness, motor limitations and screen-reader users.

| # | Visual design principle for accessibility | How it is applied (and my evaluation) |
|---|---|---|
| 1 | **Colour contrast (WCAG 2.1 AA, at least 4.5:1)** | Ride name and price use dark text on a white card. *Evaluation:* strong. Low-contrast grey for secondary ETA text or a disabled option is the weak spot, so keep it at 4.5:1 or darker. |
| 2 | **Do not rely on colour alone** | The selected ride is shown with a **thick border, a tick icon and bold text**, not just a colour change. Surge or unavailable states use an icon plus a label. *Evaluation:* essential for colour-blind users. |
| 3 | **Visual hierarchy** | Vehicle image and name first, then price (bold), then ETA, and the "Confirm ride" CTA is strongest at the bottom. *Evaluation:* good. The user's eye goes to the price and the ETA, the main decision factors. |
| 4 | **Typography and legibility** | Sans-serif, clear sizes, bold prices, support for **dynamic text sizing** (system font scaling) with layouts that reflow. *Evaluation:* a fixed-size card would break at 200% text, so use auto-layout. |
| 5 | **Touch target size (Fitts's law, 44 x 44 pt or more)** | Each ride row is a large tappable card with spacing. *Evaluation:* helps users with tremors and one-handed use, and prevents wrong selection. |
| 6 | **Proximity and common region (Gestalt)** | Each ride's image, name, ETA and price sit together in one card; cards are separated by space. *Evaluation:* the user reads each option as one unit and does not mix up prices. |
| 7 | **Consistency** | Same card structure, icons and button style for every option and across the Uber app. *Evaluation:* builds familiarity (Jakob's law). |
| 8 | **Simplicity and cognitive load (Hick, Miller)** | Show 4-5 options, with the recommended one first, and a "More" option for the rest. *Evaluation:* faster choices, and helps users with cognitive disabilities. |
| 9 | **Feedback and status** | The selected state is highlighted instantly, "Finding your driver..." progress and haptic feedback. *Evaluation:* keeps users informed (Nielsen #1). |
| 10 | **Screen-reader and semantic structure** | Each card is labelled "UberGo, Rs. 220, 3 minutes away, selected" for TalkBack or VoiceOver, and focus order follows visual order. *Evaluation:* not visual, but it is the accessibility counterpart that visual hierarchy must match. |
| 11 | **Spacing and grid (8-pt)** | Even spacing gives breathing room and a predictable rhythm. |

**Overall evaluation:** the panel is strong on hierarchy, grouping and consistency. The risk areas are colour-only status cues, low-contrast secondary text and fixed text sizes. All are fixable by meeting WCAG 2.1 AA, adding non-colour cues and testing with assistive technologies and real users with disabilities.

**Diagram:**
```
+---------------------------------------+
| Choose a ride                         |
| +-----------------------------------+ |
| | [car] UberGo        3 min    Rs.220| |  <- selected: thick border + tick
| |  4 seats                      (tick)| |
| +-----------------------------------+ |
| | [car] Premier       5 min    Rs.340| |
| +-----------------------------------+ |
| | [auto] Auto         2 min    Rs.120| |
| +-----------------------------------+ |
| [      CONFIRM UBERGO (big)        ]  |
+---------------------------------------+
```

---

### D. Gestalt principles

#### D1. Write short notes on Gestalt's principles. (Dec 2022 Q5(ii), 5 M; Nov 2023 Q5(ii), 5 M)  /  Illustrate any two Gestalt's principles in UX design with examples. (2025 Q5(iii), 5 M)

**Gestalt principles** come from Gestalt psychology ("the whole is different from the sum of its parts"). The human brain naturally organises individual visual elements into a **structured, unified whole**. In UI and UX design, these principles decide how users perceive **relationships, hierarchy and grouping** on a screen.

**Principles:**

| Principle | Meaning | UX example |
|---|---|---|
| Proximity | Close objects are seen as a group | Label near its field; the footer links grouped |
| Similarity | Same colour, shape, size or style = same function | All clickable links blue and underlined |
| Continuity | Eye follows smooth continuous lines | A horizontal scroll carousel, a stepper line |
| Closure | Brain completes missing parts | A logo or icon with gaps, a partially visible card suggesting scroll |
| Figure-ground | Separates focus from background | A modal over a dimmed page |
| Common region | Elements inside one boundary belong together | A card or box around an address |
| Common fate | Elements moving together are grouped | Menu items animating in unison |

**Diagram:**
```
 PROXIMITY                 SIMILARITY               FIGURE-GROUND
 o o o      o o o          o x o x o                +----------------+
 o o o      o o o          x o x o x                |  dimmed page   |
 -> 2 groups               -> rows by shape         |  [ MODAL ]     |
                                                    +----------------+
```

**If asked "any two" (2025 version) write these two in full:**
1. **Proximity:** on a checkout form, the "Card number", "Expiry" and "CVV" fields are placed close together and separated by extra space from "Billing address". Users see two groups without a divider, so the form feels organised and is completed faster.
2. **Similarity:** on a banking app home, all action buttons ("Pay", "Send", "Request") share the same rounded blue style, while the "Cancel" button is grey and outlined. Users read the blue ones as primary actions and the grey ones as secondary, which reduces errors.

**Importance (closing line):** Gestalt principles help designers group related content, show hierarchy, reduce clutter and guide the eye without extra instructions.

---

### E. Screen design and layout

#### E1. Importance of screen design and layout. (2024 Q5(iv), 5 M)

**Screen design** is the arrangement of all visual elements (navigation, content, controls, images, text) on a screen. **Layout** is the structure that organises them (grid, columns, alignment, spacing, hierarchy).

**Importance:**
1. **Guides attention:** a good layout uses visual hierarchy (scale, contrast, weight, white space), so users see the key content and the primary action first. Reading follows the F-pattern for text-heavy pages and the Z-pattern for landing pages.
2. **Improves usability and efficiency:** logical placement (navigation top or bottom, primary action prominent) cuts search time and clicks.
3. **Reduces cognitive load:** grouping (proximity, common region), chunking (Miller's 7 +/- 2) and fewer choices (Hick's law).
4. **Consistency and learnability:** a grid (4/8 pt), repeated patterns and design-system components mean users learn once.
5. **Readability and aesthetics:** white space, line length (45-75 chars), line height (1.4-1.6x) and a good typography scale.
6. **Responsive and accessible:** adapts to mobile, tablet and desktop, with touch targets of at least 44 pt and WCAG contrast.
7. **Trust and brand:** a tidy, professional screen increases credibility and satisfaction.
8. **Lower development cost:** a layout agreed in wireframe form avoids rework.

**Mini-diagram:**
```
+--------------------------------------+
| Header: logo | nav | search | profile |  <- consistent top
+--------+-----------------------------+
| Side   |  Page title                 |
| menu   |  [ Primary content ]        |  <- F/Z scan path, focus
|        |  [ card ] [ card ] [ card ] |  <- grouped, on a grid
+--------+-----------------------------+
| Footer: links, contact               |
+--------------------------------------+
```

---

### F. Information architecture

#### F1. What do you understand by information architecture in the UX process? Illustrate the same using a book store's sitemap. (Dec 2022 Q4(ii), 10 M)

**Definition:** **Information Architecture (IA)** is the practice of **organising, structuring and labelling content** so that users can find information and complete tasks easily. It answers "where is everything, what is it called, and how do I get there?"

**Role in the UX process (slide 97):**
- *Structural clarity:* group related concepts logically with intuitive labels and categories.
- *Navigation patterns and wayfinding:* users always know where they are, where they have been and where they can go next, via top bars, bottom tab bars, sidebars and **breadcrumbs.**
- *Testing:* validated with **card sorting** (users group and label content cards) and **tree testing** (users find items in a text-only hierarchy).
- IA sits before visual design. It is expressed as a **sitemap** and flows, and then wireframed (the "Structure" and "Skeleton" planes of UX).

**Components** [ADDED]: organisation systems, labelling systems, navigation systems, search systems.

**Bookstore sitemap** (assumptions: an online bookstore with guests and registered users):
```
                               HOME
   +-------+--------+---------+----------+-----------+----------+
   |       |        |         |          |           |          |
 BROWSE  SEARCH   NEW &     CART &     ACCOUNT     HELP &    ABOUT
 BOOKS            BESTSELL  CHECKOUT                SUPPORT
   |       |        |         |          |           |          |
 Fiction  Filters  New      Cart      Login/     FAQ        Our story
 Non-fic  (author, arrivals Shipping   Register  Contact us  Store locator
 Academic  price,  Best-    address    My orders Returns &   Careers
 Children  rating) sellers  Payment    Wishlist  refunds
 Comics            Offers   Order      Profile
 Authors                    confirmation  Saved
 Publishers                              addresses
   |
 Book detail page --> Reviews --> Add to cart / wishlist --> Related books
```
Breadcrumb example: `Home > Browse Books > Fiction > Book title`

**Design decisions explained:** a shallow hierarchy (3 clicks to a book), familiar labels (users' vocabulary), multiple access paths (browse, search, bestsellers), global navigation (cart, account always visible) and a sitemap used as the basis for the wireframes.

**Conclusion:** good IA makes the bookstore findable, learnable and efficient. It is the foundation on which wireframes, visual design and interaction are built.

#### F2. With supporting example, explain how user, context and content help in building good information architecture. (Nov 2023 Q4(i), 10 M)

**Introduction:** good IA lies at the intersection of **three inputs: Users, Context and Content** (the Morville and Rosenfeld IA model) [ADDED model; IA basics are from slide 97]. Ignoring any one produces a poor structure.

```
              USERS
            (  IA  )
   CONTEXT -------- CONTENT
```

| Input | What to study | Effect on IA | Example: university admission portal |
|---|---|---|---|
| **Users** | Who they are, goals, tasks, vocabulary, behaviour, devices, abilities (from research, card sorting) | Decides labels, grouping, navigation and search | Students call it "Fees", not "Remittance". Parents want "Hostel" and "Scholarship". Mobile users need a short menu |
| **Context** | Business goals, organisational structure, policies, technology, culture, timelines, physical or digital setting | Decides what must be prominent and what is possible | Admission deadlines and the university's priority on online applications mean "Apply Now" is always in the header |
| **Content** | Type, amount, format, metadata, freshness, ownership, structure | Decides categories, hierarchy and the navigation model | Brochures, course lists, forms, FAQs and notices are grouped into Programmes, Admissions, Fees, Notices |

**How they work together (steps):**
1. Research users (interviews, card sorting) -> understand needs and mental models.
2. Understand the context (stakeholders, business goals, constraints).
3. Audit and inventory the content.
4. Combine them into the sitemap, labels and navigation.
5. Test with tree testing, then iterate.

**Example result:** top navigation = Programmes | Admissions | Fees and Scholarships | Campus Life | Notices | Apply Now; a breadcrumb trail on each page, and a search bar for the long tail.

**Conclusion:** users shape *how* it is organised, context shapes *why and what is prioritised*, and content shapes *what is organised*. Balanced together, they produce an IA that is findable and usable.

---

### G. Interaction design

#### G1. Importance of using various interaction styles to improve User Experience. (2024 Q5(i), 5 M)  /  List any five common interaction styles. (Nov 2023 Q1(iv), 5 M)  /  List and describe any three common Interaction Styles used in designing a user interface. (2025 Q5(i), 5 M)

**Interaction style** = the way a user communicates with the system. *This topic is not in the module slides [ADDED], but it is PYQ-asked in three papers.*

**Five common styles (and any three for the 2025 version):**

| # | Style | Description | Example | Advantage / drawback |
|---|---|---|---|---|
| 1 | **Command-line** | The user types text commands | Linux terminal | Fast for experts; steep learning curve |
| 2 | **Menu selection** | The user picks from displayed options | ATM, mobile-app menus | Easy to learn, low recall; slow if menus are deep |
| 3 | **Form fill-in** | The user fills in labelled fields | Registration, e-commerce checkout | Structured, clear; tedious if long |
| 4 | **Direct manipulation** | The user acts directly on visible objects (drag, drop, pinch, resize) | File dragging, pinch to zoom, drawing apps | Intuitive, immediate feedback; needs graphics |
| 5 | **Natural language / voice** | The user speaks or types in free language | Alexa, Siri, chatbot | Very natural; ambiguous and error-prone |
| (6) | Touch and gesture / WIMP | Taps, swipes, windows and icons | Smartphone, desktop GUI | Familiar; limited by screen size |

**Importance of using various styles to improve UX (the 2024 wording):**
1. **Matches user expertise:** novices use menus and forms, experts use shortcuts and commands, so UX suits each group.
2. **Reduces learning time and errors:** the familiar style makes the task obvious.
3. **Improves efficiency and satisfaction:** the right style gives the fastest path for the task (voice while driving, form for data entry).
4. **Supports accessibility:** voice for visually impaired users, large touch targets for motor impairments.
5. **Fits context and device:** touch on phone, voice on smart speaker, command line on servers.
6. **Provides flexibility and engagement:** combining styles (voice plus touch) increases user control.
7. **Better feedback:** direct manipulation gives instant visible results.

#### G2. Describe the 5 Dimensions of Interaction Design. (2024 Q5(vi), 5 M)  /  Identify the Five Dimensions of Interaction Design. Illustrate its role in a user's experience with the help of an example. (2025 Q4(iii), 2 + 8 M)

**Interaction design** is designing the dialogue between a user and a product. *The five dimensions are not in the slides [ADDED] but are asked in two papers.*

**The five dimensions** (Crampton Smith and Silver) (2 M part: just list them with one line each):

| Dimension | Meaning |
|---|---|
| 1D Words | Text: labels, button text, messages, instructions |
| 2D Visual representations | Graphics, icons, images, typography, layout |
| 3D Physical objects / space | The device and physical context with which the user interacts |
| 4D Time | Changes over time: animations, progress, sound, response time |
| 5D Behaviour | How users act and how the system reacts: feedback, emotion, actions |

**Illustration: ordering a cab on a ride-hailing app (8 M part):**

| Dimension | Role in the user's experience |
|---|---|
| 1D Words | Clear labels "Where to?", "Confirm pickup", "Driver arriving in 3 min". Plain words reduce confusion |
| 2D Visuals | Map with pin, car icons on route, colour-coded buttons. The visual hierarchy makes the pickup pin and the Confirm button stand out |
| 3D Physical | Used one-handed on a moving road, so thumb-reach buttons at the bottom, large touch targets, a portrait layout; the phone's GPS and vibration |
| 4D Time | The car moves smoothly on the map, ETA counts down, "Finding driver" spinner, a notification sound when the driver arrives. Waiting is made visible and predictable |
| 5D Behaviour | The user taps Confirm -> button changes to "Searching..." -> shows driver details -> the user can cancel or call the driver. Feedback and recovery build trust and control |

**Diagram:**
```
          5D BEHAVIOUR (how it acts / reacts)
              ^
 1D WORDS -> 2D VISUALS -> 3D PHYSICAL SPACE -> 4D TIME  ... all combine into the experience
```
**Role summary:** each dimension adds a layer. Words give meaning, visuals give clarity, the physical dimension gives ergonomics, time gives rhythm, and behaviour gives control and emotion. A good UX balances all five. If one is weak (for example confusing words or a slow response), the whole experience suffers.

#### G3. Short note on Widgets. (Dec 2022 Q5(iii), 5 M)  /  Discuss the importance of widgets in enhancing the user interaction with supporting example. (2025 Q4(ii), 10 M)

*Widgets are not in the module slides [ADDED] but are asked in three papers (one as MCQ).*

**Definition:** a **widget** (UI control or component) is a reusable on-screen element that lets users **perform a function or access a service**, such as entering data, selecting an option or triggering an action. (2021 MCQ Q6 answer: **(b) Widget**.)

**Common widgets:** button, text field, checkbox, radio button, drop-down list, slider, toggle switch, date picker, tabs, progress bar, tooltip, search box, carousel.

**Importance in enhancing user interaction:**
1. **Familiarity and learnability (Jakob's law):** users already know how a checkbox or slider works, so there is little learning time.
2. **Affordance:** a button looks pressable, a slider invites dragging, so the action is obvious.
3. **Efficiency and accuracy:** a date picker avoids typing format errors, a dropdown restricts input to valid choices (error prevention), and a slider chooses a range quickly.
4. **Feedback:** hover, pressed, focus, disabled and error states tell the user what is happening.
5. **Consistency:** the same widget style across screens through a component library and design system.
6. **Reduced cognitive load (Hick's law):** the right widget chunks choices (radio for 2-5 options, dropdown for long lists).
7. **Accessibility:** native widgets support keyboard navigation and screen readers.
8. **Faster design and development:** reusable components speed up prototyping (Figma component libraries) and cut cost.

**Widget-selection table (example):**

| Need | Best widget |
|---|---|
| Pick one of 2-5 options | Radio buttons |
| Pick several | Checkboxes |
| Pick one from many | Dropdown or search-select |
| On or off | Toggle switch |
| Numeric range | Slider |
| Date entry | Date picker |
| Show progress | Progress bar |

**Supporting example: flight-booking app.** A date picker for departure (no wrong format), a stepper widget for passengers (+/-), a toggle for "Round trip", a dropdown with autocomplete for the city, and a primary button "Search flights". Each widget guides input, prevents errors and gives instant feedback, which makes booking faster and less frustrating.

**Diagram:**
```
 From [ Mumbai   v ]   To [ Delhi    v ]
 Date [ 12/12/2026 (calendar icon) ]   Round trip  [ o-- ] (toggle)
 Passengers  ( - )  2  ( + )           [ SEARCH FLIGHTS ]
```

#### G4. MCQ: "An application, or a component of an interface, that enables a user to perform a function or access a service is called as: a Element, b Widget, c Component Library, d API." (Nov-Dec 2021 Q1(A)6, 1 M)

**Answer: (b) Widget.**

---

### H. UI vs UX, UI design and feedback

#### H1. List five relevant points of difference between UI and UX. (Nov 2023 Q1(i), 5 M)  /  How is User Experience Designer different from User Interface Designer? (2024 Q1(iii), 5 M)

| # | Point | UI (User Interface) / UI designer | UX (User Experience) / UX designer |
|---|---|---|---|
| 1 | Meaning | The visual and interactive layer through which the user talks to the system | The overall experience and journey of using the product |
| 2 | Focus | Layout, typography, colour palettes, micro-interactions, aesthetics | Information architecture, user flows, usability, accessibility, emotion |
| 3 | Question answered | "How does it look and respond?" | "How does it work and feel for the user's goal?" |
| 4 | Scope | A product's screens and controls (narrower) | Complete journey: before, during and after use (wider) |
| 5 | Main tasks | Visual design, style guide, mockups, icons, component design | User research, personas, journey maps, wireframes, usability testing |
| 6 | Output | Mockups, design system, high-fidelity screens | Research findings, flows, wireframes, test reports |
| 7 | Skills and tools | Graphic design, typography, Figma/Sketch for visuals | Research, psychology, IA, Figma/Axure for wireframes and prototypes |
| 8 | Analogy | A car's dashboard, seats and paint | The whole experience of driving the car |

*Write any five for 5 M; for the "designer" version, say: the UX designer decides **how the product works and flows for users**, while the UI designer decides **how it looks and responds on the screen**. A good product needs both. UI is a part of UX.*

**MCQ link (2021 Q1(A)1, "User Experience Design is defined as ___"):** the process of designing products that provide meaningful, relevant and enjoyable experiences for users, covering the whole interaction with the product, from branding to usability and function.

#### H2. What is user interface design and what are its goals? (Dec 2022 Q1(vi), 5 M)

**User Interface (UI) design** is the process of designing the **visual and interactive elements** through which a user communicates with a system: layout, typography, colour, icons, buttons, menus and the way they respond. It turns the structure from UX (wireframes) into the look and feel (mockups) and behaviour (prototypes).

**Goals of UI design:**
1. **Usability:** easy to learn and operate, with few errors.
2. **Efficiency:** users complete tasks quickly with minimum steps.
3. **Clarity and simplicity:** no unnecessary elements, with a clear hierarchy.
4. **Consistency:** the same patterns and style across screens.
5. **Feedback:** the system always shows its status.
6. **Accessibility and inclusivity:** usable by people of varying abilities (WCAG, contrast, touch targets).
7. **Aesthetics and brand:** attractive and in line with the brand, which builds trust.
8. **User satisfaction:** a pleasant, confident experience that encourages adoption.

#### H3. Figure out the role of feedback mechanism in the design of user interface. (Nov 2023 Q2(A)(i), 5 M)

**Feedback** = the system's response to a user's action, or the information about the system's state, so users always know what is happening (Nielsen's Heuristic #1, visibility of system status; slides 78-79).

**Role of feedback in UI design:**
1. **Confirms actions:** a pressed-button state, a tick or "Message sent" shows that the input was received.
2. **Shows system status:** loading spinners, progress bars and "Processing..." show that the system is working and how long it will take.
3. **Reduces uncertainty and anxiety:** users do not click repeatedly or leave.
4. **Prevents errors:** immediate input validation ("Invalid email format").
5. **Helps recovery:** human-readable error messages with steps to fix.
6. **Guides and teaches:** hover and focus states, tooltips and disabled buttons reveal what is possible.
7. **Builds trust and satisfaction:** a responsive system feels reliable and in control.

**Types:** visual (colour change, animation), auditory (beep), haptic (vibration), textual (messages).
**Timing guideline** [ADDED, Nielsen]: about 0.1 s feels instant, 1 s keeps the flow, and 10 s is the limit for attention, so after that show a progress indicator.

**Example:** the "Add to cart" button changes to "Added" with a tick, and the cart counter increments.

#### H4. Consider a multimedia file download and a software installation process. State how we can create a dialogue with the user to communicate the time factor for each. (Nov 2023 Q2(A)(ii), 5 M)

**Idea:** both are waiting tasks. The interface should open a "dialogue" that tells the user *what is happening, how far along it is and how long is left*, so waiting is predictable.

| Aspect | Multimedia file download | Software installation |
|---|---|---|
| Duration known? | Yes, the file size is known, so use a **determinate progress bar** | Mostly yes, as a number of steps and components, so use a **staged determinate progress bar** |
| Information to show | File name, "45 MB of 120 MB (38%)", speed "3.2 MB/s", **time remaining "about 24 s"** | "Step 2 of 4: Copying files", "Installing component 3 of 8", percentage, "about 2 minutes remaining" |
| Controls | Pause, resume, cancel, "open folder" | Cancel with a confirmation, "Run in background" |
| Dialogue messages | "Downloading song.mp4..." -> "Download complete. Open | Show in folder" | "Preparing..." -> "Installing..." -> "Finishing..." -> "Installation complete. Launch now?" |
| When time unknown | Use an **indeterminate** spinner plus "Connecting..." | "Please wait..." spinner with a status text. Never a frozen screen |
| Error handling | "Connection lost. Retry / Resume" | "Not enough disk space (need 500 MB). Free space and retry" |
| Extras | Notification when the download is complete, usable while in the background | Tips or feature highlights during a long install, a completion sound |

**Sketch:**
```
 Downloading  holiday.mp4              Installing  App v2.1
 [#########-------------] 38%          Step 2 of 4: Copying files
 45 MB of 120 MB  -  3.2 MB/s          [##############--------] 60%
 About 24 seconds left                 About 2 minutes left
 [Pause]   [Cancel]                    [Cancel]   [Run in background]
```

**Principle:** visibility of system status, short feedback loops, honest estimates and user control (pause or cancel).

#### H5. "Affordance is the relationship between what something looks like and how it's used." Explain with the help of a supporting example. (Nov 2023 Q1(ii), 5 M)  /  What do you understand by intuitive design? Explain. (Nov 2023 Q1(iii), 5 M)

**Affordance** (Don Norman): the relationship between the **perceived properties of an object and the actions that are possible with it.** A design's appearance should *suggest* how it is used. *Signifiers* are the visible cues (shape, label, shadow, colour) that communicate the affordance.

**Examples:**
- **Physical:** a door with a flat plate affords *pushing*, a door with a vertical handle affords *pulling*. A badly designed "pull" handle on a push door (a "Norman door") confuses people.
- **Digital:** a raised button with a shadow and a label "Submit" affords *clicking*. A text box with a blinking cursor affords *typing*. A slider handle affords *dragging*. A blue underlined text affords *clicking*. Flat, borderless, grey text that is actually a button has poor affordance and users miss it.
- Good affordance means no instructions are needed. Poor affordance means errors, frustration and drop-off.

**Intuitive design:** a design that users can understand and use **immediately, without instructions or training**, because it matches what they already know.

**Characteristics:**
1. **Familiar patterns and mental models (Jakob's law):** shopping-cart icon, magnifier for search, hamburger menu.
2. **Clear affordances and signifiers.**
3. **Consistency** inside and across products.
4. **Simplicity and low cognitive load.**
5. **Immediate feedback.**
6. **Natural mapping:** controls match their effects (swipe up scrolls up).
7. **Error prevention.**

**Example:** a smartphone camera app. The big round shutter button, the pinch-to-zoom gesture and the thumbnail of the last photo are understood by anyone with no instructions.

**Relation:** affordance is one of the building blocks of an intuitive design.

---

### I. Remaining Module-4-linked MCQ (Nov-Dec 2021 Q1(A))

| Q | Question | Answer | Why |
|---|---|---|---|
| 5 | The correct sequence in which elements of user experience are developed is: (a) Strategy-Structure-Skeleton-Scope-Surface (b) Strategy-Structure-Scope-Skeleton-Surface (c) Strategy-Scope-Skeleton-Structure-Surface (d) Strategy-Scope-Structure-Skeleton-Surface | **(d)** | Garrett's five planes: Strategy -> Scope -> Structure -> Skeleton -> Surface. Wireframes sit at *Skeleton*, visual mockups at *Surface* |
| 6 | Component of an interface that lets a user perform a function: Element / Widget / Component Library / API | **(b) Widget** | See G3 |
| 9 | Wireframing and storyboard are __ & __ tools | **(c) Static & Dynamic** (best judgement; see A5) | See A5 |
| 2 | Which is a non-functional requirement: I Order of items, II Decoration, fonts, boxes, III Alignment of items, IV White space between items | Options: (a) I, II (b) II, III (c) I, III (d) All of above. Visual items (II, III, IV) are presentation, i.e. look-and-feel, concerns. The paper's key is not visible to me, so **I cannot confirm the option; check your key.** | Related to visual design but not clearly from this module |

---

### J. Questions I looked at and excluded (not Module 4), so you can verify my filter

| PYQ | Reason excluded |
|---|---|
| Empathy map (2021 Q2c; Dec 2022 Q3ii, Q3iii; Nov 2023 Q3i; 2024 Q1v; 2025 Q1ii) | Module 2 (Empathise and Define) |
| Personas (2024 Q5iii; Nov 2023 Q2B; Dec 2022 Q2B; 2025 Q2ii, Q5v) | Module 2 |
| User research, methods, goals, qualitative vs quantitative (2024 Q2A, Q4iii; Dec 2022 Q1ii, Q2A; 2021 Q1B3, Q2a; 2025 Q1iii) | Module 2 |
| Wicked problems (2021, Dec 2022, Nov 2023, 2024, 2025) | Module 1 |
| Design process stages, 5S model, remote control and ride-booking design process (2024 Q2, 2021 Q4a, Q4b, 2025 Q2, Q3i) | Module 1 (design thinking stages) |
| User-centred design, goal-directed design (Nov 2023 Q2B, 2021 Q1B2, Q1A3, 2025 Q5iv) | Module 1 |
| Heuristic evaluation and design principles of Nielsen (Dec 2022 Q2B ii, 2025 Q2i) | Module 5 (Testing and Feedback) / UX evaluation |
| Usability testing: types, process, dimensions of usability, UAT (2024 Q4ii, Q5v; Nov 2023 Q4ii, Q5vi; Dec 2022 Q4iii; 2021 Q3; 2025 Q4i, Q1vi) | Module 5 (Testing and Feedback Implementation) |
| AR, VR, MR, XR, immersive technologies (all papers) | Not in this module's syllabus |
| User flows, UX stories, flowcharts, use-case diagrams (Nov 2023 Q3ii, Q3iii; Dec 2022 Q1iv, Q2A) | Module 3 (Ideation: journey mapping, storyboards) and Module 2 |
| Evolution of UI-UX (Nov 2023 Q5i, Dec 2022 Q5v) and "Design thinking" (Dec 2022 Q5vi) | Module 1 / introductory theory |
| Impact of bad design, types of users, limitations of user-centric vs data-centric design (2025) | General UXD, not Module 4 |
| May 2023 Software Architecture and Design Thinking paper | Architecture content |

---

## 5. [ADDED] LIKELY QUESTIONS FOR MODULE 4 THAT THE PYQS DID NOT ASK (my own predictions, not official)

Every answer below follows from Section 3. A skeleton answer is given for each.

**1. Differentiate between low-fidelity and high-fidelity prototypes. (5 or 10 M)**
Use the table in 3.1.5 (at least 6 rows) plus the ladder diagram.

**2. Compare wireframe, mockup and clickable prototype. (10 M)**
Use the table in 3.2.5. Add the one-liner "skeleton / skin / behaviour". Draw the login screen in wireframe and mockup versions.

**3. Explain agile prototyping with an example. (10 M)**
Use 3.3.1: definition, living artifact, fidelity progression, 4 characteristics, and the login screen in 3 sprints.

**4. Merits and limitations of iterative prototyping. (5 M)**
Write 4-5 merits and 4-5 limitations from 3.3.2. Mention scope creep, the local-maxima trap and cost.

**5. Difference between throwaway and evolutionary prototyping. (5 M)**
Use the table in 3.3.3.

**6. Explain Hick's law and Miller's law with examples. (5 M)**
Hick: more options means longer decision time, T = b log2(n + 1). Example: a 3-plan pricing page vs a 20-option page. Miller: 7 +/- 2 items. Example: a phone number is chunked as 98765 43210, and a long menu is split into sections.

**7. Explain F-pattern and Z-pattern reading. (5 M)**
F-pattern: people scan text-heavy pages in an F shape (a top line, a shorter second line, then down the left edge). Put key content on the top and left. Z-pattern: landing pages are scanned along a Z (top-left to top-right, diagonal to bottom-left, then to bottom-right CTA). Place the logo top-left, the nav top-right and the CTA bottom-right.
```
 F-pattern                 Z-pattern
 ================          Logo ------------> Nav
 =========                      \
 =====                           \
 ===                              \
 =                          Info ------------> [CTA]
```

**8. Explain the 60-30-10 colour rule and the role of colour in UI. (5 M)**
60% dominant (background), 30% secondary (structure: cards, headers), 10% accent (CTAs). Use colour for state (success, warning, error). Never use colour alone (accessibility), and respect cultural meaning (red).

**9. Explain internationalisation and localisation challenges in UI design. (5 or 10 M)**
Text expansion up to 40% (use auto-layout), RTL mirroring (Arabic, Hebrew), colour semantics (red in Chinese markets), culture-specific icons (the piggy bank), name fields (the full name), and date, time, currency and phone formats via locale APIs. Include the table from 3.4.9.

**10. What is a wireframe? Draw a wireframe for a [mobile login / homepage / dashboard / food-ordering] screen. (5 M)**
Draw one of the three examples in 3.2.2 with the labels. For a food-ordering app, draw: header with location and search, a promo banner, a category icon row, restaurant cards (image, name, rating, ETA) and a bottom tab bar (Home, Search, Orders, Profile).

**11. Explain the role of prototyping in the design thinking process / Why is rapid prototyping important? (5 M)**
Use 3.5.1: bridge from ideas to testing, a tool to ask questions, Build-Test-Learn, 4 principles, and disposability.

**12. Explain rapid prototyping with a case study. (10 M)**
Use the iPhone police-sketch case in 3.5.2 (the 6-stage diagram) and add the lessons. Optionally add the login-screen mini-case.

**13. Explain UI/UX considerations for a mobile app or a website. (10 M)**
Structure by the slides' five groups: usability and psychology, visual design, navigation and IA, workflow and content, governance and testing. Pick 2-3 points from each (Hick, hierarchy, Jakob, feedback, colour, typography, grid, nav patterns, Fitts 44 pt, WCAG, forms, CTA, i18n).

**14. Explain integration design / interaction design and its link with design thinking phases. (5 or 10 M)**
Use 3.4.1: definition, the 4 principles and the 4-phase table.

**15. Explain accessibility in UI design (WCAG). (5 M)**
WCAG 2.1 AA baseline; contrast of at least 4.5:1; screen-reader and keyboard support; dynamic text sizing; touch targets of at least 44 x 44 pt; do not use colour alone; alt text; focus states.

**16. Explain micro-interactions with examples. (5 M)**
Small, single-purpose animated responses: a heart that pulses on "like", a pull-to-refresh spinner, a button press state, a password strength meter. Purpose: feedback, show spatial relationships, delight. Constraint: 200-400 ms, with easing, and never delay tasks.

**17. Difference between mockup and prototype / mockup and wireframe. (5 M)**
Mockup = static, visual, look and feel. Wireframe = static, structural, no styling. Prototype = interactive. Use the 3.2.5 table rows.

**18. Role-playing and Wizard-of-Oz prototyping (5 M).**
Use 3.1.3 and the chatbot example. Mention why it is useful: it tests demand before building costly technology.

---

## 6. LAST-MINUTE REVISION CHEAT-SHEET

**One-line spine of the module:**
*Prototype to learn -> start low-fidelity -> wireframe (structure) -> mockup (look) -> clickable prototype (behaviour) -> iterate in Agile sprints -> design the UI/UX with psychology, hierarchy, Gestalt, accessibility -> rapid-prototype: Build, Test, Learn -> case: iPhone police-sketch app, 6 stages.*

**Fidelity ladder:** Low (sketch, paper, storyboard, simple wireframe, role-play) -> Medium (greyscale clickable wireframe, basic mockup) -> High (interactive, real content, animation).

**9 prototype types:** Sketches, Paper, Storyboards, Wireframes, Clickable, Physical, Role-play/service, Wizard-of-Oz, User-driven/co-creation.

**Wireframe / Mockup / Clickable in one line each:**
- Wireframe: static, greyscale, structure and layout (placement, hierarchy, journey), cheapest.
- Mockup: static, coloured, look and feel, stakeholder and branding review, developer handoff.
- Clickable: interactive hotspots, usability testing, developer handoff, tools Figma, Adobe XD, Axure RP, InVision, Sketch.

**Agile prototype:** living artifact, build-measure-learn; low -> mid -> high; hypothesis-driven, fail fast, throwaway vs evolutionary, cross-functional; MVP; login example Sprint 1 layout, Sprint 2 validation and feedback, Sprint 3 backend integration.

**Iterative prototype:** build -> test -> learn -> adapt; merits (risk, assumptions, time-to-market, alignment, adoption); limits (scope creep, overhead, code debt, fatigue, local-maxima trap, fixed-budget difficulty).

**Interaction (integration) design 4 principles:** User journey integration, Cross-functional empathy, Systemic feasibility, Ecosystem consistency.

**5 dimensions of IxD [ADDED]:** Words, Visuals, Physical space, Time, Behaviour.

**Interaction styles [ADDED]:** command-line, menu, form fill-in, direct manipulation, natural language (touch and gesture).

**UI vs UX:** UI = look and interaction; UX = whole journey (IA, flows, usability, accessibility, emotion).

**Psychology laws:** Hick (choices increase time), Miller (7 +/- 2), Jakob (use familiar patterns), Fitts (big, close targets, 44 pt), Nielsen #1 (system status), error prevention and recovery.

**Visual hierarchy levers:** scale, contrast, weight, white space. **Reading patterns:** F (text) and Z (landing).

**UI principles (6):** clarity and simplicity, consistency, visual hierarchy, feedback and response, forgiveness and error prevention, accessibility. **Standardise:** typography, colour system, grid and spacing.

**Gestalt (7):** Proximity, Similarity, Continuity, Closure, Figure-ground, Common region, Common fate. Safe picks for "any two": proximity and similarity.

**Numbers:** 60-30-10; 8/4-pt grid; line height 1.4-1.6; line length 45-75; type scale 1.250; animation 200-400 ms; touch 44 x 44 pt; contrast 4.5:1; WCAG 2.1 AA; text expansion 40%; 5 users ~ 85%.

**IA:** organise, label, navigate; test with card sorting and tree testing; breadcrumbs, top bar, bottom tab bar, sidebar; users + context + content [ADDED]; sitemap.

**i18n/l10n:** text expansion, RTL mirroring, colour semantics (red), culture-specific icons, full-name field, locale-based date, number, currency, address and phone formats.

**Rapid prototyping:** Build (lowest fidelity) -> Test (real users, behaviour over words) -> Learn (refine or pivot). 4 principles: avoid debate, expose assumptions cheaply, test a hypothesis, prototypes are disposable.

**Case study (iPhone police-sketch):** 1 Paper exploration -> 2 Mechanics and limitations test -> 3 Team brainstorm and presentations -> 4 Merge best into two paths -> 5 User validation protocol (different user profiles) -> 6 Final assertive design (designers detail, developers implement).

**PYQ priority list (study in this order):**
1. Visual design principles (10 M, scenario based: ticket machine, Uber panel).
2. Gestalt (5 M, any two with examples).
3. Wireframes and wireframe vs storyboard.
4. Interaction styles, widgets, 5 dimensions of interaction design.
5. Information architecture (sitemap) and user-context-content.
6. UI vs UX, feedback, affordance and intuitive design, screen design and layout.
7. Prototyping tools (Figma plus one more).
8. Rapid prototyping case study and Agile/iterative (likely, not yet asked).

**Exam-writing checklist:** a one-line definition first, a neat diagram on every answer (paper instructions say "Draw neat diagrams"), numbered points, one example, a table for any compare question, state assumptions in scenario questions ("assume suitable data"), and a one-line conclusion.
