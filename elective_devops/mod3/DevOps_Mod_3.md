# DevOps - Module 3: Cloud, Artifact Management and Containerization

> **Syllabus Reference:**
> 3.1 Introduction to Cloud Computing (IaaS) | Server setup & deployment on cloud (Linode) | Linux user configuration on cloud | Artifact Repository (Nexus): setup, repository types, REST API | Blob store, cleanup policies
> 3.2 Introduction to Containers and Docker | Docker architecture, commands, volumes, networking | Dockerfile and Docker Compose | Private Docker repositories and deployment

> **Marks: 09 hours, 3 credits**

> **Legend:** Items marked `[SG]` are self-generated — not directly from the provided notes or official PYQs, but based on the syllabus topics.

---

## DELIVERABLE 1 — TOPIC MAP

```
Module 3: Cloud, Artifact Management and Containerization
|
+-- 3.1  Cloud Computing (IaaS) and Artifact Management
|   |
|   +-- Introduction to Cloud Computing
|   |   +-- Cloud Service Models
|   |   |   +-- IaaS (Infrastructure as a Service)
|   |   |   +-- PaaS (Platform as a Service)
|   |   |   +-- SaaS (Software as a Service)
|   |   +-- IaaS Key Characteristics
|   |       +-- On-Demand Compute
|   |       +-- Elastic and Scalable
|   |       +-- Self-Managed Stack
|   |       +-- Full Root Access
|   |
|   +-- Server Setup and Deployment on Cloud (Linode)
|   |   +-- Provisioning a Cloud Server (steps)
|   |   +-- First SSH Login and Basic Hardening (ufw, hostname)
|   |   +-- Deploying an Application (runtime, process manager)
|   |
|   +-- Linux User Configuration on Cloud
|   |   +-- Creating and Managing Users (useradd, passwd, deluser)
|   |   +-- Groups (groupadd, usermod -aG)
|   |   +-- Sudo Access (not root day-to-day)
|   |   +-- SSH Key Authentication (ssh-keygen, ssh-copy-id)
|   |   +-- Hardening sshd_config (PermitRootLogin, PasswordAuthentication)
|   |
|   +-- Artifact Repository (Nexus)
|   |   +-- What is an Artifact?
|   |   |   +-- Types: JAR, WAR, APK, .whl, Docker Image, build folder
|   |   |   +-- Artifacts vs Source Code
|   |   +-- Why an Artifact Repository?
|   |   +-- Nexus Repository Manager
|   |   |   +-- Setup and Initial Configuration (Docker-based)
|   |   |   +-- Repository Types
|   |   |   |   +-- Hosted
|   |   |   |   +-- Proxy
|   |   |   |   +-- Group
|   |   +-- Nexus REST API
|   |       +-- Upload artifact (curl --upload-file)
|   |       +-- Download artifact
|   |       +-- Search components
|   |       +-- Delete component
|   |
|   +-- Blob Store and Cleanup Policies
|       +-- What is a Blob Store?
|       +-- File-based vs S3-backed
|       +-- Cleanup Policies
|           +-- Criteria: Published before, Last downloaded, Regex
|           +-- Compact Blob Store task (two-step reclaim)
|
+-- 3.2  Containers and Docker
    |
    +-- Introduction to Containers
    |   +-- What is a Container?
    |   +-- The "works on my machine" problem
    |   +-- Container vs Virtual Machine
    |
    +-- Docker Architecture
    |   +-- Client-Server Architecture
    |   +-- Docker Client (CLI)
    |   +-- Docker Daemon (dockerd)
    |   +-- Docker Host
    |   +-- Docker Engine (daemon + REST API + CLI)
    |   +-- Docker Registry (Docker Hub / Private)
    |   +-- Docker Objects (Images, Containers, Volumes, Networks)
    |
    +-- Docker Commands
    |   +-- Image commands (pull, build, images, rmi, tag, push)
    |   +-- Container commands (run, ps, stop, start, rm, exec, logs, inspect)
    |   +-- Volume commands (volume create, volume ls)
    |   +-- Network commands (network create, network ls, network inspect)
    |   +-- Port Mapping (-p host:container  vs  -P)
    |   +-- Foreground Mode vs Detached Mode (-d flag)
    |   +-- docker attach, docker exec
    |
    +-- Container Lifecycle
    |   +-- Created
    |   +-- Running
    |   +-- Paused (SIGSTOP)
    |   +-- Stopped (SIGTERM / SIGKILL)
    |   +-- Deleted
    |
    +-- Dockerfile
    |   +-- What is a Dockerfile?
    |   +-- Key Instructions: FROM, WORKDIR, COPY, RUN, EXPOSE, CMD
    |   +-- Building an Image (docker build -t name .)
    |   +-- Layered, Immutable Images
    |
    +-- Docker Volumes
    |   +-- Why Volumes? (data persists beyond container lifecycle)
    |   +-- Named Volumes
    |   +-- Bind Mounts
    |   +-- Volumes vs Bind Mounts
    |
    +-- Docker Networking
    |   +-- Network Types
    |   |   +-- Bridge (default)
    |   |   +-- Host
    |   |   +-- Overlay
    |   |   +-- Macvlan
    |   |   +-- None
    |   +-- User-Defined Bridge Network
    |   +-- Container-to-Container Communication
    |   +-- Docker DNS (container name resolution)
    |   +-- Port Publishing vs Internal Networking
    |   +-- Commands: network create, connect, disconnect, inspect
    |
    +-- Docker Compose
    |   +-- What is Docker Compose?
    |   +-- YAML basics
    |   +-- docker-compose.yml structure
    |   |   +-- services (image, build, ports, volumes, networks, environment)
    |   |   +-- networks
    |   |   +-- volumes
    |   +-- Commands: up, up -d, down, ps
    |
    +-- Private Docker Repositories and Deployment
        +-- Why a Private Registry?
        +-- Building and Tagging for a Private Registry
        +-- Push and Pull Workflow
        +-- Deployment: Developer -> Build -> Private Registry -> Server
```

---

## DELIVERABLE 2 — TOPIC-WISE QUESTION TYPES TABLE

> **PYQ column:** "YES" = that question type has appeared in a previous year paper.
> Sources: `DevOps.PDF` (ESE Jul-Nov 2025, KJ Somaiya SVU) and `Sample.pdf` (official question bank).

| Topic | Short Note / Theory | Diagram | Write Code / Commands | Scenario-Based | PYQ Appeared |
|---|---|---|---|---|---|
| Cloud Service Models (IaaS/PaaS/SaaS) | YES | YES (layer diagram) | NO | YES | YES - Sample.pdf M3 Q1 |
| IaaS Characteristics | YES | NO | NO | YES | YES - Sample.pdf M3 Q1 |
| Server Setup on Linode (steps) | YES | NO | YES (SSH/apt commands) | YES | YES - Sample.pdf M3 Q1 |
| Linux User Configuration on Cloud | YES | NO | YES (useradd, passwd, chmod) | YES | YES - Sample.pdf M3 Q2 |
| What is an Artifact? (types, why needed) | YES | YES (CI/CD pipeline flow) | NO | YES | YES - Sample.pdf M2/M3 |
| Nexus - What and Why | YES | NO | NO | YES | YES - Sample.pdf M3 Q2 |
| Nexus Repository Types (Hosted/Proxy/Group) | YES | YES (flow diagram) | NO | YES | YES - Sample.pdf M3 Q2 |
| Nexus REST API | YES | NO | YES (curl examples) | YES | YES - Sample.pdf M3 Q3 |
| Blob Store | YES | YES (metadata->blob->disk) | NO | YES | YES - Sample.pdf M3 Q3 |
| Cleanup Policies | YES | NO | NO | YES | YES - Sample.pdf M3 Q3 |
| What is Docker / Container | YES | YES (container architecture) | NO | YES | YES - Sample.pdf M3 Q4 |
| Docker vs VMs | YES (comparison table) | NO | NO | NO | YES - Sample.pdf |
| Docker Architecture (Client-Daemon-Registry) | YES | YES (arch diagram) | NO | YES | YES - Sample.pdf M3 Q4, DevOps.PDF |
| Docker Engine components | YES | YES | NO | NO | YES - Sample.pdf M3 Q4 |
| Docker Commands (run, ps, stop, exec, etc.) | NO | NO | YES | NO | YES - Sample.pdf |
| Dockerfile (write + explain instructions) | YES | NO | YES (write Dockerfile) | YES | YES - Sample.pdf M3 Q5, DevOps.PDF |
| Docker Image (layers, immutability) | YES | YES (layer diagram) | NO | NO | YES - Sample.pdf |
| Docker Volumes (named vs bind mount) | YES | YES (bind mount diagram) | YES | YES | YES - Sample.pdf M3 Q6 |
| Docker Networking (types + user-defined) | YES | YES (network diagram) | YES | YES | YES - Sample.pdf M3 Q6 |
| Docker Compose (explain + write yml) | YES | NO | YES (write docker-compose.yml) | YES | YES - DevOps.PDF Q4(ii), Sample.pdf M3 Q7 |
| Container Lifecycle | YES | YES (state diagram) | YES | NO | NO |
| Port Mapping (-p vs -P) | YES | NO | YES | NO | NO |
| Private Docker Repository and Deployment | YES | YES (workflow) | YES | YES | YES - Sample.pdf M3 Q25 |
| Fault Tolerance in Docker | YES | NO | NO | NO | YES - DevOps.PDF Q5(vi) |

---

## DELIVERABLE 3 — TOPIC-BY-TOPIC DETAILED BREAKDOWN

---

### 3.1 Cloud Computing (IaaS)

#### What is Cloud Computing?

Cloud computing is the delivery of computing resources — servers, storage, databases, networking, software — over the internet on a pay-as-you-go basis. Instead of buying and maintaining physical hardware, you rent these resources from a cloud provider.

#### Cloud Service Models

There are three main service models. Think of them as layers — the higher you go, the less you manage yourself.

```
+-------------------------------+---------------------------+---------------------------+
|           IaaS                |           PaaS            |           SaaS            |
|  Infrastructure as a Service  | Platform as a Service     | Software as a Service     |
+-------------------------------+---------------------------+---------------------------+
| YOU MANAGE:                   | YOU MANAGE:               | YOU MANAGE:               |
|   OS, Runtime, Apps, Data     |   Apps, Data              |   Just your data & usage  |
|                               |                           |                           |
| PROVIDER MANAGES:             | PROVIDER MANAGES:         | PROVIDER MANAGES:         |
|   Servers, Storage,           |   + OS, Runtime           |   Everything              |
|   Networking, Virtualization  |                           |                           |
+-------------------------------+---------------------------+---------------------------+
| Linode, AWS EC2,              | Heroku, Google            | Gmail, Slack,             |
| DigitalOcean                  | App Engine, Render        | Salesforce                |
+-------------------------------+---------------------------+---------------------------+
```

**For exam - IaaS definition:**
> IaaS provides virtualized computing infrastructure (servers, storage, networking) over the internet. The provider manages the physical hardware and virtualization layer. The user manages the operating system, runtime, applications, and data.

#### IaaS Key Characteristics

| Characteristic | Explanation |
|---|---|
| On-Demand Compute | Spin up virtual machines in minutes, sized to workload |
| Elastic and Scalable | Add or remove servers as demand changes; pay only for what you use |
| Self-Managed Stack | User owns the OS, runtime, and application layer |
| Full Root Access | SSH in as root, install packages, configure firewall, manage users |

---

### Server Setup and Deployment on Cloud (Linode)

#### Steps to Provision a Cloud Server on Linode

1. Log in to the Linode Cloud Manager and click "Create Linode"
2. Choose a distribution image (e.g., Ubuntu 22.04 LTS)
3. Select a region closest to your users for lowest latency
4. Pick a plan (Shared CPU / Dedicated CPU) sized to the workload
5. Set a strong root password and add your SSH public key
6. Click "Create Linode" — the instance boots with a public IPv4 address

#### First SSH Login and Basic Hardening

```bash
# Connect to the server
ssh root@<server-ip>

# Update packages
apt update && apt upgrade -y

# Set the hostname
hostnamectl set-hostname app-server

# Enable the firewall
ufw allow OpenSSH
ufw allow 80,443/tcp
ufw enable
```

#### Deploying a Node.js Application on Linode

```bash
# Install Node.js
curl -fsSL https://deb.nodesource.com/setup_20.x | bash -
apt install -y nodejs

# Clone and install dependencies
git clone https://github.com/org/my-app.git
cd my-app && npm ci --omit=dev

# Run under a process manager so it survives reboots/crashes
npm install -g pm2
pm2 start server.js --name my-app
pm2 startup && pm2 save
```

**How to answer "steps to deploy on cloud" in exam (short note format):**
1. Provision a VM instance (choose OS, region, plan, add SSH key)
2. SSH into the server; update packages and harden firewall
3. Create a non-root user with sudo privileges
4. Install application runtime (Node.js, Java, Python, etc.)
5. Pull source code (git clone) or copy the artifact
6. Install dependencies and start the application under a process manager

---

### Linux User Configuration on Cloud

#### Why Not Use Root?
The root account has unlimited privileges. Operating as root means any mistake or malicious command runs without restriction. Best practice: create a dedicated user with sudo access.

#### User Management Commands

| Command | What It Does |
|---|---|
| `useradd -m -s /bin/bash dev` | Create user "dev" with home directory and bash shell |
| `passwd dev` | Set or reset the user's password |
| `usermod -aG sudo dev` | Add "dev" to the sudo group (admin privileges) |
| `groupadd deploy` | Create a new group named "deploy" |
| `usermod -aG deploy dev` | Add user to the deploy group |
| `deluser dev` | Remove a user account |
| `cat /etc/passwd` | List all user accounts |
| `id dev` | Show UID, GID, and group memberships |

#### SSH Key Authentication (Secure Login)

```bash
# On your LOCAL machine: generate a key pair
ssh-keygen -t ed25519 -C "dev@laptop"

# Copy the public key to the server
ssh-copy-id dev@<server-ip>

# On the server: harden sshd_config
# Edit /etc/ssh/sshd_config and set:
PermitRootLogin no
PasswordAuthentication no

# Restart SSH
systemctl restart sshd
```

**Why SSH keys over passwords?**
- Keys are cryptographically strong; passwords can be brute-forced
- `PermitRootLogin no` blocks automated attacks that target root
- Always test a new SSH session before closing your existing one

---

### Artifacts in DevOps

#### What is an Artifact?
An artifact is the **generated output of the software build process** that is ready for testing, deployment, or distribution. It is not source code — it is the compiled, packaged result.

| Technology | Artifact Type |
|---|---|
| Java | JAR (Java Archive) |
| Spring Boot | Executable JAR |
| Java Web App | WAR (Web Archive) |
| Python | Wheel (.whl) |
| React / Frontend | build/ folder (static files) |
| Android | APK |
| Docker | Docker Image |

#### Source Code vs Artifact

| Source Code | Artifact |
|---|---|
| Human-readable | Machine-ready / deployable |
| Stored in Git | Stored in Artifact Repository (Nexus) |
| Requires build tools to run | Can be directly deployed |
| Changes frequently | Versioned, immutable snapshot of a build |

#### Why Do We Need Artifact Repositories?

**Without artifacts:** Every deployment server builds independently, leading to:
- Different versions on different servers
- Compilation errors in production
- Dependency mismatches
- Slow and unreliable deployments

**With an artifact repository:**
- Faster deployment (pre-built)
- Same binary everywhere
- Easy rollback to previous version
- Version control for builds
- Reliable, repeatable deployments

---

### Nexus Artifact Repository

#### What is Sonatype Nexus?
Nexus Repository Manager (by Sonatype) is a self-hosted artifact repository that stores and manages binary artifacts. It supports multiple formats: Maven (JAR/WAR), npm, Docker, PyPI, NuGet, and raw files — all in one place.

It acts as the **central source of truth** for build artifacts in a DevOps pipeline:
- CI pipelines **publish** artifacts to Nexus
- Deployments and other builds **pull** from Nexus

#### Nexus Setup via Docker

```bash
# Create a persistent volume
docker volume create nexus-data

# Run Nexus
docker run -d -p 8081:8081 \
    -v nexus-data:/nexus-data \
    --name nexus \
    sonatype/nexus3

# Get the generated admin password
docker exec nexus cat /nexus-data/admin.password
```

**First-Login Checklist:**
1. Open `http://<server-ip>:8081` and sign in as "admin"
2. Complete the setup wizard and set a new admin password
3. Disable anonymous access unless serving public artifacts
4. Create additional users/roles — do not share the admin login

#### Nexus Repository Types

Every Nexus repository is one of three types:

```
+------------------+--------------------------------------------------+-----------------------------+
| Type             | What it does                                     | Example                     |
+------------------+--------------------------------------------------+-----------------------------+
| Hosted           | Stores artifacts YOU publish (your own builds)   | my-app-releases             |
|                  |                                                  | my-app-snapshots            |
+------------------+--------------------------------------------------+-----------------------------+
| Proxy            | Caches artifacts from a REMOTE repository        | npm-proxy                   |
|                  | (e.g., npmjs.org, Maven Central)                | maven-central-proxy         |
+------------------+--------------------------------------------------+-----------------------------+
| Group            | Combines multiple repos behind ONE URL           | npm-group                   |
|                  | (merges Hosted + Proxy for clients)              | (= hosted + proxy)          |
+------------------+--------------------------------------------------+-----------------------------+
```

**Typical workflow:**
- Developers/CI **publish** to a **Hosted** repo
- Everyone **consumes** through a **Group** repo (which merges Hosted + Proxy under one endpoint)

**How to draw a diagram for this in exam:**

```
[CI Build] --publish--> [Hosted Repo]
                                     \
                                      +--[Group Repo]---> [Developer / Deploy Server]
                                     /
[Maven Central] --cache--> [Proxy Repo]
```

#### Nexus REST API

Nexus exposes a REST API so CI/CD pipelines can automate artifact management without using the web UI.

```bash
# Upload a raw artifact to a hosted repository
curl -u admin:password --upload-file app-1.2.0.zip \
    http://nexus:8081/repository/my-app-releases/app-1.2.0.zip

# Download an artifact
curl -u admin:password -O \
    http://nexus:8081/repository/my-app-releases/app-1.2.0.zip

# Search for components
curl -u admin:password \
    "http://nexus:8081/service/rest/v1/search?repository=my-app-releases"

# Delete a component by ID
curl -u admin:password -X DELETE \
    http://nexus:8081/service/rest/v1/components/<component-id>
```

**Use of REST API in exam context:**
- Automate uploads from Jenkins pipelines after a successful build
- Automate downloads during deployment scripts
- Query for artifact metadata without logging into the UI

---

### Blob Store and Cleanup Policies

#### What is a Blob Store?

A **blob store** is where Nexus physically writes artifact bytes to disk (or cloud storage like S3). Repositories only track **metadata** — the blob store holds the **actual file content**.

```
[Repository (Hosted/Proxy/Group)]
         |
         | tracks metadata only
         v
  [Blob Store (File System or S3)]
         |
         | holds the actual bytes
         v
  [Disk / S3 Bucket]
```

**Key points:**
- Multiple repositories can share one blob store, or each can have its own
- File-based blob stores are the simplest; S3-backed blob stores scale further
- Deleting a **component record** (metadata) does not immediately free disk space — the blob must be reclaimed separately

#### Cleanup Policies

Artifact repositories grow indefinitely unless old/unused components are removed. Cleanup policies automate this pruning.

| Criteria | What It Targets |
|---|---|
| Published before | Remove components older than N days since publish date |
| Last downloaded before | Remove components not pulled/used in the last N days |
| Last blob updated | Remove components whose blob has not changed recently |
| Regex on version/name | Target only components matching a pattern (e.g., `*-SNAPSHOT`) |

**Important two-step process:**
1. A cleanup policy only **marks** matching components for deletion on its schedule
2. Disk space is actually freed only after running the **Compact Blob Store** task

> Policies alone do not shrink disk usage — you must run Compact Blob Store afterward.

---

## 3.2 Containers and Docker

---

### What is a Container?

A container is a **lightweight, isolated unit** that packages an application together with all its code, runtime, libraries, dependencies, and configuration.

- It shares the **host operating system kernel** (unlike a VM which has its own OS)
- It is **portable** — a container that works on a developer's laptop will work identically on a server
- Once a container is destroyed, data stored only inside it is lost (use volumes to persist data)

**The problem Docker solves:**
> Developer builds an app. It works on their machine. The tester runs it on their machine — it fails. The developer says "But it is working on my machine." This environment mismatch problem is exactly what containers solve. The developer packages the app into a Docker image with all its dependencies. The tester runs that exact image and gets identical behavior.

---

### Docker vs Virtual Machines

```
+-------------------------------------------+------------------------------------------+
|         Docker Containers                 |         Virtual Machines (VMs)           |
+-------------------------------------------+------------------------------------------+
| Lightweight: shares host OS kernel        | Heavy: each VM has its own full OS       |
| Low impact on OS; very fast startup       | High impact on OS; slower startup        |
| Low disk space usage                      | High disk space usage                    |
| Sharing, re-building, distributing easy   | Sharing and distribution is challenging  |
| Encapsulates the APP and its dependencies | Encapsulates the whole machine           |
| Less isolation (shares kernel)            | Strong isolation (separate kernel)       |
+-------------------------------------------+------------------------------------------+
```

**Architecture comparison:**

```
VIRTUAL MACHINE                          DOCKER CONTAINERS

+----------+ +----------+                +----------+ +----------+ +----------+
|  App 1   | |  App 2   |                |  App 1   | |  App 2   | |  App 3   |
+----------+ +----------+                | + Libs   | | + Libs   | | + Libs   |
| Guest OS | | Guest OS |                +----------+ +----------+ +----------+
+----------+ +----------+                +--------------------------------------+
+--------------------------------------+ |           Docker Engine              |
|         Hypervisor / VMM             | +--------------------------------------+
+--------------------------------------+ |            Operating System          |
|           Host OS                    | +--------------------------------------+
+--------------------------------------+ |              Hardware                |
|              Hardware                | +--------------------------------------+
+--------------------------------------+
```

---

### Docker Architecture

Docker follows a **Client-Server** architecture with five major components.

```
+-----------+          REST API         +--------------------+
|  Docker   |  ----------------------> |   Docker Daemon    |
|  Client   |                          |   (dockerd)        |
|  (CLI)    |  <---------------------- |                    |
+-----------+   responses/events       +--------------------+
                                              |
                              +---------------+--------------+
                              |               |              |
                         +--------+     +----------+    +---------+
                         | Images |     |Containers|    |Volumes/ |
                         |        |     |          |    |Networks |
                         +--------+     +----------+    +---------+
                              |
                    +---------+----------+
                    |   Docker Registry  |
                    | (Docker Hub or     |
                    |  Private Registry) |
                    +--------------------+
```

#### Component Descriptions

**Docker Client:**
- The interface the user interacts with
- Issues commands via CLI (`docker run`, `docker build`, etc.)
- Communicates with Docker Daemon using commands and REST APIs
- Can communicate with a remote daemon (not just local)

**Docker Daemon (dockerd):**
- Runs on the host operating system
- Listens for Docker API requests
- Manages Docker objects: images, containers, networks, volumes
- Responsible for building, running, and distributing containers
- Can communicate with other daemons (for Docker Swarm)

**Docker Host:**
- The machine where Docker is installed and running
- Commands from the client are sent to the Docker Daemon running on the host

**Docker Registry:**
- A central repository for storing and distributing Docker images
- **Docker Hub** is the default public registry
- Private registries can be self-hosted (e.g., using Nexus, AWS ECR, GitLab Registry)

**Docker Objects:**
- Images, Containers, Volumes, Networks, Plugins
- These are what you interact with while using Docker

**Docker Engine:**
Docker Engine is the core of Docker. It is a client-server application with:
- A server: the long-running daemon process `dockerd`
- REST APIs: interfaces for programs to communicate with the daemon
- CLI client: the `docker` command

---

### Docker Commands

#### Image Commands

```bash
docker pull nginx:latest          # Download image from registry
docker images                     # List all local images
docker build -t my-image:1.0 .    # Build image from Dockerfile in current dir
docker rmi my-image:1.0           # Remove a local image
docker tag my-image:1.0 registry/my-image:1.0   # Tag image for a registry
docker push registry/my-image:1.0               # Push image to registry
```

#### Container Commands

```bash
docker run nginx                        # Create and start a container
docker run -d nginx                     # Run in detached (background) mode
docker run -it ubuntu bash              # Run interactively with terminal
docker run -p 8080:80 nginx             # Map host port 8080 to container port 80
docker run --name myapp nginx           # Give the container a name
docker ps                               # List running containers
docker ps -a                            # List all containers (including stopped)
docker stop myapp                       # Gracefully stop a container
docker start myapp                      # Start a stopped container
docker rm myapp                         # Remove a stopped container
docker rm -f myapp                      # Force remove a running container
docker exec -it myapp bash              # Run a command inside a running container
docker logs myapp                       # View container logs
docker inspect myapp                    # Detailed JSON info about a container
```

#### Port Mapping: -p vs -P

| Flag | Behaviour |
|---|---|
| `-p 8080:80` | Map host port 8080 to container port 80 (explicit) |
| `-P` (capital P) | Automatically map all EXPOSED ports to random host ports |

```bash
docker run --name web1 -d -p 8080:80 nginx    # Access at localhost:8080
docker run --name web2 -d -P nginx             # Random port assigned by Docker
docker ps                                       # Check which port was assigned
```

#### Foreground vs Detached Mode

| Mode | Flag | Use Case |
|---|---|---|
| Foreground (Interactive) | `docker run <image>` | Debugging, short-lived tasks, interactive commands |
| Detached (Background) | `docker run -d <image>` | Web servers, databases, long-running services |

```bash
# Attach to a detached container
docker attach <container-id>

# Run a shell in a running container
docker exec -it <container-id> /bin/bash
```

---

### Container Lifecycle

```
               docker create
[Image] -----------------------> [CREATED]
                                      |
                                      | docker start / docker run
                                      v
                                  [RUNNING] <----------+
                                  /       \            |
                     docker pause  \       / docker unpause
                                    v     ^
                                  [PAUSED]
                                      |
                            docker stop (SIGTERM -> SIGKILL)
                                      |
                                      v
                                  [STOPPED]
                                      |
                            docker rm / docker kill (SIGKILL)
                                      |
                                      v
                                  [DELETED]
```

| State | Description | Command |
|---|---|---|
| Created | Container created from image, not yet started | `docker create` |
| Running | Container executing its processes | `docker run` / `docker start` |
| Paused | Processes suspended (SIGSTOP signal) | `docker pause` |
| Unpaused | Processes resumed (SIGCONT signal) | `docker unpause` |
| Stopped | Main process gracefully shut down (SIGTERM, then SIGKILL) | `docker stop` |
| Deleted | Container removed from system | `docker rm` / `docker kill` |

---

### Dockerfile

#### What is a Dockerfile?
A Dockerfile is a plain text file containing a series of instructions that Docker uses to automatically build a Docker image. It defines the base image, copies files, installs dependencies, configures environment, and specifies how the container should start.

#### Key Dockerfile Instructions

| Instruction | Purpose |
|---|---|
| `FROM` | Sets the base image (starting point). Every Dockerfile must begin with FROM. |
| `WORKDIR` | Sets the working directory inside the container for subsequent instructions. |
| `COPY` | Copies files/directories from the build context (host) into the container. |
| `RUN` | Executes a shell command during the image build (e.g., install packages). |
| `EXPOSE` | Documents which port the container listens on at runtime. Does NOT publish the port. |
| `CMD` | Specifies the default command to run when the container starts. |
| `ENV` | Sets environment variables inside the container. |
| `ADD` | Like COPY, but also handles URLs and auto-extracts tar archives. |

#### Sample Dockerfile (Node.js Application)

```dockerfile
# Set the base image to the official Node.js 14 image
FROM node:14

# Create a working directory for the application
WORKDIR /app

# Copy the package.json and package-lock.json files to the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose port 3000 so it can be accessed from outside the container
EXPOSE 3000

# Start the Node.js application
CMD ["npm", "start"]
```

#### Build and Run the Image

```bash
# Build the image and tag it as "my-image"
docker build -t my-image .

# Run a container from the image
docker run -p 3000:3000 my-image
```

#### Dockerfile -> Image -> Container Relationship

```
[Dockerfile]  --docker build-->  [Image]  --docker run-->  [Container]
(Instructions)                   (Blueprint,               (Running instance
                                  read-only,                of the image)
                                  layered)
```

One image can create **multiple containers**. The image itself is **immutable** — you cannot modify it after creation.

#### Docker Image Layers

- Images are composed of **layers**. Each instruction in the Dockerfile creates a new read-only layer.
- Layers are cached: if a layer has not changed, Docker reuses the cached version, making builds faster.
- Containers add a thin **writable layer** on top — all changes made in a running container go here.

---

### Docker Volumes

#### Why Volumes?

Containers are ephemeral — when a container is deleted, all data stored inside its writable layer is lost. Docker Volumes provide a way to **persist data** independently of the container lifecycle.

#### Types of Volume Mounting

**Named Volume:**
- Managed entirely by Docker
- Stored in Docker's own area on the host filesystem (`/var/lib/docker/volumes/`)
- Preferred for production

**Bind Mount:**
- Maps a specific directory/file on the host to a path inside the container
- Changes on either side are reflected immediately
- Useful for development (share source code with container)

```
Host Machine                    Container
+--------------+                +------------------+
| servers.txt  |<-- bind mount->| /data/servers.txt|
+--------------+   (shared)     +------------------+
```

#### Volume Commands

```bash
# Create a named volume
docker volume create mydata

# Run a container with a named volume
docker run -d -v mydata:/var/lib/mysql mysql

# Run a container with a bind mount
docker run -d -v /host/path:/container/path nginx

# List volumes
docker volume ls

# Inspect a volume
docker volume inspect mydata
```

#### Volumes vs Bind Mounts

| Named Volume | Bind Mount |
|---|---|
| Docker manages the location | You specify the exact host path |
| Portable, works regardless of host directory structure | Depends on the host directory layout |
| Can use different storage drivers (remote, cloud) | Tied to the local filesystem |
| Preferred for databases and persistent app data | Good for development and sharing config files |

---

### Docker Networking

#### Why Networking?

Containers are isolated by default. Docker networking enables:
- Containers to communicate with each other
- Containers to communicate with external services
- Isolation of container groups from each other

#### Docker Network Types

| Type | Description | Use Case |
|---|---|---|
| **Bridge** | Default. Creates a private network on the host. Containers on the same bridge can communicate by name or alias. | Single-host applications |
| **Host** | Container uses the host's network stack directly — no isolation. | High-performance scenarios where port mapping overhead is unacceptable |
| **Overlay** | Connects containers across multiple hosts using a distributed store (Consul/etcd). | Docker Swarm, multi-host setups |
| **Macvlan** | Assigns a MAC address to each container; connects to the host's physical network. | Containers that need to appear as physical devices on the network |
| **None** | Disables all networking. Only loopback interface available. | Maximum isolation |

#### User-Defined Bridge Network

The **default bridge network** does not support automatic DNS resolution by container name. A **user-defined bridge network** does — this is the recommended way to connect containers.

```bash
# Create a custom network
docker network create my-network

# Verify
docker network ls

# Inspect the network (shows subnet, gateway, connected containers)
docker network inspect my-network
```

#### Step-by-Step: Two Containers on the Same Network

```bash
# Step 1: Create the network
docker network create app-net

# Step 2: Start the database container
docker run -d \
  --name mysql-db \
  --network app-net \
  -e MYSQL_ROOT_PASSWORD=Root@123 \
  -e MYSQL_DATABASE=demo \
  mysql:8

# Step 3: Start the web container
docker run -d \
  --name web \
  --network app-net \
  -p 8080:80 \
  nginx

# Step 4: Test DNS resolution from web to mysql-db
docker exec -it web sh
# Inside the container:
getent hosts mysql-db    # should resolve mysql-db to its IP
exit
```

**How it works:**
- Docker provides an embedded **DNS server** for user-defined networks
- Containers can reach each other using their **container names** (e.g., `mysql-db`) instead of IP addresses
- The `mysql-db` port 3306 does NOT need to be published to the host for internal communication
- Only the nginx port 80 is published (as 8080 on the host) so external users can access it

```
[Browser] --port 8080--> [Host] --port 80--> [web (nginx)] --port 3306--> [mysql-db]
                                              ^                           ^
                                              |        app-net            |
                                              +---------------------------+
                                                   (Docker DNS resolves names)
```

#### Port Publishing vs Container-to-Container Networking

| Port Publishing (-p) | Container Networking |
|---|---|
| Makes a container port accessible from OUTSIDE the Docker network | Containers on the same user-defined network communicate directly |
| `docker run -p 8080:80 nginx` exposes nginx to the host | web container connects to mysql-db:3306 internally without -p |
| For external traffic (browsers, clients) | For internal service-to-service communication |

#### Other Network Commands

```bash
# Connect a running container to an additional network
docker network connect my-network mycontainer

# Disconnect a container from a network
docker network disconnect my-network mycontainer

# Remove a network (all containers using it must be removed first)
docker network rm my-network
```

---

### Docker Compose

#### What is Docker Compose?

Docker Compose is a tool for defining and running **multi-container Docker applications**. Instead of running multiple `docker run` commands manually, you describe all the services, networks, and volumes in a single **YAML file** (`docker-compose.yml`) and bring everything up with one command.

**Problem it solves:**
Most real applications have multiple services — a web server, a database, a cache. Each needs to be configured with the right image, ports, environment variables, volumes, and network connections. Doing this manually is error-prone and hard to repeat. Compose encapsulates all these settings as code.

#### YAML Basics

YAML (YAML Ain't Markup Language) is a human-readable data serialization format used for configuration files. Key rules:
- Indentation (spaces, not tabs) defines hierarchy
- Colons separate keys from values
- Dashes (`-`) indicate list items

```yaml
# Example YAML structure
name: my-app
version: "1.0"
services:
  - web
  - database
```

#### docker-compose.yml Structure

```yaml
services:
  web:
    image: nginx
    ports:
      - "8080:80"
    networks:
      - app-net
    depends_on:
      - db

  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: Root@123
      MYSQL_DATABASE: demo
    volumes:
      - db-data:/var/lib/mysql
    networks:
      - app-net

  redis:
    image: redis:latest
    networks:
      - app-net

networks:
  app-net:

volumes:
  db-data:
```

**Key sections explained:**

| Section | Purpose |
|---|---|
| `services` | Defines each container as a "service" with its configuration |
| `image` | Docker image to use for the service |
| `build` | Path to a Dockerfile to build the image from (instead of using a pre-built image) |
| `ports` | Port mappings (host:container) |
| `environment` | Environment variables passed to the container |
| `volumes` | Volume mounts for the service |
| `networks` | Which networks the service connects to |
| `depends_on` | Ensures one service starts after another |
| `networks` (top-level) | Defines the named networks used |
| `volumes` (top-level) | Defines the named volumes used |

#### Docker Compose Commands

```bash
# Start all services (foreground)
docker compose up

# Start all services in the background (detached)
docker compose up -d

# Show running services
docker compose ps

# View logs for all services
docker compose logs

# Stop and remove all containers, networks (but NOT volumes)
docker compose down

# Stop and remove everything including named volumes
docker compose down -v

# Check version
docker compose version
```

#### Benefits of Docker Compose

- Fast and easy configuration through YAML
- Single-host deployment with one command
- Automatically creates a shared network for all services
- Automatically manages volume reattachment on restart
- Reproducible: the same YAML file produces the same environment every time

---

### Private Docker Repositories and Deployment

#### Why a Private Registry?

Docker Hub is public — any image you push is visible to everyone. For proprietary/internal applications, you need a **private registry** where only authorized users can push or pull images.

**Use cases:**
- Internal company applications (banking, healthcare data)
- Images containing proprietary logic or trade secrets
- CI/CD pipelines in air-gapped environments

#### Options for Private Registries

- **Docker Hub private repos** (limited on free plan) [SG]
- **AWS ECR** (Elastic Container Registry) [SG]
- **GitLab Container Registry** [SG]
- **Sonatype Nexus** (self-hosted, covered in this module)
- **Docker Registry** (official open-source, self-hosted) [SG]

#### Build, Tag, Push, Pull Workflow

```bash
# 1. Build the image
docker build -t my-banking-app:1.0 .

# 2. Tag the image for your private registry
docker tag my-banking-app:1.0 registry.company.com:5000/my-banking-app:1.0

# 3. Authenticate with the private registry
docker login registry.company.com:5000

# 4. Push to the private registry
docker push registry.company.com:5000/my-banking-app:1.0

# On the deployment server:
# 5. Authenticate
docker login registry.company.com:5000

# 6. Pull the image
docker pull registry.company.com:5000/my-banking-app:1.0

# 7. Run the container
docker run -d -p 80:8080 registry.company.com:5000/my-banking-app:1.0
```

#### Deployment Workflow Diagram

```
[Developer Machine]
       |
   docker build
       |
   docker tag
       |
   docker push
       |
       v
[Private Registry] (Nexus / ECR / Docker Registry)
       |
   docker pull (from deployment server)
       |
       v
[Cloud Linux Server (Linode)]
       |
   docker run
       |
       v
[Running Container]
```

#### Setting Up Nexus as a Private Docker Registry [SG]

Nexus can host a private Docker registry as a "Docker (hosted)" repository:
- Create a Docker Hosted repository in Nexus (assign a port, e.g., 5000)
- Configure Docker daemon to allow the insecure registry (if not using HTTPS)
- Use `docker login nexus-server:5000` to authenticate
- Push and pull images as you would with any other registry

---

### Fault Tolerance in Docker [SG - partially, from DevOps.PDF Q5vi]

> Note: The ESE PYQ (DevOps.PDF) asked about "Fault tolerance in Dockers & Kubernetes" (5 marks). Docker itself has basic fault tolerance features; Kubernetes extends this further. Only Docker-side content is covered here.

**Fault tolerance** means the system continues to operate (or fails gracefully) when a component fails.

**Docker fault tolerance mechanisms:**

| Mechanism | How it helps |
|---|---|
| Restart Policies | `--restart always` / `--restart on-failure` automatically restarts crashed containers |
| Health Checks | `HEALTHCHECK` instruction in Dockerfile; Docker monitors and can restart unhealthy containers |
| Named Volumes | Data persists even if the container crashes and is recreated |
| Docker Compose `restart: always` | Ensures services auto-restart on failure |
| Multiple Replicas (Swarm) | Docker Swarm runs multiple instances; if one fails, others handle traffic |

```dockerfile
# Dockerfile with healthcheck [SG]
HEALTHCHECK --interval=30s --timeout=3s \
  CMD curl -f http://localhost:3000/health || exit 1
```

```yaml
# docker-compose.yml with restart policy
services:
  web:
    image: my-app
    restart: always    # restart on any failure
```

---

## DELIVERABLE 4 — PYQ SOLUTIONS (Module 3 Only)

> Only Module 3 questions from the official PYQs are solved here.
> Sources: `DevOps.PDF` (ESE Jul-Nov 2025, KJ Somaiya) and `Sample.pdf` (official question bank).

---

### FROM DevOps.PDF (ESE Jul-Nov 2025) — Module 3 Relevant Questions

---

#### Q4(ii) — 10 Marks
**"Explain how Docker Compose simplifies multi-container deployment. Give an example of docker-compose.yml file."**

**Answer:**

**What is Docker Compose?**

Docker Compose is a tool for defining and managing multi-container Docker applications. It uses a YAML configuration file (`docker-compose.yml`) to describe all services, their images, ports, volumes, environment variables, and network connections. With a single command (`docker compose up`), all defined services are started together in the correct order.

**How It Simplifies Multi-Container Deployment:**

Without Docker Compose, deploying an application with a web server, API, and database requires:
- Running `docker network create` manually
- Running separate `docker run` commands for each container with the right flags
- Remembering the order of startup, environment variables, volume mounts, and port mappings
- Re-running all these manually every time the environment is recreated

With Docker Compose:
- All configuration is declared once in a single YAML file
- One command (`docker compose up -d`) starts everything
- Networks and volumes are automatically created
- Environment is fully reproducible from the YAML file

**Example docker-compose.yml (Web App + MySQL Database):**

```yaml
services:
  web:
    image: nginx
    ports:
      - "8080:80"
    networks:
      - app-net
    depends_on:
      - app

  app:
    build: ./app
    environment:
      DB_HOST: db
      DB_PORT: 3306
      DB_NAME: demo
      DB_USER: root
      DB_PASSWORD: Root@123
    ports:
      - "3000:3000"
    volumes:
      - ./app:/usr/src/app
    networks:
      - app-net
    depends_on:
      - db

  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: Root@123
      MYSQL_DATABASE: demo
    volumes:
      - db-data:/var/lib/mysql
    networks:
      - app-net

networks:
  app-net:

volumes:
  db-data:
```

**Key sections explained:**
- `services` — each container is a service (web, app, db)
- `image` — pre-built image to use; `build` — build from a Dockerfile
- `ports` — `"8080:80"` maps host port 8080 to container port 80
- `environment` — environment variables injected into the container
- `volumes` — `db-data:/var/lib/mysql` mounts a named volume to persist MySQL data
- `networks` — all three services share `app-net`, so they can communicate by service name
- `depends_on` — ensures `db` starts before `app`, and `app` before `web`

**Commands:**

```bash
docker compose up -d    # Start all services in background
docker compose ps       # Check status of services
docker compose down     # Stop and remove all containers and networks
```

**Benefits:**
- Single command to start/stop entire stack
- Automatically creates a shared network (DNS by service name)
- Configuration is version-controlled alongside code
- Easy rollback and reproducibility

---

#### Q5(vi) — 5 Marks
**"Fault tolerance in Dockers & Kubernetes"**

**Answer (Docker portion — 5 marks):**

**Fault Tolerance** is the ability of a system to continue operating correctly in the event of a component failure.

**Docker Fault Tolerance Mechanisms:**

1. **Restart Policies:**
   Docker can automatically restart a container if it exits or crashes.
   ```bash
   docker run --restart always my-app        # restart no matter what
   docker run --restart on-failure my-app    # restart only on non-zero exit
   docker run --restart unless-stopped my-app
   ```
   In `docker-compose.yml`:
   ```yaml
   services:
     web:
       image: my-app
       restart: always
   ```

2. **Health Checks:**
   Dockerfile can define a health check command. Docker periodically runs it; if the container becomes "unhealthy," it can be restarted.
   ```dockerfile
   HEALTHCHECK --interval=30s --timeout=5s \
     CMD curl -f http://localhost:3000/ || exit 1
   ```

3. **Named Volumes for Data Persistence:**
   If a container crashes and is restarted, data in a named volume is not lost.
   ```bash
   docker run -v mydata:/var/lib/mysql mysql
   ```

4. **Docker Compose `restart: always`:**
   All services in a Compose file can be set to restart automatically on failure.

**Kubernetes Fault Tolerance (brief):** [SG - K8s is beyond this module's scope but mentioned for completeness]
Kubernetes extends fault tolerance with Deployments (maintain desired replica count), ReplicaSets (auto-replace failed pods), and liveness/readiness probes.

---

### FROM Sample.pdf (Official Question Bank) — Module 3 Questions

---

#### Q1 (M3) — Cloud Compute (IaaS)
**"Explain the IaaS cloud delivery model. List the step-by-step procedure to provision and configure a secure Linux virtual server on a cloud provider (e.g., Linode/AWS)."**

**Answer:**

**IaaS — Infrastructure as a Service:**

IaaS is a cloud delivery model where the cloud provider manages the physical hardware, networking, storage, and virtualization layer. The user (organization) manages everything above: the operating system, runtime, middleware, applications, and data.

Characteristics:
- On-demand compute resources provisioned in minutes
- Pay-per-use billing (no capital expenditure on hardware)
- Elastic — resources can be scaled up or down
- Full root/admin access to the provisioned virtual machine
- Examples: Linode, AWS EC2, DigitalOcean

**Steps to Provision and Configure a Secure Linux Server on Linode:**

1. **Create Account and Log In**
   Log in to the Linode Cloud Manager at `cloud.linode.com`

2. **Click "Create Linode" (Provision a VM):**
   - Choose distribution: Ubuntu 22.04 LTS
   - Choose region: closest to users for lowest latency
   - Choose plan: Shared CPU (Nanode) for a basic app
   - Set root password and upload your SSH public key

3. **First SSH Connection:**
   ```bash
   ssh root@<server-ip>
   ```

4. **Update Packages:**
   ```bash
   apt update && apt upgrade -y
   ```

5. **Set Hostname:**
   ```bash
   hostnamectl set-hostname app-server
   ```

6. **Configure Firewall:**
   ```bash
   ufw allow OpenSSH
   ufw allow 80,443/tcp
   ufw enable
   ```

7. **Create a Non-Root User:**
   ```bash
   useradd -m -s /bin/bash devuser
   passwd devuser
   usermod -aG sudo devuser
   ```

8. **Set Up SSH Key Authentication for the New User:**
   ```bash
   # From local machine
   ssh-copy-id devuser@<server-ip>
   ```

9. **Harden SSH Config (`/etc/ssh/sshd_config`):**
   ```
   PermitRootLogin no
   PasswordAuthentication no
   ```
   ```bash
   systemctl restart sshd
   ```

10. **Verify Login as New User:**
    ```bash
    ssh devuser@<server-ip>
    ```

---

#### Q2 (M3) — Artifact Management with Nexus
**"What is Sonatype Nexus, and why is an artifact repository needed in DevOps? Describe Hosted, Proxy, and Group repository types in Nexus."**

**Answer:**

**What is Sonatype Nexus?**

Sonatype Nexus Repository Manager is a self-hosted artifact repository manager. It stores, organizes, and distributes the binary outputs of software builds (artifacts) such as JAR files, Docker images, npm packages, Python wheels, and raw zip files. It supports multiple formats from a single server.

**Why is an Artifact Repository Needed in DevOps?**

In a DevOps pipeline, source code is compiled and packaged into a deployable artifact. This artifact needs to be:
- **Versioned** — each build produces a uniquely identified artifact
- **Stored centrally** — not on developer laptops or shared via email
- **Accessible reliably** — CI builds publish; deployment servers pull
- **Reproducible** — the same artifact can be redeployed at any time

Without a repository: developers share JARs via email, builds happen on every deployment server independently (causing version mismatches), and rollback is nearly impossible.

With Nexus: CI publishes once, all servers pull the same tested binary.

**Nexus Repository Types:**

**1. Hosted Repository:**
- Stores artifacts published by your own builds
- Your CI pipeline pushes artifacts here after a successful build
- Examples: `my-app-releases`, `my-app-snapshots`

**2. Proxy Repository:**
- Acts as a caching proxy for a remote public repository (Maven Central, npmjs.org)
- When a build requests a dependency, Nexus fetches it once from the remote source and caches it locally
- Subsequent requests are served from the local cache (faster, works offline)
- Examples: `maven-central-proxy`, `npm-proxy`

**3. Group Repository:**
- Combines one or more Hosted and Proxy repositories behind a single URL
- Build tools and developers use one URL; Nexus resolves which repo has the artifact
- Example: `npm-group` = `npm-hosted` + `npm-proxy`

```
[Your CI Build]  --publish-->  [Hosted Repo]
                                            \
                                             +--[Group Repo URL]---> [All consumers]
                                            /
[npmjs.org]  --cached in-->  [Proxy Repo]
```

---

#### Q3 (M3) — Nexus Maintenance & APIs
**"Explain Blob Stores and Cleanup Policies in Nexus. How can REST APIs be used to manage Nexus artifacts programmatically?"**

**Answer:**

**Blob Store:**

A Blob Store is the physical storage backend for Nexus. While repositories track metadata (component names, versions, checksums), the actual file bytes are stored in a Blob Store.

- Nexus supports **file-based** blob stores (local filesystem) and **S3-backed** blob stores (AWS S3 for scalability)
- Multiple repositories can share one blob store, or each can have its own
- Deleting a component from the Nexus UI removes the metadata record; the blob bytes are reclaimed only when the **Compact Blob Store** task runs

```
Repository  -->  Blob Store  -->  Disk/S3
(metadata)       (actual bytes)
```

**Cleanup Policies:**

As CI runs continuously, old artifact versions accumulate and consume disk space. Cleanup policies define rules to automatically identify and remove stale components.

Criteria available:
- **Published before N days** — remove artifacts older than N days
- **Last downloaded before N days** — remove artifacts unused for N days
- **Regex on version** — remove only artifacts matching a pattern (e.g., `*-SNAPSHOT`)

**Important:** Cleanup policies only **mark** components for deletion. Actual disk space is freed only after the **Compact Blob Store** task is run separately.

**REST API Usage:**

```bash
# Upload an artifact
curl -u admin:password --upload-file app-1.2.0.jar \
    http://nexus:8081/repository/my-app-releases/com/company/app/1.2.0/app-1.2.0.jar

# Download an artifact
curl -u admin:password -O \
    http://nexus:8081/repository/my-app-releases/com/company/app/1.2.0/app-1.2.0.jar

# Search for components
curl -u admin:password \
    "http://nexus:8081/service/rest/v1/search?repository=my-app-releases&name=app"

# Delete a component by its ID
curl -u admin:password -X DELETE \
    http://nexus:8081/service/rest/v1/components/<component-id>
```

**Why use the REST API?**
- CI pipelines (Jenkins, GitLab CI) automate artifact upload after a successful build
- Deployment scripts automate artifact download to the target server
- No manual UI interaction required — fully scriptable

---

#### Q4 (M3) — Docker Architecture
**"Explain the client-server architecture of Docker. Describe the roles of Docker Client, Docker Daemon, Docker Images, Docker Containers, and Docker Registry."**

**Answer:**

Docker follows a **client-server architecture**.

```
[Docker Client]  ---REST API--->  [Docker Daemon (dockerd)]
                <---responses----         |
                                          |
                          +--------------+-----------+
                          |              |           |
                       [Images]    [Containers]  [Volumes/Networks]
                          |
                  [Docker Registry]
                  (Docker Hub / Private)
```

**Docker Client:**
- The primary way users interact with Docker
- Provides the CLI (`docker` command)
- Sends API requests to the Docker Daemon
- Can connect to a local or remote daemon

**Docker Daemon (dockerd):**
- Runs as a background service on the host OS
- Listens for Docker API requests
- Manages all Docker objects: images, containers, networks, volumes
- Handles building, running, and distributing containers
- Can communicate with other daemons (for Swarm)

**Docker Images:**
- Read-only templates used to create containers
- Built from a Dockerfile
- Composed of layered filesystem snapshots
- Stored in a registry and pulled to the host when needed
- Immutable — once created, cannot be modified (create a new image instead)

**Docker Containers:**
- Running instances of a Docker image
- Isolated processes on the host OS (own filesystem, network, process space)
- Multiple containers can be created from the same image
- Add a thin writable layer on top of the image layers

**Docker Registry:**
- A central storage and distribution system for Docker images
- **Docker Hub** is the default public registry
- Private registries (Nexus, AWS ECR) restrict access to authorized users
- `docker push` uploads an image; `docker pull` downloads it

---

#### Q5 (M3) — Dockerfile Instructions
**"Write a sample Dockerfile for a simple web application. Explain FROM, WORKDIR, COPY, RUN, EXPOSE, and CMD."**

**Answer:**

```dockerfile
# Use the official Node.js 14 image as the base
FROM node:14

# Set the working directory inside the container
WORKDIR /app

# Copy package files first (for better layer caching)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application source code
COPY . .

# Expose the port the app listens on
EXPOSE 3000

# Define the command to run the application
CMD ["node", "server.js"]
```

**Explanation of each instruction:**

| Instruction | Explanation |
|---|---|
| `FROM node:14` | Every Dockerfile starts with FROM. Sets the base image. Here, we start from the official Node.js 14 image which already has Node and npm installed. |
| `WORKDIR /app` | Sets the working directory inside the container. All subsequent COPY, RUN, CMD instructions operate relative to /app. Creates the directory if it does not exist. |
| `COPY package*.json ./` | Copies package.json and package-lock.json from the build context (host machine) into the container's working directory. Done separately to leverage Docker's layer caching — if package.json hasn't changed, Docker reuses the cached npm install layer. |
| `RUN npm install` | Executes a command during the build phase. Installs all Node.js dependencies. RUN creates a new image layer with the result. |
| `COPY . .` | Copies all remaining source files into the container. Done after npm install to avoid reinstalling dependencies when only source files change. |
| `EXPOSE 3000` | Documents that the container listens on port 3000. This is informational — it does NOT publish the port. Use `-p 3000:3000` at `docker run` to actually publish it. |
| `CMD ["node", "server.js"]` | The default command to run when the container starts. Uses exec format (JSON array) which is preferred — runs the process directly without a shell wrapper. |

**Build and run:**

```bash
docker build -t my-web-app:1.0 .
docker run -d -p 3000:3000 my-web-app:1.0
```

---

#### Q6 (M3) — Docker Storage and Networking
**"Differentiate between Docker Volumes and Bind Mounts. Briefly explain the default network drivers in Docker (bridge, host, none)."**

**Answer:**

**Docker Volumes vs Bind Mounts:**

| Aspect | Named Volume | Bind Mount |
|---|---|---|
| Who manages the location | Docker manages it (stored in `/var/lib/docker/volumes/`) | User specifies the exact host path |
| Portability | Portable — works regardless of host directory structure | Tied to a specific path on the host OS |
| Use case | Production databases, persistent application data | Development (sharing source code), config files |
| Performance | Optimized by Docker | Dependent on host filesystem performance |
| Command example | `-v mydata:/var/lib/mysql` | `-v /home/user/config:/app/config` |
| Works across hosts | Can use remote storage drivers | Only works on the specific host machine |

**Bind Mount diagram:**
```
[Host: /home/user/servers.txt] <---bind mount---> [Container: /data/servers.txt]
(Changes on either side are immediately reflected on the other)
```

**Docker Network Drivers:**

**Bridge (Default):**
- The default network type for containers on a single host
- Docker creates a virtual bridge (`docker0`) on the host
- Containers on the same bridge can communicate with each other
- Containers on different bridge networks need port mapping or explicit linking
- **User-defined bridge networks** (created with `docker network create`) support DNS resolution by container name — the default `bridge` network does not

```bash
docker run nginx           # automatically on default bridge network
docker network create app-net   # user-defined bridge
```

**Host:**
- The container shares the host machine's network stack directly — no isolation
- Container binds directly to host ports (no port mapping needed or available)
- Highest performance (no network translation overhead)
- Less secure — container processes can access all host network interfaces

```bash
docker run --network host nginx   # nginx binds directly to host port 80
```

**None:**
- Disables all networking for the container
- Only the loopback interface (`lo`) is available
- The container cannot communicate with other containers or external networks
- Used for maximum isolation or batch processing that requires no network access

```bash
docker run --network none my-isolated-job
```

---

#### Q7 (M3) — Docker Compose
**"What is Docker Compose, and what problem does it solve? Explain the key sections of a docker-compose.yml file used to run a multi-container application (e.g., App + Database)."**

**Answer:**

**What is Docker Compose?**

Docker Compose is a tool that simplifies the definition, configuration, and execution of multi-container Docker applications. It allows developers to describe the entire application stack — all services, networks, and volumes — in a single YAML file. The whole stack can then be started or stopped with a single command.

**Problem it solves:**

Real-world applications consist of multiple services. For example, a web application may have:
- A frontend/backend application container
- A MySQL database container
- A Redis cache container

Without Compose, each of these requires a separate `docker run` command with specific flags for ports, environment variables, volumes, and networks. These must be run in the correct order and recreated every time. Compose replaces all of this with one file and one command.

**Key sections of docker-compose.yml:**

```yaml
services:
  app:
    build: .                         # Build image from Dockerfile in current dir
    image: my-app:latest
    ports:
      - "3000:3000"                  # Map host port 3000 to container port 3000
    environment:
      DB_HOST: db                    # Use service name "db" as hostname
      DB_PASSWORD: secret
    volumes:
      - ./app:/usr/src/app           # Bind mount for development
    networks:
      - backend-net
    depends_on:
      - db                           # Start db before app

  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: myapp
    volumes:
      - db-data:/var/lib/mysql       # Named volume for data persistence
    networks:
      - backend-net

networks:
  backend-net:                       # User-defined network for service communication

volumes:
  db-data:                           # Named volume declaration
```

**Section by section:**

| Section | Purpose |
|---|---|
| `services` | Top-level key; defines each container/service |
| `build` | Path to Dockerfile to build the image |
| `image` | Use a pre-built image from the registry |
| `ports` | `"host:container"` port mapping |
| `environment` | Environment variables injected at runtime |
| `volumes` | Mount paths — bind mounts or named volumes |
| `networks` | Attach service to one or more named networks |
| `depends_on` | Define startup order |
| `networks` (top-level) | Declare the named networks |
| `volumes` (top-level) | Declare the named volumes |

**Commands:**

```bash
docker compose up -d      # Start all services in background
docker compose down       # Stop and remove containers and networks
docker compose ps         # Check service status
docker compose logs app   # View logs for the "app" service
```

---

### FROM Sample.pdf — Scenario-Based Questions (Module 3)

---

#### Q16 (M3) — Cloud-Based Application Deployment
**Scenario: A startup wants to deploy a web app without physical servers. Traffic varies throughout the year.**

1. **IaaS for this requirement:**
   The startup provisions virtual machines on a cloud provider (e.g., Linode). During peak traffic, more VMs are added; during low traffic, they are reduced. The startup pays only for resources used — no upfront hardware cost.

2. **Resources to provision:**
   - Virtual machine (compute): CPU, RAM
   - Storage: block storage for data, object storage for static assets
   - Networking: public IP address, load balancer for multiple instances, firewall rules

3. **Steps to set up a Linux server:**
   Create Linode instance (choose Ubuntu, region, plan, SSH key) -> SSH in -> update packages -> configure firewall (ufw) -> create a non-root sudo user -> install runtime -> deploy application -> set up a process manager (pm2) for auto-restart

4. **Cloud deployment advantages over physical infrastructure:**
   - No hardware purchase or maintenance
   - Elastic scaling up or down on demand
   - Pay-as-you-go pricing
   - Global regions for low-latency delivery
   - High availability through provider SLAs

---

#### Q18 (M3) — Nexus Artifact Repository
**Scenario: Developers store JAR files on personal systems and share via email.**

1. **Problems with this approach:**
   - No version control for artifacts — impossible to know which version is deployed
   - Email attachments get lost or corrupted
   - Different team members may use different (stale) versions
   - Cannot roll back to a previous artifact easily
   - No access control — anyone can modify the file

2. **How Nexus solves this:**
   Nexus acts as a central, versioned store for all build artifacts. CI pipeline publishes the artifact after a successful build. Deployment scripts pull the exact version required.

3. **Repository type purposes:**
   - **Hosted:** stores your own published artifacts
   - **Proxy:** caches external dependencies (Maven Central) locally
   - **Group:** provides one unified URL for all repository content

4. **Benefits of centralized artifact management:**
   - All teams use the same binary — no version mismatch
   - Artifacts are versioned and immutable
   - Easy audit trail of what was deployed when
   - Faster builds (dependencies cached locally via Proxy)

---

#### Q20 (M3) — Docker Containerization
**Scenario: A Java app works on the developer's laptop but fails on the server due to different Java versions.**

1. **How Docker solves this:**
   The developer packages the application, its exact Java version, and all dependencies into a Docker image. When the tester or deployment server runs this image, they get an identical environment — the same Java version, same libraries, same configuration.

2. **Docker Image vs Container:**
   - **Image:** A read-only, layered blueprint built from a Dockerfile. Contains the application code, runtime, libraries, and config. Cannot be modified after creation.
   - **Container:** A running instance of an image. Multiple containers can be created from one image. Each container has its own writable layer for changes during runtime.

3. **Basic Docker Architecture:**
   Docker Client communicates with Docker Daemon over REST API. The Daemon manages images, containers, volumes, and networks. Images are stored in and pulled from a Registry (Docker Hub or private).

4. **Advantages of containerization:**
   - Environment consistency ("build once, run anywhere")
   - Isolation between applications on the same host
   - Lightweight compared to VMs (shares OS kernel)
   - Fast startup and reproducible deployments
   - Easy rollback — redeploy the previous image version

---

#### Q21 (M3) — Dockerfile
**Scenario: Containerize a Java application (app.jar).**

```dockerfile
FROM openjdk:17-jre-slim

WORKDIR /app

COPY app.jar app.jar

EXPOSE 8080

CMD ["java", "-jar", "app.jar"]
```

```bash
# Build the image
docker build -t java-app:1.0 .

# Run the container
docker run -d -p 8080:8080 java-app:1.0
```

---

#### Q22 (M3) — Docker Volumes
**Scenario: MySQL database in a container loses all data when the container is deleted.**

1. **Why data is lost:**
   Containers have a writable layer that is tied to the container's lifecycle. When the container is deleted, this writable layer (and all data in it, including MySQL data files) is deleted with it.

2. **Purpose of Docker volumes:**
   Docker volumes store data outside the container's writable layer, on the host filesystem or a remote storage driver. Data in a volume persists even after the container is stopped, removed, or replaced with a new version.

3. **Modified deployment with persistence:**
   ```bash
   # Create a named volume
   docker volume create mysql-data

   # Run MySQL with the volume mounted
   docker run -d \
     --name mysql-db \
     -e MYSQL_ROOT_PASSWORD=secret \
     -v mysql-data:/var/lib/mysql \
     mysql:8
   ```
   Now even if `mysql-db` is removed and recreated, the data in `mysql-data` persists.

4. **Why not store data in the container's writable layer:**
   The writable layer is ephemeral, hard to back up, cannot be shared between containers, and is lost on container removal. Volumes are independently managed, can be backed up, and can be shared across containers or even across hosts (with remote volume drivers).

---

#### Q23 (M3) — Docker Networking
**Scenario: A frontend container needs to communicate with a backend API container.**

1. **How Docker networking facilitates communication:**
   By placing both containers on the same user-defined Docker network, Docker's embedded DNS resolver lets each container reach the other using its container name as the hostname.

2. **Placing both containers on the same network:**
   ```bash
   docker network create app-net
   docker run -d --name backend --network app-net my-backend-api
   docker run -d --name frontend --network app-net -p 3000:3000 my-frontend
   ```

3. **How frontend accesses backend:**
   Inside the frontend container, HTTP requests are sent to `http://backend:<port>`. Docker DNS resolves `backend` to the backend container's IP address automatically.

4. **Advantage of using names over hard-coded IPs:**
   Container IP addresses are dynamically assigned and can change when containers are recreated. Using the container/service name is stable — Docker DNS always resolves it to the current IP. This makes the system resilient to container restarts and easier to configure.

---

#### Q24 (M3) — Docker Compose (Frontend + Backend + Database)

```yaml
services:
  frontend:
    build: ./frontend
    ports:
      - "3000:3000"
    networks:
      - app-net
    depends_on:
      - backend

  backend:
    build: ./backend
    environment:
      DB_HOST: db
      DB_PORT: 3306
    networks:
      - app-net
    depends_on:
      - db

  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: myapp
    volumes:
      - db-data:/var/lib/mysql
    networks:
      - app-net

networks:
  app-net:

volumes:
  db-data:
```

```bash
# Start everything
docker compose up -d

# Stop everything
docker compose down
```

**Networking:** Compose automatically creates `app-net`. All three services are on it and can communicate by service name (frontend -> backend, backend -> db).

---

#### Q25 (M3) — Private Docker Repository

1. **Why private registry:**
   Internal applications (e.g., banking) contain proprietary code and must not be publicly accessible. A private registry ensures only authenticated users and servers can pull the image.

2. **Building and tagging:**
   ```bash
   docker build -t banking-app:2.1 .
   docker tag banking-app:2.1 registry.company.com:5000/banking-app:2.1
   ```

3. **Authentication before push:**
   ```bash
   docker login registry.company.com:5000
   # Enter username and password
   docker push registry.company.com:5000/banking-app:2.1
   ```

4. **Workflow:**
   ```
   Developer
      |
   docker build & docker tag
      |
   docker login  ->  Private Registry  <-  docker login (from deployment server)
      |                                           |
   docker push                               docker pull
                                                   |
                                             docker run
                                                   |
                                          Running Container (Cloud Server)
   ```

---

*End of DevOps_Mod_3.md*
