I'll start by reading the three PPTX files, since their contents aren't in context yet.

Text from all three decks is read. Many slides carry their content only in diagrams, so I'm rendering them now to read those visually.

Quick update: all the slide text is read, and I'm now looking at the key architecture diagrams (sensor cloud first), then the IoT and fog diagrams.

Still going: deck 1's diagrams are done, and I'm now viewing the IoT, vehicular cloud and parking diagrams from deck 2, then the fog slides in deck 3.

Everything is read. Before I write the file, I'm saving the study context so it carries forward.

# Cloud_Computing_Mod_5.md

**Subject:** Cloud Computing (KJSCE, LY B.Tech Comp) | **Module 5:** Sensor Clouds, Cloud IoT and Fog Computing | **CO5**

---

## 0. CARRY-FORWARD CONTEXT (UTMOST IMPORTANT, keep this in every summary of this chat)

**Task:** prepare the user for Module 5. Deliver everything inside the chat as one `Cloud_Computing_Mod_5.md`. No separate artifacts, no emojis unless necessary. Read images multimodally, no OCR scripts.

**Inputs actually read:**
- `Module_5_1.pptx` (124 slides): Sensor Clouds, Sensor Cloud Infrastructure, Virtual Sensors, VS configurations, System Architecture.
- `Module_5_2.pptx` (134 slides): Basic IoT Architecture, Cloud Components for IoT, iCOMOT, IoT infrastructure/protocols/platforms, Vehicular Data Cloud, Intelligent Parking Cloud.
- `Module_5_3.pptx` (85 slides): Fog Computing, Cloud vs Fog, Cloud-Fog-Edge, Health Cloud-Fog case study. Diagram-only slides were rendered and inspected visually.
- PYQs: `cloud_computing.PDF` (Jan-Apr 2025 ESE, 100 marks) and 7 screenshots covering Dec 2022 ESE (100), Nov-Dec 2021 (50) and May-Jun 2021 (50, Distributed and Cloud Computing).

**Syllabus (verbatim):**
- 5.1 Sensor Clouds, Overview of Sensor Cloud Infrastructure, Virtual Sensors, System Architecture of Sensor Cloud Infrastructure, Virtual Sensor Configurations: one-to-many, many-to-one, many-to-many, and derived
- 5.2 Basic IoT Architecture, Cloud Components for IoT, iCOMOT: An IoT Cloud System, Infrastructure, Protocols and Software Platforms for establishing an IoT Cloud system, Architecture for IoT-based vehicular data clouds, Architecture for Intelligent Parking Cloud service
- 5.3 Fog Computing, Cloud vs Fog Computing, Cloud-Fog-Edge Computing, Case Study: Health Cloud Fog Model
- 5.4 Self-Learning: Edge Computing Architecture

**Key finding (critical):** none of the four papers asks anything directly from Module 5. Details are in Section 4. All Module 5 question types below are therefore predicted from your notes plus the question patterns in the papers.

**Source tags used throughout:**
- `[N]` = from your notes
- `[+]` = added by me beyond your notes (verify against your textbook)
- `[S]` = self-made question or numerical
- `[P]` = appeared in a real PYQ (none for this module)
- `[P~]` = the same question type appeared in a PYQ for another module

---

## 1. TOPIC MAP

```
MODULE 5: Sensor Clouds, Cloud IoT and Fog Computing
|
+-- 5.1 SENSOR CLOUDS
|   +-- Sensor basics (sensor, gateway, sensor network)
|   +-- Sensor Cloud = Sensors + Network + Cloud
|   |   +-- Why needed (storage, processing, scalability, remote access, analytics, ML)
|   |   +-- Features (scalability, elasticity, sharing, virtualization, on-demand, ...)
|   |   +-- Sensor data pipeline + role of AI/ML (anomaly, prediction, classification)
|   |   +-- Challenges (volume, latency, bandwidth, security, privacy, reliability, energy)
|   |   +-- Applications + Advantages
|   +-- Overview of Sensor Cloud Infrastructure
|   |   +-- Layers: Physical sensor > Network/Comm > Mgmt/Middleware > Virtual sensor
|   |   |           > Cloud service > Application
|   |   +-- Middleware functions: discovery, registration, configuration
|   +-- Virtual Sensors
|   |   +-- Physical vs Virtual sensor
|   |   +-- Functions: abstraction, sharing, composition, data processing
|   |   +-- Configurations
|   |       +-- One-to-one (in notes, baseline)
|   |       +-- One-to-many
|   |       +-- Many-to-one
|   |       +-- Many-to-many
|   |       +-- Derived virtual sensor
|   +-- System Architecture of Sensor Cloud Infrastructure
|       +-- 6 components (sensor, gateway, cloud infra, virtualization,
|       |                 service/mgmt, user/application)
|       +-- Reference diagrams (template/registry model, Se-aaS model,
|       |                       WSN virtual-sensor-network model, SCSP model)
|       +-- Complete data flow + why it is called "Sensor" Cloud
|
+-- 5.2 CLOUD IoT
|   +-- Basic IoT Architecture
|   |   +-- 4 layers: Device/Perception > Network > Cloud/Processing > Application
|   +-- Cloud Components for IoT
|   |   +-- Device mgmt, Data ingestion, Message broker, IoT DB,
|   |       Analytics, AI/ML, Cloud APIs, Security
|   +-- iCOMOT: An IoT Cloud System (functions, why cloud)
|   +-- Infrastructure, Protocols, Software Platforms
|   |   +-- Infrastructure: Things+Actuators, Embedded devices, Gateway,
|   |   |                   Network, Edge/Fog, Cloud infra
|   |   +-- Protocols
|   |   |   +-- Application: MQTT, CoAP, HTTP/HTTPS, AMQP, WebSocket
|   |   |   +-- Connectivity: Wi-Fi, BLE, Zigbee, LoRaWAN, Cellular (NB-IoT, LTE-M, 4G/5G)
|   |   +-- Software platforms: functions + AWS IoT, Azure IoT, ThingsBoard, Eclipse IoT
|   |   +-- Security infrastructure
|   +-- Architecture for IoT-based Vehicular Data Cloud
|   |   +-- Vehicle/IoT layer + OBU > Communication (4G/5G, Wi-Fi, DSRC, C-V2X; V2X)
|   |   |   > RSU > Edge/Fog > Cloud > Application
|   |   +-- V2V, V2I, V2N, V2P | Edge vs Cloud roles | Security
|   +-- Architecture for Intelligent Parking Cloud Service
|       +-- Sensor layer > Gateway/Comm > Cloud data layer > Cloud service layer > App layer
|       +-- Services: management, availability, reservation, navigation, payment, analytics
|
+-- 5.3 FOG COMPUTING
|   +-- Fog Computing (definition, why needed (9 reasons), fog node, working)
|   +-- Cloud vs Fog Computing
|   +-- Cloud-Fog-Edge Computing (3-tier hierarchy, smart parking example)
|   +-- Case Study: Health Cloud-Fog Model (layers, working, applications,
|                                           advantages, challenges)
|
+-- 5.4 SELF-LEARNING: EDGE COMPUTING ARCHITECTURE
    +-- Partly in deck 3 (edge definition, edge vs fog vs cloud); rest [+]
```

---

## 2. TOPIC-WISE QUESTION TYPES

**Legend:**
- `[X]` = very likely
- `[x]` = possible
- `-` = unlikely
- `[P~]` = same question type appeared in a PYQ for another module
- `[P]` = appeared for this topic (none did)

**Pattern evidence from the 4 papers:**
- "Explain X architecture with diagram" appears 6+ times (Aneka, AppEngine, Hyper-V, AWS) `[P~]`.
- "Compare A vs B" appears about 10 times (Public vs Private, SAN vs NAS, hardware vs software power management, Web 1.0/2.0/3.0) `[P~]`.
- "Write short notes on" 5-mark items fill Q5 in every long paper `[P~]`.
- 1-mark define/fill-in/match items appear in both 50-mark papers `[P~]`.
- No paper contains a numerical or derivation. Module 5 is a theory + diagram module.

| # | Topic | Short note (5m) | Diagram | Compare | Long answer (10m) | Example / flow | Numerical | 1-mark / MCQ |
|---|---|---|---|---|---|---|---|---|
| 1 | Sensor, Sensor Cloud definition | [X] | [x] | - | [x] | [x] | - | [X] |
| 2 | Features, advantages, challenges, applications | [X] | - | - | [x] | [x] | - | [x] |
| 3 | Sensor cloud layers (overview) | [x] | [X] | - | [X] [P~] | [x] | - | [x] |
| 4 | Virtual sensors (concept, functions) | [X] | [X] | [X] physical vs virtual [P~] | [x] | [X] | [x] | [X] |
| 5 | VS configurations | [X] | [X] | [x] | [x] | [X] | [X] average | [X] match |
| 6 | System architecture of sensor cloud | [x] | [X] | - | [X] [P~] | [X] | - | [x] |
| 7 | Basic IoT architecture | [X] | [X] | - | [X] [P~] | [X] | - | [X] |
| 8 | Cloud components for IoT | [X] | [x] | - | [X] | [x] | - | [x] |
| 9 | iCOMOT | [X] | [x] | - | [x] | - | - | [x] |
| 10 | IoT infrastructure | [X] | [X] | - | [X] | [x] | - | [x] |
| 11 | IoT protocols | [X] MQTT, CoAP | [x] | [X] MQTT vs CoAP vs HTTP [P~] | [x] | [X] | - | [X] |
| 12 | IoT software platforms | [X] | [x] | [x] | [x] | - | - | [x] |
| 13 | Vehicular data cloud | [x] | [X] | - | [X] [P~] | [X] | - | [x] |
| 14 | V2X, OBU, RSU | [X] | [x] | - | - | [X] | - | [X] |
| 15 | Intelligent parking cloud | [x] | [X] | - | [X] [P~] | [X] | [x] occupancy | [x] |
| 16 | Fog computing (need, fog node) | [X] | [X] | - | [x] | [X] | [x] bandwidth | [X] |
| 17 | Cloud vs Fog | [x] | [x] | [X][X] most probable [P~] | - | [x] | - | [X] |
| 18 | Cloud-Fog-Edge | [X] | [X] | [X] | [X] | [X] | [x] latency | [X] |
| 19 | Health cloud-fog case study | [x] | [X] | [x] | [X] | [X] | - | [x] |
| 20 | Edge computing architecture (5.4) | [X] | [X] | [X] edge vs fog | [x] | [x] | - | [x] |

**Predicted shape of a Module 5 paper (about 10-15 marks):** one "Compare Cloud vs Fog" or "Cloud-Fog-Edge" question; one "Explain architecture of ___ with diagram" (vehicular, parking, sensor cloud or health fog); one short note (virtual sensor, MQTT, fog node, V2X, edge); and possibly a 1-mark item on virtual sensor configuration, gateway or MQTT.

---

## 3. TOPIC-BY-TOPIC BREAKDOWN

**How to score in this subject (derived from the papers):**
- **1 mark:** one precise line.
- **5 marks:** definition, neat diagram, 4-6 points, one example. About one page.
- **10 marks:** intro, labelled diagram, each layer/component in 2-3 lines, working example, advantages (and challenges if relevant), one-line conclusion. About 2 pages. Papers say "draw neat diagrams", so a diagram is worth marks.

---

### 5.1 SENSOR CLOUDS

#### T1. Sensor and Sensor Cloud `[N]`

**Easy explanation.** A sensor measures a physical quantity (temperature, humidity, motion, GPS, heart rate) and converts it into data. One sensor connects to a local computer easily. Millions of sensors spread across places cannot be handled locally. The Sensor Cloud solves this by putting sensors and their data on the cloud.

**Definition (write this):** A Sensor Cloud is a cloud-based environment that allows physical sensors and their data to be shared, accessed, managed, processed and integrated through cloud computing services.

**Formula to remember:** `Sensor Cloud = Sensors + Network + Cloud Computing` (infrastructure version: `+ Virtual Sensors + Cloud Services`).

**Basic flow (diagram for a 1-2 mark answer):**
```
Physical Environment -> Sensors -> Sensor Network / Gateway -> Internet
   -> Cloud Platform [Storage | Processing | Analytics | ML/AI] -> Applications / Users
```

**Core idea:** instead of every application talking to individual sensors, the cloud gives a common platform through which applications access sensor resources.

#### T2. Why needed, features, advantages, challenges, applications `[N]`

**Why needed (6):** large storage, high processing power, scalability, remote access, data analytics, machine learning (prediction, classification, anomaly detection, fault detection, forecasting).

**Features (8):** scalability, elasticity, data sharing, resource virtualization, on-demand resources, remote monitoring, data analytics, fault tolerance.

**Advantages (8):** scalable, cost-effective, large storage, powerful processing, remote accessibility, data analytics, AI/ML integration, resource sharing.

**Challenges (7):**
1. Large data volume
2. Network latency
3. Bandwidth (video sensors produce far more than temperature sensors)
4. Security (authentication, authorization, encryption, access control)
5. Privacy
6. Sensor reliability (failure, wrong readings, lost connectivity, low battery)
7. Energy consumption (battery sensors; communication costs energy)

**Applications:** smart city (traffic, parking, pollution, street lights), smart agriculture, healthcare (wearables, remote monitoring), industrial IoT (predictive maintenance), smart homes, transportation (fleet tracking), environmental monitoring (air, water, weather, forest).

**Exam tip:** for a 5-mark "features/advantages" question, write 6-8 one-line points with a bold keyword each. Pair challenges with fog later; challenges 2-3 (latency, bandwidth) are exactly what fog computing fixes.

**Sensor data processing pipeline `[N]`:**
```
Sensor -> Gateway -> Cloud storage -> Processing (real-time | batch)
       -> Analytics -> ML -> Application
```
- Real-time example: Temp > 50 C, then generate alert.
- Batch example: a month of electricity data, then analytics, then an energy report.

#### T3. Sensor cloud layers (overview) and Sensor Cloud Infrastructure `[N]`

The notes give two layer lists. Use the **infrastructure version** (6 layers) when the question says "Sensor Cloud Infrastructure".

```
+-------------------------------------------------------------+
| F. APPLICATION LAYER   Smart agri | Healthcare | Smart city |
+-------------------------------------------------------------+
| E. CLOUD SERVICE LAYER  Data processing | Analytics | ML     |
+-------------------------------------------------------------+
| D. VIRTUAL SENSOR LAYER  VS1  VS2  VS3 ...  (software)       |
+-------------------------------------------------------------+
| C. SENSOR MANAGEMENT / MIDDLEWARE  Discovery | Registration |
|                                    Configuration            |
+-------------------------------------------------------------+
| B. SENSOR NETWORK / COMMUNICATION  Wi-Fi Zigbee LoRaWAN     |
|                                    BLE 4G/5G MQTT CoAP      |
+-------------------------------------------------------------+
| A. PHYSICAL SENSOR LAYER  Temp | Humidity | Pressure | Motion|
+-------------------------------------------------------------+
```

**Layer explanations (how to write):**
- **A. Physical sensors:** actual hardware that measures real-world quantities (e.g. 10:00 AM 28 C, 10:01 AM 28.2 C).
- **B. Communication:** moves data to the cloud, directly or through a gateway.
- **C. Middleware:** sits between sensors and apps. Discovery ("find temperature sensors in Mumbai" returns T101, T102, T103). Registration (Sensor ID T101, Type Temperature, Location Mumbai, Unit C, Rate 1 min). Configuration (sampling interval 60 s changed to 10 s).
- **D. Virtual sensor layer:** software representation of one or more physical sensors. Apps see VS1 and not the hardware. Gives abstraction, sharing, composition, scalability, flexibility.
- **E. Cloud service:** processing (average temperature) and analytics (traffic data, then ML, then prediction).
- **F. Application:** farmer sees irrigation advice, doctor sees patient monitoring, city sees traffic dashboard.

**Gateway functions `[N]`:** collect data, filter unnecessary data, convert protocols, preliminary processing, forward to cloud.

**Example to include:** an app asks "current temperature of Mumbai". The sensor cloud locates suitable sensors, collects readings, processes them and returns the result. The app never knows which physical sensor was used.

#### T4. Virtual sensors `[N]`

**Easy explanation.** A virtual sensor is the "software twin" or interface of one or many real sensors. Apps talk to the virtual sensor, and the virtual sensor talks to the hardware.

```
Without:  Application -> Physical Sensor
With:     Application -> Virtual Sensor -> Physical Sensor(s)
```

**Why needed:** with 1,000 temperature sensors, apps would otherwise need to know which sensor is available, where it is, its protocol, whether it works and how often it reports. Virtualization hides all of this.

**What a VS contains (from the slides' idea):** ID, type, linked physical sensor(s), location, unit, access permissions, configuration.

**How it works (4 steps `[N]`):**
1. Physical sensor measures (30 C).
2. Sends data (Internet to Cloud).
3. Virtual sensor represents it (VS1 = 30 C).
4. Application requests data (App to VS1 gives 30 C).

**Four functions (write all four with one example each):**

| Function | Meaning | Example |
|---|---|---|
| Abstraction | hides hardware and protocol details | Zigbee sensor and Wi-Fi sensor both appear through one VS interface |
| Sensor sharing | one physical sensor serves many apps | one sensor serves weather, agriculture and monitoring apps |
| Sensor composition | many physical sensors form one VS | temp + humidity + pressure give a Virtual Environment Sensor |
| Data processing | VS returns processed, not raw, data | T1=30, T2=32, T3=31 gives VS = 31 C |

**Physical vs Virtual sensor (table, exactly as in the notes):**

| Physical Sensor | Virtual Sensor |
|---|---|
| Real hardware | Software representation |
| Measures physical phenomenon | Represents/accesses sensor resource |
| Has hardware limitations | Can combine or abstract resources |
| Usually one physical device | Can represent one or multiple sensors |
| Produces raw readings | Can provide processed/combined data |

#### T5. Virtual sensor configurations `[N]` (syllabus-critical)

The syllabus lists four: **one-to-many, many-to-one, many-to-many, derived**. The notes add one-to-one as the baseline. Learn all five, and in the exam always draw the mapping.

```
ONE-TO-ONE            ONE-TO-MANY              MANY-TO-ONE           MANY-TO-MANY
PS --> VS             PS --+--> VS1            PS1 --+               T1 --+--> VS1
                          +--> VS2            PS2 --+--> VS         T2 --+--> VS2
                          +--> VS3            PS3 --+               H1 --+--> VS3
                                                                     P1 --+
```

| Configuration | Meaning | Example `[N]` | Useful for |
|---|---|---|---|
| One-to-one | 1 physical sensor = 1 virtual sensor | T1 = 28 C, VS1 = 28 C | exposing a single sensor directly |
| One-to-many | 1 physical sensor shown as several VSs | T1 gives VS1 (weather app), VS2 (agriculture app), VS3 (smart building app) | resource sharing, different permissions and configurations per app, better sensor utilization |
| Many-to-one | several physical sensors combined into 1 VS | T1=28, T2=30, T3=29 gives VS1 = average = 29 C | average temperature/pollution, noise and regional weather monitoring, fault-tolerant sensing |
| Many-to-many | several physical sensors map to several VSs; one PS can feed multiple VSs and a VS can use multiple PSs. Most flexible | T1, T2 (temp), H1 (humidity), P1 (pressure): VS1 = Avg Temp (T1+T2); VS2 = Environmental Condition (T1+T2+H1+P1); VS3 = Heat Index (Temp + Humidity) | flexible multi-application sensing |
| Derived | VS created by processing/combining data to give a new value or service, using calculations, rules, aggregation, statistics, analytics or ML | Smart agri: Temperature, Humidity, Soil Moisture, Light go to cloud analytics, giving Irrigation Status. Rule: soil moisture < threshold + high temp + low humidity gives "Irrigation Required" | higher-level services |

**Memory trick:** read direction as physical-to-virtual. One-to-many = share. Many-to-one = combine. Many-to-many = both. Derived = compute something new.

**Numericals from the notes:**
- Many-to-one: (28 + 30 + 29) / 3 = 87 / 3 = **29 C**
- Data processing: (30 + 32 + 31) / 3 = 93 / 3 = **31 C**

#### T6. System architecture of sensor cloud infrastructure `[N]` (10-mark favourite)

**Core idea:** physical sensors are virtualized in the cloud so their sensing capabilities can be accessed, shared and managed through software. Resources are dynamically provisioned and shared by different applications.

**Draw this (the layered architecture, deck 1 slide 110):**
```
 USERS / APPLICATIONS   Web | Mobile | IoT apps | APIs | Dashboards
          |
 SENSOR CLOUD SERVICES / MANAGEMENT
   registration | discovery | provisioning | monitoring |
   access control | resource release
          |
 VIRTUALIZATION LAYER   Virtual sensors | Virtual sensor groups
          |   (mapping to physical sensors)
 CLOUD INFRASTRUCTURE   Compute | Storage | Database | Network | Data processing
          |
 GATEWAY / SENSOR NETWORK   Wi-Fi | Zigbee | Bluetooth | LoRaWAN | Cellular
          |
 PHYSICAL SENSORS   Temp | Humidity | Pressure | Light | Motion | Soil | Camera
```

**Six components (explain each in 2-3 lines):**
1. **Physical sensor layer:** actual sensors (Temp 31 C, Humidity 72%, Soil 35%).
2. **Sensor network/gateway:** Wi-Fi, Zigbee, Bluetooth, LoRaWAN, cellular. The gateway does data collection, protocol conversion, filtering and temporary storage.
3. **Cloud infrastructure layer:** compute, storage, database, networking and processing for thousands of readings.
4. **Virtualization layer (the most important part):** a physical sensor is represented by a virtual sensor. Enables sensor sharing, remote access, resource abstraction, dynamic allocation and multi-app use.
5. **Sensor cloud service/management layer:**
   - registration (new sensor registers)
   - discovery (find temperature sensors in Building A)
   - provisioning (VS created when an app requests it)
   - monitoring (availability and status)
   - access control
   - resource release (free resources when the service ends)
6. **User/application layer:** web, mobile, IoT apps, APIs, dashboards. The farmer sees sensor info without contacting the physical sensor.

**Reference diagrams your slides show (draw whichever you remember best, then label):**

**(A) Template/registry model (slide 104):**
```
 Sensor owner --registers sensors--> REGISTRY
 Sensor-Cloud administrator --prepares service templates / manages infra-->
 +------------- SENSOR CLOUD INFRASTRUCTURE -------------+
 |  Template Repository | Sensor Management Service       |
 |  Virtual Sensor Group | Service templates ST-A, ST-B   |
 |  Other IT resources                                    |
 +--------^----------------------------------^------------+
          | Gateway                           | Gateway
    Physical sensors 1                  Physical sensors 2
 End users / Applications 1..n --request service instances (virtual sensors)-->
```
**(B) Se-aaS model (slide 105):** Physical Sensors and Sensor Providers **publish** into the Se-aaS Cloud (Portal Server, Monitoring/Management Server, Provisioning Server, Data Storage). Consumers **request** and **acquire** sensor data. The cloud **subscribes** to providers.

**(C) WSN model (slide 106):** cloud users send sensing requests and receive sensed data. The sensor cloud platform runs cloud computing plus virtual sensor networks. Wireless sensor networks WSN1, WSN2, WSN3 aggregate sensed data to the cloud.

**(D) SCSP model (slide 107):** end users get virtual sensors from the Sensor-Cloud Service Provider (SCSP). Virtual sensors map by dashed lines to physical sensor nodes in Regions 1, 2, 3, owned by sensor owners.

**Complete data flow (smart agriculture `[N]`):**
```
Soil sensor (20%) -> Gateway -> Cloud -> Virtual sensor "Soil Moisture VS" -> Analytics
   -> Irrigation app -> Farmer
```

**Why "Sensor" Cloud? `[N]`** In conventional cloud computing, the resources are servers, storage and networks. In the Sensor Cloud, **sensor resources are treated as cloud resources**: provisioned, shared and metered on demand.

**Model 10-mark answer structure:** definition (2 lines), one diagram (layered or A), six components, data flow example, 4 advantages (resource sharing, scalability, centralized management, abstraction), conclusion.

---

### 5.2 CLOUD IoT

#### T7. Basic IoT architecture `[N]`

**What is IoT:** physical objects equipped with sensors, actuators, processing capability, communication interfaces and software. They collect data, communicate over a network and act on it.

**Example:** `Soil sensor -> Internet -> Cloud -> Data processing -> Decision -> Water pump`.

**Diagram:**
```
+---------------------------------------------------+
| APPLICATION LAYER   Smart Home | City | Healthcare | Farming |
+---------------------------------------------------+
| CLOUD / PROCESSING LAYER  Storage | Analytics | AI/ML | DB | APIs |
+---------------------------------------------------+
| NETWORK / COMMUNICATION LAYER  Wi-Fi | 5G | Ethernet | LoRaWAN | BLE |
+---------------------------------------------------+
| DEVICE / PERCEPTION LAYER  Sensors | Actuators | RFID | Cameras |
+---------------------------------------------------+
```

**Layers (2-3 lines each):**
- **Device/perception:** temperature, humidity, pressure, motion sensors, cameras, GPS, RFID readers, smart meters, actuators. Senses conditions, converts them to digital data, sends them up, receives actuator commands.
- **Network:** transports data to the processing systems.

| Technology | Typical use |
|---|---|
| Wi-Fi | homes/buildings |
| Bluetooth/BLE | wearables, short range |
| Zigbee | smart homes |
| Ethernet | industrial IoT |
| 4G/5G | mobile IoT |
| LoRaWAN | long-range, low-power IoT |
| NB-IoT | cellular IoT |
| RFID | identification/tracking |

- **Processing/cloud:** storage, processing, DBs, analytics, ML, device management, security, APIs. Example: readings 28, 29, 31, 35, 38 give "continuously increasing", so an alert is generated.
- **Application:** smart home, smart healthcare, smart agriculture.

#### T8. Cloud components for IoT `[N]`

```
IoT Devices -> IoT Gateway -> Communication Network ->
[ IoT CLOUD: Device Mgmt | Data Ingestion | Message Broker | Database |
              Data Analytics | AI/ML | Security | APIs ] -> Applications / Users
```

| # | Component | Role |
|---|---|---|
| 1 | Device management | registration, identification, authentication, configuration, monitoring, firmware/software updates, device status |
| 2 | Data ingestion | bring data from devices into the cloud; handles high volume, velocity, multiple types and formats (sensors, then gateway, then cloud) |
| 3 | Message broker | receives messages from devices and distributes them to services. Publish/subscribe via MQTT |
| 4 | IoT database | time-series data; relational, NoSQL, time-series DB, object storage |
| 5 | Cloud analytics | raw data into information (e.g. "irrigation is required") |
| 6 | AI/ML | predictive maintenance, anomaly detection, traffic prediction, energy forecasting, failure prediction |
| 7 | Cloud APIs | Mobile App, then REST API, then IoT Cloud, then Sensor DB (no direct sensor access) |
| 8 | Security | device authentication, authorization, encryption, secure communication, access control, key management, secure firmware updates |

#### T9. iCOMOT: An IoT Cloud System `[N]`

**As in your notes:** iCOMOT is an IoT cloud system providing a cloud-based environment for connecting, managing, collecting data from and using IoT devices. Core concept: `IoT devices + communication + cloud infrastructure + applications`.

```
 Users / Applications
         |
   [ iCOMOT IoT Cloud ]
   /        |          \
 Storage  Analytics  Device Mgmt
   \        |          /
        IoT Gateway
      /      |       \
  Sensor   Sensor   Actuator
```

**Six functions (write all):** device connectivity, data collection, data storage, data processing, device management, application support.

**Why cloud for iCOMOT:** e.g. 10,000 parking sensors + 5,000 traffic sensors + 2,000 environmental sensors. The cloud gives elastic computing, large-scale storage, centralized management, remote access, high availability and analytics.

**`[+]` Caution:** in the research literature (TU Wien group) iCOMOT is described as a tool suite for modelling, deploying, monitoring and elasticity-controlling IoT cloud systems. I am fairly but not fully sure of the exact component names, so for a 10-mark question stick to the notes' functions above and check your textbook for the precise definition.

#### T10. Infrastructure for an IoT cloud system `[N]`

```
IoT SYSTEM
 Sensors/Things   Actuators
      |
 Microcontroller / Embedded device (Arduino, ESP32, Raspberry Pi ...)
      |
 Communication network (Wi-Fi/BLE/Zigbee/LoRaWAN/4G/5G)
      |
 Gateway --> Edge/Fog computing --> Internet --> IoT Platform
 [Storage | Analytics | Device Mgmt] --> Web/Mobile App --> User/Operator
```

**Five infrastructure components + cloud infrastructure:**
1. **Things/sensors and actuators.** Sensors convert quantities into data. Actuators perform actions (motor, relay, valve, LED, door lock, pump). Sensor observes, actuator changes the environment.
2. **IoT devices/embedded systems:** Arduino, ESP32, ESP8266, Raspberry Pi, STM32, BeagleBone, industrial PLCs. They read sensors, digitize, preprocess, connect, send to the platform and receive commands.
3. **IoT gateway** (between devices and the Internet/cloud). Functions: collect, protocol conversion (e.g. Zigbee to IP), filter, aggregate, local processing, security, connect local network to Internet.
4. **Network infrastructure.** Choice depends on distance, power, data rate, cost, reliability, coverage.
5. **Edge/fog infrastructure.** Sending all raw data to the cloud causes high latency, large bandwidth, higher cost and privacy concerns, so process nearer the devices.
6. **Cloud infrastructure:** data storage, data processing (millions of messages), analytics (statistics, ML, anomaly detection, prediction, classification), application services (APIs for web/mobile/dashboards/control systems).

**Smart agriculture end-to-end `[N]`:**
```
Sensors (soil moisture/temp/humidity/rain) -> ESP32 -> LoRaWAN -> LoRaWAN gateway
 -> IoT cloud platform -> Storage -> Analytics ("irrigation needed?") -> Actuator (pump ON if moisture low)
```

#### T11. IoT protocols `[N]`

| Protocol | Full form / type | Key points | Example |
|---|---|---|---|
| MQTT | Message Queuing Telemetry Transport (application) | publish/subscribe with publisher, broker, subscriber. Lightweight, low bandwidth, constrained devices, tolerates unreliable networks | topic `home/room1/temperature`, message 28 C; the broker delivers it to the subscriber |
| CoAP | Constrained Application Protocol | like HTTP for constrained devices; GET, POST, PUT, DELETE; commonly uses UDP so it is lightweight | `GET /temperature` returns 28.5 C |
| HTTP/HTTPS | Hypertext Transfer Protocol | used when the device has enough resources; HTTPS = encrypted with TLS, needed for sensitive data | `POST /sensor/data` |
| AMQP | Advanced Message Queuing Protocol | reliable messaging, queuing, routing, delivery guarantees; more feature-rich than MQTT | enterprise messaging |
| WebSocket | persistent two-way channel | real-time updates without polling | live dashboard |

**Connectivity technologies (use-case view):**

| Technology | Use when |
|---|---|
| Wi-Fi | high data rate, power available, near access point (smart cameras) |
| BLE | low power, short range (fitness bands, smart watches, medical sensors) |
| Zigbee | low-power mesh (smart homes, building automation, sensor networks) |
| LoRaWAN | long range + low power + low data rate (agriculture, smart cities, environment) |
| Cellular IoT (4G LTE, 5G, NB-IoT, LTE-M) | connected vehicles, smart meters, asset tracking |

**Compare MQTT vs CoAP vs HTTP (for a compare question; only the first two rows below are from notes, the rest `[+]` general knowledge):**

| Feature | MQTT | CoAP | HTTP |
|---|---|---|---|
| Model | publish/subscribe via broker `[N]` | request/response (GET/POST/PUT/DELETE) `[N]` | request/response `[N]` |
| Transport | `[+]` TCP | UDP commonly `[N]` | `[+]` TCP |
| Weight | lightweight `[N]` | lightweight `[N]` | heavier; for devices with enough resources `[N]` |

#### T12. IoT software platforms `[N]`

**Definition:** software services needed to manage devices, collect data, process information and build applications.

**Functions:**
- **Device management:** register, identify, monitor, update firmware, configure, disable. Sample record: Device D1001, Temperature Sensor, Online, Battery 82%, 27.4 C.
- **Data collection:** from thousands or millions of devices.
- **Data storage:** time-stamped data (25, 25.2, 25.4, 25.7 C) kept for history, monitoring, ML, prediction and auditing.
- **Analytics:** descriptive (temperature reached 85 C), predictive ("may need maintenance soon"), prescriptive (reduce load or start maintenance).
- **Dashboards:** readings, status, alerts, graphs, maps, trends.

**Examples:** AWS IoT (connectivity, device management, message routing, security, processing, AWS integration), Microsoft Azure IoT (connectivity, management, processing, analytics, cloud integration), ThingsBoard (device management, telemetry, dashboards, rule processing; monitoring and prototyping), Eclipse IoT (open source, MQTT-related and device communication software).

**IoT security infrastructure `[N]`:** device identity, authentication ("is this device allowed to connect?"), authorization ("what may it do?"), encryption in transit, secure/authenticated firmware updates.

#### T13/T14. Architecture for IoT-based vehicular data clouds `[N]`

**Definition:** a cloud-based system in which vehicles act as IoT devices generating data continuously. The data goes through communication networks, is processed at edge/fog/cloud, and used for traffic management, navigation, monitoring, accident detection and predictive maintenance. It combines IoT + vehicular networks + edge/fog + cloud.

**Vehicle data sources:** GPS (location, speed), accelerometer (braking), engine sensors, fuel sensor, temperature sensor, camera, proximity sensors, OBD-II (diagnostics).

**Why a cloud:** 10,000 vehicles generate large, fast-changing data. The cloud gives large-scale storage, processing, analytics and ML.

**Draw this (5-layer view, deck 2 slide 82/107):**
```
+------------------------------------------------------------+
| APPLICATION  Traffic mgmt | Navigation | Parking | Fleet |  |
|              Emergency | Predictive maintenance            |
+------------------------------------------------------------+
| CLOUD SERVICES  Storage | Big-data analytics | ML | DB |     |
|                 APIs | Visualization | Data processing     |
+------------------------------------------------------------+
| EDGE / FOG  RSUs | Edge servers | Local processing |         |
|             Traffic analysis | Filtering | Alerts          |
+------------------------------------------------------------+
| COMMUNICATION  4G/5G | Wi-Fi | DSRC / C-V2X | Internet      |
+------------------------------------------------------------+
| VEHICLE / IoT  GPS | Cameras | Engine | Speed | OBD | OBU    |
+------------------------------------------------------------+
```

**Basic data flow (deck 2 slides 79/95):**
```
Sensors -> OBU -> Wireless network -> RSU -> Edge/Fog server -> Internet/5G
   -> Vehicular Cloud -> Data analytics -> Application
```

**Components:**
- **Vehicle/IoT layer:** e.g. Vehicle V102, location 19.0760/72.8777, speed 55 km/h, fuel 62%, engine 85 C, brakes normal.
- **On-Board Unit (OBU):** collects sensor data, processes, temporarily stores, talks to other vehicles and roadside infrastructure, sends data to cloud/edge, receives commands.
- **Communication layer:** 4G/5G (wide area), Wi-Fi (parking, service stations, roadside), **DSRC** (Dedicated Short-Range Communications, built for vehicles), **C-V2X** (Cellular Vehicle-to-Everything).
- **V2X types:**

| Type | Meaning | Example |
|---|---|---|
| V2V | vehicle to vehicle | A detects sudden braking, alerts B |
| V2I | vehicle to infrastructure | receives traffic signal info from roadside unit |
| V2N | vehicle to network | talks to cloud via cellular/Internet |
| V2P | vehicle to pedestrian | detects pedestrians with connected devices |

- **Roadside Unit (RSU):** receives and forwards vehicle data, broadcasts traffic info, connects vehicles to edge/cloud.
- **Edge/fog layer:** critical because vehicles move fast and need low latency. An accident is processed at the edge server and a local warning is issued without the long cloud path.
- **Cloud layer:** storage (locations, traffic, readings, history, accidents), processing, big-data analytics, ML (traffic prediction, accident-risk analysis, predictive maintenance, route optimization, anomaly detection). Stores real-time data (current location, speed, traffic) and historical data (patterns, routes, accidents, maintenance).
- **Applications (7):** traffic management, navigation, fleet management, predictive maintenance, accident detection, emergency services, intelligent parking.

**Examples:** *congestion detection:* vehicle speed 20 km/h on Highway X, many nearby vehicles slow, cloud analytics detects congestion, traffic management system suggests an alternative route. *Edge vs cloud:* immediate collision warning goes to edge/fog; analysis of the last 6 months' traffic goes to cloud.

**Security:** device authentication, encryption, secure communication, access control, data integrity, secure software updates, privacy protection.

#### T15. Architecture for Intelligent Parking Cloud Service `[N]`

**Definition:** a Cloud-IoT system that uses sensors, communication networks, cloud computing, databases and mobile/web apps to detect parking-space availability and offer parking services (find, reserve, navigate, pay).

**Draw this (5-layer view, deck 2 slide 132):**
```
+----------------------------------------------------+
| 5. APPLICATION LAYER   Mobile App | Web | Navigation | Pay |
+----------------------------------------------------+
| 4. CLOUD SERVICE LAYER  Availability | Reservation | Payment |
|                         Management | Analytics            |
+----------------------------------------------------+
| 3. CLOUD DATA LAYER   Database | Storage | Processing   |
+----------------------------------------------------+
| 2. COMMUNICATION LAYER  Gateway | Wi-Fi | 4G/5G | LPWAN  |
+----------------------------------------------------+
| 1. SENSOR LAYER   Parking sensors | Cameras | RFID      |
+----------------------------------------------------+
```

**Explanation:**
1. **Sensor layer:** ultrasonic, magnetic, infrared, camera, RFID. Decide Occupied or Available (P1 occupied, P2 available, P3 available, P4 occupied).
2. **Gateway:** collects from many sensors, aggregates, converts protocols, does local processing, talks to the cloud (e.g. low-power wireless locally, IP to the cloud).
3. **Communication network:** Sensors, then Gateway, then Cloud. Technologies: Wi-Fi, BLE, Zigbee, LoRaWAN, 4G/5G, Ethernet. Choice depends on parking-area size, range, power, number of sensors, data rate.
4. **Cloud platform and services:**
   - **Parking management:** locations, spaces, occupied/available, zones, rates, hours (Mall: 500 total, 420 occupied, 80 available).
   - **Availability:** processes sensor data, shows "2 parking spaces available".
   - **Reservation:** User reserves P23, cloud marks P23 RESERVED so nobody else takes it.
   - **Navigation:** guides to the space (P25, 120 m away).
   - **Payment:** calculates and processes fees.
5. **Cloud database:** parking information, user information, reservations, history.
6. **Analytics:** 9-11 AM high occupancy, 11 AM-2 PM medium, 6-8 PM high, which helps operators manage capacity.
7. **User application:** mobile, web, in-car app, display boards (find, check, reserve, navigate, fee, pay, history).

**Working example (8 steps `[N]`):** sensors detect status, gateway collects P1-P4, gateway sends to cloud over the Internet, cloud DB updates (P3, P4 available), user opens app and sees P3, P4, user reserves P3 (RESERVED), app navigates, sensor detects the vehicle and the cloud updates P3 = OCCUPIED.

**Key features table `[N]`:** real-time monitoring, cloud storage, virtualization (parking/sensing resources as services), reservation, navigation, payment, analytics, scalability (many areas and users), remote management.

**Numerical (from notes data):** Mall parking 500 total, 420 occupied → available = 500 - 420 = **80**, occupancy = 420/500 = **84%**.

---

### 5.3 FOG COMPUTING

#### T16. Fog computing `[N]`

**Definition (write this):** Fog computing is an extension of cloud computing toward the edge of the network. It places computing, storage, networking and data-processing resources between IoT devices and centralized cloud data centers, so processing happens closer to the data source.

**Traditional cloud:** `IoT Sensors -> Internet -> Cloud DC -> Processing -> Response`. Problems: high network traffic, higher latency, more bandwidth, delayed responses, dependence on connectivity.

**Fog:** `IoT Sensors -> Fog Node -> Processing/Filtering/Analysis -> Cloud`.

**Architecture diagram (deck 3 slide 18):**
```
+--------------------------------------------------+
| CLOUD  Large-scale storage | Big-data analytics |  |
|        ML | Long-term processing                  |
+--------------------------------------------------+
        | Internet
+--------------------------------------------------+
| FOG    Local processing | Data filtering |         |
|        Data aggregation | Real-time analytics |    |
|        Local decision making                      |
+--------------------------------------------------+
        | Local network
+--------------------------------------------------+
| IoT DEVICES  Sensors | Actuators | Cameras |       |
|              Vehicles | Smart meters               |
+--------------------------------------------------+
```

**Why fog is needed (9 reasons `[N]`):**
1. Reduce latency (Device, Internet, Cloud, Processing, Device is slow; matters for autonomous vehicles, emergency healthcare, industrial control, traffic).
2. Reduce bandwidth (10,000 cameras: send events instead of raw video).
3. Reduce cloud overload (hierarchical distribution).
4. Support real-time applications (millisecond/second decisions).
5. Reduce network traffic (filter, aggregate, compress, send only important events).
6. Continue during connectivity loss (local processing, then sync when restored).
7. Improve privacy (process healthcare, video, industrial, location data locally).
8. Support geographically distributed IoT (cities, factories, farms, hospitals, vehicles).
9. Enable local decision making (smart factory).

**Fog node:** a device between IoT devices and the cloud that does processing, filtering, aggregation, storage, analytics, security and local decision-making. Examples: routers, gateways, local servers, switches, industrial computers, edge servers, access points.

**How fog works (factory temperature `[N]`):**
```
Sensors (28,29,30,31,32...) -> Fog node
Temperature > 80 C?  Yes -> Generate alert
                      No  -> Continue
Normal data -> filter/aggregate | Critical event -> send immediately to cloud
```

**Smart traffic example:** without fog, all camera data goes to the cloud. With fog, the fog node decides immediately and sends only useful information to the cloud.

**Autonomous vehicle example `[N]`:** camera/sensor, then fog/edge processor, then immediate decision (brake/avoid). Cloud is used for historical data, ML training, fleet analytics and long-term storage.

**Fog and cloud work together; fog does not replace the cloud.** Fog answers "what must happen immediately?" Cloud answers "what should we store, analyze and learn from over a longer period?"

#### T17. Cloud vs Fog Computing `[N]` (highest-probability compare question)

**Core statement:** Cloud = centralized processing far from devices. Fog = distributed processing closer to devices.

| Feature | Cloud Computing | Fog Computing |
|---|---|---|
| Processing location | centralized cloud data center | closer to IoT devices |
| Distance from devices | usually far | near |
| Latency | higher | lower |
| Bandwidth usage | can be high | can be reduced |
| Response time | relatively slower | faster |
| Storage capacity | very high | usually limited |
| Computing power | very high | lower than cloud |
| Internet dependency | generally high | can reduce dependency |
| Scalability | very high | moderate |
| Suitable for | large-scale processing and storage | real-time/local processing |
| IoT support | yes | particularly useful |
| Data processing | mostly centralized | distributed |
| Example | AWS cloud analytics | IoT gateway processing |

**Slide figures worth mentioning:**
- Cloud-fog-edge pyramid: **thousands of data centers, millions of nodes, billions of devices**.
- Layer-trend figure: computing power, reliability, data storage and latency are higher toward the cloud; mobility, location awareness and interactivity are higher toward the edge.

**Intelligent parking illustration `[N]`:** cloud-only sends every sensor's data to the cloud. Fog processes locally first, then sends summaries.

#### T18. Cloud-Fog-Edge Computing `[N]`

**Three tiers (diagram):**
```
CLOUD  (centralized)    Data centers | Big data | AI/ML | Long-term storage
   ^  Internet
FOG    (intermediate)   Fog servers | IoT gateways | Local servers | Regional analytics
   ^  Local network
EDGE   (near the source) Cameras | Sensors | Vehicles | Controllers | Smartphones
```

| Tier | Where | Role | Examples |
|---|---|---|---|
| Edge | on or very near the device | ultra-low latency, local processing, real-time response, reduced bandwidth | sensors, cameras, smartphones, industrial controllers, smart vehicles, IoT gateways, embedded computers |
| Fog | between edge and cloud | geographically distributed, intermediate processing, low latency, data aggregation, supports many edge devices, connects edge and cloud. More powerful than an edge device but nearer than the cloud | IoT gateways, local servers, routers, access points, base stations, micro data centers |
| Cloud | centralized/distributed data centers | massive storage, high processing, elastic scalability, big-data analytics, backup, hosting. Limitation: latency | AWS, Azure, Google Cloud |

**Focus summary:** Cloud = large-scale computation and storage. Fog = local/regional processing and reduced latency. Edge = as close as possible to the data source. **Cloud = centralized, Fog = intermediate, Edge = near the source.**

**Edge example (smart camera):** `Camera -> Edge device -> detect person -> response`, only important information goes to the cloud. **Fog example:** 1,000 traffic cameras to a local fog server, which analyses traffic and sends only useful info to the cloud.

**Smart parking across all three `[N]`:**
- Edge: sensors say Space 1 occupied, 2 empty, 3 occupied.
- Fog: a nearby server collects hundreds of spaces, giving Zone A = 15 free, Zone B = 3 free.
- Cloud: historical analysis gives peak parking time and future demand prediction.

**Short note on "Cloud-Fog-Edge" 5 marks:** definition, 3-tier diagram, one line per tier, smart parking example.

#### T19. Case study: Health Cloud-Fog Model `[N]`

**Definition:** a model combining IoT healthcare devices, fog computing and cloud computing to give faster, reliable and secure healthcare. Urgent data is processed near the patient, while large or historical data goes to the cloud for storage and advanced analysis.

**Why in healthcare (6):** low latency (emergencies), reduced bandwidth (10,000 readings go to 100 important records, then to cloud), faster emergency response, reduced cloud workload, better availability (local services continue offline), privacy. Note: fog does not automatically guarantee privacy; encryption, authentication and access control are still required.

**Architecture (draw 3 layers as in the slide, mention the 4th):**
```
+----------------------- CLOUD LAYER -----------------------+
| Analytics | Permanent storage | ML | Patient records |    |
| Long-term decision making by medical personnel            |
+-----------------------------------------------------------+
        ^  Internet
+----------------------- FOG LAYER -------------------------+
| Border router / gateway | Local router | Local server nodes |
| Local processing | Filtering | Emergency detection |       |
| Alarm triggering | -> Emergency response (ambulance/doctor)|
+-----------------------------------------------------------+
        ^  Hospital / local network (Wi-Fi, BLE)
+-------------------- SENSING / DEVICE LAYER ---------------+
| ECG | BP | SpO2 | heart rate | temp | glucose | fall detector |
| Patient, elderly people | Arduino, Raspberry Pi | actuator |
+-----------------------------------------------------------+
```
The notes describe four layers: (1) healthcare/IoT devices, (2) edge/fog layer, (3) cloud layer, (4) healthcare applications (doctor dashboard, patient app, hospital management system, remote monitoring, emergency alert). If asked for "four layers", draw the diagram above and add the application layer on top.

**Working (6 steps `[N]`):**
1. **Data collection:** sensors monitor heart rate, ECG, BP, oxygen, temperature (e.g. 145 BPM).
2. **Sent to fog node** (sensor to fog gateway), not directly to the cloud.
3. **Fog processing:** 75 BPM is normal (store/send periodically). 145 BPM is abnormal (generate emergency alert).
4. **Immediate response:** activate alarm, notify nurse/doctor, SMS/app notification, trigger emergency procedures. Low latency.
5. **Cloud storage:** patient history, ECG records, readings, reports, medication info, previous emergencies.
6. **Cloud analytics:** long-term analysis, disease prediction, ML, risk analysis, population health.

**Cloud vs Fog in healthcare `[N]`:**

| Feature | Cloud | Fog |
|---|---|---|
| Location | remote data center | near patient/device |
| Processing | large-scale | local/nearby |
| Latency | relatively higher | low |
| Storage | very high | limited |
| Computing power | very high | moderate |
| Emergency response | less suitable for immediate local response | highly suitable |
| Long-term analytics | excellent | limited |
| Bandwidth usage | can be high | can reduce transmission |
| Patient monitoring | historical/centralized analysis | real-time monitoring |

**Applications (7):** remote patient monitoring, emergency healthcare, smart hospitals, ambulance monitoring, elderly care (fall detection), chronic disease management (diabetes, hypertension, heart disease), telemedicine.

**Advantages (10):** low latency, real-time monitoring, fast emergency response, reduced bandwidth, reduced cloud workload, improved availability, local data processing, scalable healthcare IoT, support for AI/ML analytics, better handling of large sensor data.

**Challenges (6):** security, privacy, fog node management (hundreds or thousands of nodes), resource limitations (less than cloud), reliability (a failed fog node must not interrupt critical services), interoperability (devices from different manufacturers).

**Remote patient monitoring example:** an elderly patient at home. Sensors send data to the fog node, which immediately identifies that the patient may need medical attention and alerts.

---

### 5.4 SELF-LEARNING: EDGE COMPUTING ARCHITECTURE

Your notes do not cover this topic as its own section. The edge material in deck 3 (slides 50-52, 59-60 and the layered figures) is `[N]`. The rest below is `[+]` or `[S]`, so please verify it against your textbook or lecture notes.

**Definition `[N]`:** processing data close to where it is generated, on or very near the IoT device, instead of sending everything to the cloud.

**Edge devices `[N]`:** sensors, cameras, smartphones, industrial controllers, smart vehicles, IoT gateways, embedded computers.

**Benefits `[N]`:** ultra-low latency, local processing, real-time response, reduced bandwidth, distributed computing.

**Architecture (layered figure in deck 3 slide 43 `[N]`, redrawn):**
```
CLOUD DATA CENTERS   Big-data analytics, AI/ML; advanced processing, long-term storage
        ^  (higher latency, more computational resource)
FOG NODES            Data and computational orchestration; distributed processing
        ^
EDGE NODES           Edge AI; real-time / near-real-time processing
        ^  (closest to data generation, lowest latency)
IoT NODES            Data sensing; aggregation, preprocessing, routing
```
Workload shifts upward toward the cloud, and data flows from the devices upward. In your slide, the left arrow indicates workload and the right arrow indicates data.

**Edge vs Fog (`[S]` compare table, based on slide 53 and 59):**

| Point | Edge | Fog |
|---|---|---|
| Location | on/in the device or its gateway | intermediate layer between edge and cloud |
| Power | limited | more powerful than a single edge device |
| Scope | one device or a small group | many edge devices / a region |
| Role | ultra-low-latency, immediate response | aggregation, regional analytics, connects edge and cloud |
| Examples | camera, smartphone, controller | gateways, local servers, routers, micro data centers |

**`[+]` Extra points that may help:** common edge deployment pattern is device, then edge node (runs a small ML model for inference), then fog/regional server, then cloud (trains the model). Check your textbook for named architectures such as MEC (Multi-access Edge Computing).

---

### NUMERICALS AND CALCULATIONS (all Module 5 numerical-style items)

None of the PYQs have numericals. The notes contain several small calculations, and I added a few `[S]` ones in case a short numerical is asked.

| # | Problem | Solution |
|---|---|---|
| N1 `[N]` | Three sensors report T1=28, T2=30, T3=29 C. Many-to-one VS gives the average. | (28+30+29)/3 = 87/3 = **29 C** |
| N2 `[N]` | T1=30, T2=32, T3=31 C. VS returns the average. | 93/3 = **31 C** |
| N3 `[N]` | Mall parking: total 500, occupied 420. Available? Occupancy? | 500 − 420 = **80**; 420/500 = **84%** |
| N4 `[N]` | Fog filters 10,000 sensor readings down to 100 important records. Reduction? | (10,000 − 100)/10,000 = **99%** reduction |
| N5 `[S]` | 1,000 cameras each produce 4 Mbps. Raw cloud traffic? If fog forwards only 1%? | 1,000 × 4 = **4,000 Mbps (4 Gbps)**; 1% = **40 Mbps** |
| N6 `[S]` | Cloud round trip = 100 ms; fog = 10 ms. A vehicle at 90 km/h: distance covered while waiting for each response? | 90 km/h = 25 m/s. Cloud: 25 × 0.1 = **2.5 m**. Fog: 25 × 0.01 = **0.25 m** |
| N7 `[S]` | 1,000 temperature sensors, 1 reading/min, 4 bytes each (ignoring headers). Daily data? | 1,000 × 1,440 = 1,440,000 readings; × 4 B = 5.76 MB/day |
| N8 `[S]` | Many-to-many: T1=28, T2=30, H1=60%, P1=1010 hPa. VS1 = Avg Temp; VS2 uses T1+T2+H1+P1; VS3 = Heat Index (Temp + Humidity). Show VS1 and the mapping. | VS1 = (28+30)/2 = **29 C**. Mapping: T1→{VS1,VS2}, T2→{VS1,VS2}, H1→{VS2,VS3}, P1→{VS2}; T1 and T2 also feed VS3 via Temperature. Notes give the structure, not a heat-index formula, so do not compute VS3's value in the exam unless a formula is given. |

---

## 4. PYQ ANALYSIS AND SOLUTIONS

### 4.1 Audit of every uploaded paper against Module 5

| Paper | What it asks (grouped) | Module 5 content? |
|---|---|---|
| Jan-Apr 2025 ESE (100m) | cloud characteristics, levels of virtualization, XaaS, Aneka framework/foundation/fabric/scheduling services, microservices, SOA, MapReduce, deployment models, VM files and migration, Docker commands, AWS EC2 types/S3/architecture, Google AppEngine, impact of cloud data centres on environment, Mobility as a Service | None. Only "Mobility as a Service" is adjacent (see 4.2) |
| Dec 2022 ESE (100m) | SaaS, scalability vs elasticity, private vs public cloud, SAN vs NAS, Jenkins/CI, Web 2.0, utility computing, PaaS, machine reference model, Hyper-V, Aneka (container, logical organization, private/public deployment), AppEngine, DVFS/power management, cloud federation, Docker, MBASS, Xen, VMware, Spot Cloud, MAAS | None directly. "MBASS" and "MAAS" are ambiguous (see 4.2) |
| Nov-Dec 2021 (50m) | matching on VT-x/VT-d/EPT, AppEngine technologies, cloud federation, Aneka items, physical vs actual core, Web 1.0/2.0/3.0, cloud reference model, PaaS, SimpleDB vs RDS, server consolidation, hardware vs software power management, legal issues of federation / MOCC, AppEngine components, MaaS, hybrid Aneka | None directly. "MaaS" is adjacent (see 4.2) |
| May-Jun 2021 (50m, Distributed and Cloud Computing) | power-management layers, parallel programming models, VM live migration, SAN/LAN/NAS, reliability/availability/serviceability, Microsoft offerings, Top 500, enabling technologies, hypervisor vs para-virtualization, service registry, stateless web services, WS-* vs REST, demand-driven vs event-driven provisioning, virtual clusters, GPU vs CPU, cluster job management, public vs private clouds, Google App Engine/HUBzero/OGCE | None |

**Result: zero Module 5 questions appear in any of the four papers.**

**Inference (not certain):** Module 5 looks like newer syllabus material, and 5.4 being "Self-Learning" supports that. So expect unseen questions, framed in the same styles the papers use (architecture with diagram, compare, short notes, 1-mark items).

**What I excluded and why:** all questions on Aneka, virtualization, AppEngine, AWS, Docker, microservices, power management, federation, web services and cluster computing belong to other modules, so I did not solve them, per your instruction to use only this module's PYQs. If you want them solved, I can do that module by module.

### 4.2 Borderline items (Mobility as a Service / MaaS) `[+]`

These appear three times: Jan-Apr 2025 Q5(vi) "Mobility as a Service" (5m), Nov-Dec 2021 Q3 OR "What is the MaaS? Describe the components of MaaS" (10m), and Dec 2022 Q5 "MAAS" (5m).

I cannot tell for sure which module owns them, and in the 2021/2022 papers the acronym could mean something else. I am treating them as Mobility as a Service because the 2025 paper spells it out. It is thematically close to 5.2 (vehicular cloud, intelligent parking). Below is a general-knowledge answer (not from your notes) in case your course ties it to this module. Please check which module your faculty assigns it to before relying on it.

**Mobility as a Service (5-mark answer):**
MaaS integrates different transport services (buses, metro, taxis, bike/car sharing, parking) into a single on-demand service, accessed through one digital platform with a single booking and payment.

**Components (for the 10-mark version):**
1. **Transport service providers:** public transit, ride-hailing, car/bike sharing, parking operators.
2. **MaaS integrator/platform (cloud):** journey planning, booking, ticketing, routing across providers.
3. **Data layer:** real-time data from vehicles and IoT sensors (GPS, parking sensors) via open APIs.
4. **Payment and ticketing system:** one account and one bill across modes.
5. **User application:** mobile/web app for planning, booking, navigating and paying.
6. **Authorities/regulation:** policies, data sharing rules, standards.

**Link to Module 5:** the vehicular data cloud supplies real-time traffic and vehicle data, and the intelligent parking cloud supplies availability, reservation and payment, so a MaaS platform can combine them.

### 4.3 Predicted questions in the papers' style (`[S]`, with answer map)

Since there are no real PYQs, here are the questions most likely to come, written in the papers' phrasing. Each maps to the full answer content above and to the exact structure to follow.

| # | Predicted question (style source) | Marks | Answer where | Structure to write |
|---|---|---|---|---|
| 1 | What is a sensor cloud? Explain its architecture with a diagram. (like "Aneka framework with diagram") | 10 | T3 + T6 | definition, formula, layered diagram, 6 components, data flow example, advantages |
| 2 | Explain virtual sensor configurations with examples. | 5-10 | T5 | table of 5 configs, mapping diagram, averaging example |
| 3 | Compare physical sensor and virtual sensor. (like "compare physical core with actual core") | 5 | T4 | 5-row table, one example |
| 4 | Write short notes on virtual sensors. | 5 | T4 | definition, 4 functions, example, diagram |
| 5 | Explain the basic IoT architecture and cloud components for IoT. | 10 | T7 + T8 | 4-layer diagram, then 8 cloud components |
| 6 | Explain MQTT / compare MQTT, CoAP and HTTP. | 5 | T11 | publisher-broker-subscriber diagram, topic example, advantages |
| 7 | Explain the architecture of an IoT-based vehicular data cloud with a neat diagram. | 10 | T13/T14 | 5-layer diagram, OBU, RSU, V2X, edge vs cloud, applications |
| 8 | Explain the architecture of an Intelligent Parking Cloud service. | 10 | T15 | 5-layer diagram, services, 8-step example |
| 9 | What is fog computing? Why is it needed? | 5 | T16 | definition, diagram, 5-6 reasons, example |
| 10 | Differentiate between cloud and fog computing. (like "compare private and public cloud") | 5 | T17 | 8-10 row table + one line "centralized vs distributed" |
| 11 | Explain cloud-fog-edge computing with a suitable example. | 5-10 | T18 | 3-tier diagram, role per tier, smart parking |
| 12 | Explain the Health Cloud-Fog model. | 10 | T19 | 3-4 layer diagram, 6-step working, advantages, challenges |
| 13 | Write short notes on any four: V2X, OBU/RSU, fog node, iCOMOT, edge computing, LoRaWAN, IoT gateway. (like Q5 "any four") | 20 | respective sections | 5 marks each: definition, diagram/example, 4 points |
| 14 | 1-mark items (like Q1A in the 2021 papers): define virtual sensor; "the ____ converts Zigbee to IP"; match VS configuration to example; "fog node lies between ____ and ____" | 1-2 | notes | one line each |

**Sample 1-mark and match items with answers `[S]`:**
- A software representation of one or more physical sensors is a ______. **Virtual sensor.**
- The IoT component that converts Zigbee to IP-based communication is the ______. **Gateway.**
- MQTT follows the ______ model. **Publish/subscribe.**
- Fog nodes lie between ______ and ______. **IoT devices and the cloud.**
- V2I stands for ______. **Vehicle to Infrastructure.**
- Match: (a) One-to-many (b) Many-to-one (c) Derived. (i) Irrigation Status from several sensors (ii) T1, T2, T3 give average (iii) one sensor serves 3 apps. **a-iii, b-ii, c-i.**

---

## 5. 10-MINUTE REVISION SHEET

- **Sensor Cloud** = Sensors + Network + Cloud (+ Virtual Sensors + Services). Key idea: sensor resources treated as cloud resources.
- **Layers:** physical sensor, network/gateway, middleware (discovery, registration, configuration), virtual sensor, cloud service, application.
- **Virtual sensor functions:** abstraction, sharing, composition, data processing.
- **Configurations:** one-to-many (share), many-to-one (combine, average), many-to-many (both), derived (compute a new service such as irrigation status). Averages: 29 C, 31 C.
- **IoT 4 layers:** device, network, cloud, application.
- **IoT cloud components (8):** device mgmt, ingestion, broker, DB, analytics, AI/ML, APIs, security.
- **Protocols:** MQTT (pub/sub, broker), CoAP (UDP, GET/POST/PUT/DELETE), HTTP/HTTPS, AMQP (reliable queuing), WebSocket (two-way real-time). Connectivity: Wi-Fi, BLE, Zigbee, LoRaWAN, cellular.
- **Vehicular cloud:** vehicle + OBU, communication (DSRC, C-V2X, 4G/5G, Wi-Fi), RSU, edge/fog, cloud, applications. V2V, V2I, V2N, V2P.
- **Parking cloud:** sensor, gateway/communication, cloud data, cloud services (availability, reservation, navigation, payment, analytics), app. Example 500/420/80.
- **Fog:** between devices and cloud; reduces latency, bandwidth, cloud load; local decisions; works offline; improves privacy (not guaranteed).
- **Cloud vs Fog:** centralized, far, high latency, huge storage vs distributed, near, low latency, limited storage.
- **Cloud-Fog-Edge:** centralized, intermediate, near the source. Thousands of data centers, millions of nodes, billions of devices.
- **Health cloud-fog:** sensors, fog (alert on 145 BPM), cloud (history, ML), apps.

---

**Next step:** tell me if you want the excluded PYQs (Aneka, virtualization, AppEngine, Docker, microservices and so on) solved module by module, and send the next module's files when ready.
