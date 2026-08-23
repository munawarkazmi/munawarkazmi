<div align="center">

# Munawar Kazmi

### Robotics & AI Research Engineer

**I build robots that navigate safely, AI that runs on the edge, and software that real institutions depend on every day.**

MSc AI & Robotics (Commendation) · University of Hertfordshire

[![Portfolio](https://img.shields.io/badge/munawarkazmi.com-visit_my_portfolio-0f2f52?style=for-the-badge)](https://munawarkazmi.com)
[![Preprint](https://img.shields.io/badge/preprint-10.5281%2Fzenodo.21756817-b08d3f?style=for-the-badge)](https://doi.org/10.5281/zenodo.21756817)

</div>

---

| **4.3x** | **0 / 2,151** | **32 / 32** |
| :---: | :---: | :---: |
| faster replanning<br>D* Lite vs A*, 200 seeded trials | unsafe trajectories missed<br>by my LLM safety verifier | certified legibility bounds holding<br>every world, every budget |

My work sits where autonomy meets responsibility: human-robot interaction, sim-to-real
transfer, and keeping learned systems honest before they touch hardware.

**Every number below is checkable.** Each one is produced by committed code and re-verified
in CI on every push — clone the repo, run one command, get the same number. Where a result
has not survived review, the retraction is published next to the claim it replaced.

## Featured work

| Project | What it is |
| --- | --- |
| [legibility-bounds](https://github.com/munawarkazmi/legibility-bounds) | Certified two-sided bounds on how legible a robot trajectory can be under a path budget — quantified over *every* admissible trajectory, not the ones somebody searched. 32 world-ceiling pairs, 0 violations. RA-L draft in `paper/`. |
| [plan-failure-bench](https://github.com/munawarkazmi/plan-failure-bench) | How LLM planners fail at robot tasks, not just how often: 60 trap-labelled instructions, ground truth decidable end to end, no human or model judging anywhere. 548 CI-enforced tests. Citable preprint: [DOI 10.5281/zenodo.21756817](https://doi.org/10.5281/zenodo.21756817). |
| [llm-nav-shield](https://github.com/munawarkazmi/llm-nav-shield) | An LLM proposes a trajectory, my verifier checks it, my planner recovers a safe one, and the system halts when none exists. Replaying 40 committed proposals: 38/38 flawed plans recovered, 0 unsafe forwarded. |
| [ros2-llm-safety-verifier](https://github.com/munawarkazmi/ros2-llm-safety-verifier) | Deterministic safety gate between LLM planners and Nav2. Over 40 real scenarios it caught 35/35 unsafe qwen2.5-7B and 32/32 unsafe llama-3.3-70B trajectories — zero misses, zero false positives, microsecond latency. |
| [ros2-dynamic-path-planning](https://github.com/munawarkazmi/ros2-dynamic-path-planning) | A* and D* Lite as Nav2 plugins over a ROS-free C++20 core. 4.3x faster replans on average (11x median) in a fair seeded benchmark, validated against Dijkstra ground truth on 185k fuzzed replans. |
| [legible-motion-bench](https://github.com/munawarkazmi/legible-motion-bench) | What clarity costs a robot in safety, measured exactly with no human or model judging. Two models called all 80 of their trajectories legible; 25 of those were not physically possible. |
| [toolcall-contract](https://github.com/munawarkazmi/toolcall-contract) | Two-layer validator for LLM tool calls. The structural layer agrees with pinned jsonschema across 25,000 differential cases; the semantic layer catches what it cannot — 7 contract breaks where the schema layer saw 0. |
| [exact-predicates](https://github.com/munawarkazmi/exact-predicates) | Geometric predicates that cannot be wrong, grown from a real D* Lite key-tie bug. 657 committed adversarial cases where CI asserts the float version is wrong and the exact one is right. Exactness costs ~2x, measured. |
| [degregorio-blowup](https://github.com/munawarkazmi/degregorio-blowup) | Finite-time blowup in a 1D model for 3D Euler. Regressing an unknown constant against a known one cancels the discretisation error and collapses the spread 800-fold: `beta = 3.0024227 +/- 5e-6`, excluding the natural guess of exactly 3. |
| [esp32-cam-motion-detector](https://github.com/munawarkazmi/esp32-cam-motion-detector) | Deterministic motion-detection firmware from a commercial prototype (Muxtronics 2025). No ML, no vision libraries, CI-compiled for the target board on every push. |
| [safina-portal-showcase](https://github.com/munawarkazmi/safina-portal-showcase) | School management system in production for a real institute: seven user roles, prorated billing, payroll, and an append-only, trigger-written audit trail. Built, shipped, and operated solo. |

## Toolbox

**Robotics and systems**

![C++](https://img.shields.io/badge/C++20-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![ROS2](https://img.shields.io/badge/ROS2_Nav2-22314E?style=flat-square&logo=ros&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git_&_CI/CD-F05032?style=flat-square&logo=git&logoColor=white)

**Edge AI and embedded**

![TensorRT](https://img.shields.io/badge/TensorRT-76B900?style=flat-square&logo=nvidia&logoColor=white)
![Jetson](https://img.shields.io/badge/Jetson_Nano_/_Orin-76B900?style=flat-square&logo=nvidia&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=flat-square&logo=espressif&logoColor=white)
![LoRa](https://img.shields.io/badge/LoRa_Mesh-2C3E50?style=flat-square)

**Full-stack**

![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL_+_RLS-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)

## Currently

- Extending plan-failure-bench's k=5 sampling protocol to the remaining grid cells — the single change that would most strengthen its claims
- Preparing the legibility-bounds RA-L draft for submission
- Running and evolving a production school platform serving students, teachers, and staff daily
- **Open to research collaborations and PhD opportunities** in robotics and trustworthy AI

<div align="center">

**[munawarkazmi.com](https://munawarkazmi.com)**

</div>
