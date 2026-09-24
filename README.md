<div align="center">

# Hey, I'm Tarun 👋

**M.Tech CS @ IIIT Hyderabad** · I build backend systems that hold up under load, and I like knowing what the kernel is doing underneath them.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-tarun--rajai--iiith-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/tarun-rajai-iiith/)
[![LeetCode](https://img.shields.io/badge/LeetCode-rajaiTarun-FFA116?style=for-the-badge&logo=leetcode&logoColor=black)](https://leetcode.com/u/rajaiTarun/)
[![Email](https://img.shields.io/badge/Email-tarunkrajai%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:tarunkrajai@gmail.com)

</div>

---

## 🧑‍💻 About me

- 🎓 **M.Tech in Computer Science** at IIIT Hyderabad (2025–2027) · CGPA 8.59
- 🎓 **B.E. in Information Technology** from Shantilal Shah Engineering College, Bhavnagar (2021–2025) · CGPA 8.11
- 🏗️ I work mostly on **event-driven microservices in Node.js**, with **C++**, DSA and OS fundamentals behind them
- 🔍 What I care about most is what a system does **under contention**: race conditions, partial failures, retries, and keeping two databases consistent with each other
- 📫 Open to **SDE / backend / systems** roles. Reach me at **tarunkrajai@gmail.com**

---

## 🚀 Featured projects

### 🛍️ [MerchFlow](https://github.com/RajaiTarun/MerchFlow): a polyglot, event-driven microservices platform

A merch-drop portal for campus clubs. The real goal was to get flash-sale checkout right: 500 students on the same 50-unit hoodie at the same second, and inventory still ends at exactly zero.

`5 services` · `2 databases` · `1 message broker` · `4 design patterns` · `0 oversells`

- **Architecture:** API Gateway, Auth/User, Catalog, Order and Notification services in **Node.js/Express**, with a zero-trust gateway that owns JWT verification, RBAC and rate limiting
- **Polyglot persistence:** **PostgreSQL** for ACID-critical orders and **MongoDB** for the irregular, schema-flexible catalog
- **Concurrency:** **Valkey (Redis) distributed locks** (`SET NX PX` plus a token-bound Lua release) and atomic stock decrements, so checkout never oversells
- **Consistency:** a choreography-based **Saga** with idempotent, retry-with-backoff compensating transactions that roll back stock when payment fails
- **Reliability:** UUID idempotency keys stop double checkouts. Notifications go through a **RabbitMQ** pub/sub exchange, so a slow consumer never adds latency to an order
- **Frontend:** a 12-page, role-based **React 19** SPA built with React Router v7, Tailwind CSS and Vite
- **Design patterns:** Factory, Builder, Command, and Strategy + Observer, each one solving an actual problem in the system
- **Security:** I found and fixed an **IDOR** vulnerability, a cross-tenant cache-key scoping bug, and a rate limiter that could go negative under burst load
- **Deployment:** Docker Compose locally, and all 6 services on **Render** from a single blueprint → [live demo](https://frontend-6jke.onrender.com)

<p>
<img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white" />
<img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white" />
<img src="https://img.shields.io/badge/React_19-149ECA?style=flat-square&logo=react&logoColor=white" />
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" />
<img src="https://img.shields.io/badge/Valkey%2FRedis-DC382D?style=flat-square&logo=redis&logoColor=white" />
<img src="https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white" />
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
</p>

### 🐚 [POSIX](https://github.com/RajaiTarun/POSIX): an interactive Unix shell in C++

A POSIX-compliant shell written from scratch in **C++11**. It doesn't wrap `bash`. Every feature talks to the kernel directly through raw system calls.

- **Processes:** `fork` / `execvp` / `waitpid` for foreground and background jobs, with `waitpid(-1, WNOHANG)` reaping zombies on every REPL iteration
- **IPC:** **N-stage pipelines** and `<` `>` `>>` redirection, built with chained `pipe` + `dup2`. Pipes and redirects work together in one command (`cat < in.txt | sort | uniq > out.txt`)
- **Signals:** `sigaction`-based SIGINT handling with a `volatile sig_atomic_t` flag. SIGTSTP suspends only the foreground child, never the shell
- **Built-ins:** `cd`, `pwd`, `echo`, `ls -la`, `search`, `history`, and `pinfo`, which reads live `/proc/<pid>` data
- **Modular OOP design:** `ProcessExecutor`, `JobController`, `HistoryManager` and `BuiltinEngine`, with command history that persists across sessions
- **A deliberate trade-off:** I chose canonical-mode I/O over GNU readline after finding a signal-safety race condition. A crash-free shell mattered more than a fancier prompt

<p>
<img src="https://img.shields.io/badge/C%2B%2B11-00599C?style=flat-square&logo=cplusplus&logoColor=white" />
<img src="https://img.shields.io/badge/POSIX-333333?style=flat-square&logo=linux&logoColor=white" />
<img src="https://img.shields.io/badge/Linux%20%2F%20macOS-FCC624?style=flat-square&logo=linux&logoColor=black" />
</p>

---

## 🛠️ Tech stack

**Languages**
<p>
<img src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" />
<img src="https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=black" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
</p>

**Backend, databases & messaging**
<p>
<img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" />
<img src="https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white" />
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" />
<img src="https://img.shields.io/badge/RabbitMQ-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white" />
</p>

**Frontend**
<p>
<img src="https://img.shields.io/badge/React-149ECA?style=for-the-badge&logo=react&logoColor=white" />
<img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" />
<img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" />
</p>

**Tools & platforms**
<p>
<img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" />
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" />
<img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" />
<img src="https://img.shields.io/badge/Render-46E3B7?style=for-the-badge&logo=render&logoColor=black" />
</p>

**Core CS:** Data Structures & Algorithms · Object-Oriented Design & Design Patterns · Distributed Systems · Operating Systems · Computer Networks · DBMS · System Design

---

## 🧩 Problem solving

<div align="center">

<a href="https://leetcode.com/u/rajaiTarun/">
  <img src="https://leetcard.jacoblin.cool/rajaiTarun?theme=dark&font=Inter&ext=heatmap" alt="LeetCode stats for rajaiTarun" />
</a>

</div>

---

## 🏆 Achievements

- 🥇 **All India Rank 114** in IIIT Hyderabad's **PGEE 2025**, which got me into the M.Tech CS program
- 📈 **GATE CS 2025**, 97.24 percentile, in the **top 3%** of over 100,000 candidates
- ✅ Also qualified **GATE DA 2025** and **GATE CS 2024**

---

<div align="center">

*Currently learning more about distributed systems at IIIT Hyderabad, one race condition at a time.*

</div>
