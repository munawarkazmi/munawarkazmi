<div align="center">

# Munawar Kazmi

### Robotics & AI Research Engineer

**I build robots that navigate safely, AI that runs on the edge, and software that real institutions depend on every day.**

MSc AI & Robotics (Commendation) · University of Hertfordshire

[![Portfolio](https://img.shields.io/badge/munawarkazmi.com-visit_my_portfolio-0f2f52?style=for-the-badge)](https://munawarkazmi.com)

</div>

---

## Proof, not promises

| 4.3x | 35/35 · 32/32 | 0 | 548 | 7 |
| :---: | :---: | :---: | :---: | :---: |
| faster replanning, D* Lite vs A*, seeded 200-trial benchmark | unsafe qwen2.5-7B and llama-3.3-70B trajectories caught by my safety verifier, per model | missed dangers - 2,071 constructed + 80 real-model verifier cases, each count CI-enforced | CI-enforced tests behind my LLM-planner benchmark, differential-tested against pyperplan | user roles served daily by my production school platform |

My work sits where autonomy meets responsibility: human-robot interaction, sim-to-real
transfer, and keeping learned systems honest before they touch hardware. Every robotics
number above is produced by committed code and re-verified in CI on every push - clone
the repo, run one command, get the same number. The products are in production for real users.

## Featured work

| Project | What it is |
| --- | --- |
| [llm-nav-shield](https://github.com/munawarkazmi/llm-nav-shield) | The keystone: an LLM proposes a trajectory, my verifier checks it, my planning core recovers a provably-safe path when it fails, and the system halts when no safe path exists. Composition of the two verified cores below as pinned submodules. Replaying 40 committed qwen2.5-7B proposals: 38/38 flawed plans recovered, 0 unsafe forwarded, 10/10 sealed-goal cases halted - all CI-enforced. |
| [toolcall-contract](https://github.com/munawarkazmi/toolcall-contract) | The shield's architecture pointed at agent frameworks: a deterministic two-layer validator for LLM tool calls. Stdlib structural checker in 25,000-case differential agreement with pinned jsonschema, plus the semantic contract layer where failures actually live - on the same 40 committed tasks, qwen2.5-7B broke 0 schemas and 7 contracts, llama-3.3-70B 0 and 5; CI replays both datasets. |
| [plan-failure-bench](https://github.com/munawarkazmi/plan-failure-bench) | Research benchmark measuring how LLM planners fail at robot tasks, not just how often: 60 trap-labelled instructions over two symbolic environments, ground truth decidable end to end with a 548-test suite re-run in CI (the count itself is CI-asserted), a semantically obfuscated condition, and no human or LLM judging anywhere. Results for four models - a local 7B through a frontier reasoning model - committed as replayable records; working paper in progress. |
| [ROS2 Dynamic Path Planning](https://github.com/munawarkazmi/ros2-dynamic-path-planning) | A* and D* Lite as Nav2 plugins over a ROS-free C++20 core, validated against Dijkstra ground truth (185k fuzzed replans, exact equality). In a fair, seeded 200-trial benchmark on a real building map, D* Lite replans 4.3x faster on average (11x median) - full per-event data committed, re-run in CI. |
| [exact-predicates](https://github.com/munawarkazmi/exact-predicates) | Geometric predicates that cannot be wrong, grown from the D* Lite key-tie bug: exact integer arithmetic under code-enforced bounds, an unbounded big-integer oracle, and 657 committed adversarial cases where CI asserts the float version is wrong AND the exact one is right - every case, every push. Exactness costs ~2x, measured. |
| [ROS2 LLM Safety Verifier](https://github.com/munawarkazmi/ros2-llm-safety-verifier) | Deterministic safety gate between LLM planners and Nav2. Against real model output over the same 40 scenarios: qwen2.5-7B proposed unsafe trajectories in 35, llama-3.3-70B in 32 - the verifier caught every one, zero misses and zero false positives for both, at microsecond latency. The 70B model hit every endpoint and still drove through obstacles: unsafe-but-on-target, the exact failure a runtime gate exists for. Prompts, raw responses, and the evaluator are committed; CI replays both datasets. |
| [ESP32-CAM Motion Detector](https://github.com/munawarkazmi/esp32-cam-motion-detector) | Deterministic motion-detection firmware from a commercial prototype (Muxtronics 2025): block-difference detection, no ML, no vision libraries, CI-compiled for the target board on every push. Demo video and signed academic reference included; claims nothing it cannot back. |
| [Safina Portal](https://github.com/munawarkazmi/safina-portal-showcase) | Complete school management system in production for an educational institute: seven user roles, prorated billing, payroll, digital ID cards, and an append-only, trigger-written audit trail. Designed, built, shipped, and operated end to end, solo. |

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

## What working with me looks like

- **I ship.** From firmware on a camera board to a school's entire operations platform, my projects end in deployment, not in slides.
- **Safety is a feature I engineer, not a word I use.** Protective stops on real robots, verification layers in front of LLMs, audit trails behind every database write.
- **I own systems end to end.** Requirements, architecture, code, security model, documentation in two languages, and the 2 a.m. bug.

## Currently

- Extending safety verification for learned planners in ROS2
- Running and evolving a production school platform serving students, teachers, and staff daily
- **Open to research collaborations and PhD opportunities** in robotics and trustworthy AI

<div align="center">

---

*The best systems are the ones people trust without thinking about them.*

**[munawarkazmi.com](https://munawarkazmi.com)**

</div>
