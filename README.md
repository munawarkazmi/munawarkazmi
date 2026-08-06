<div align="center">

# Munawar Kazmi

### Robotics & AI Research Engineer

**I build robots that navigate safely, AI that runs on the edge, and software that real institutions depend on every day.**

MSc AI & Robotics (Commendation) · University of Hertfordshire

[![Portfolio](https://img.shields.io/badge/munawarkazmi.com-visit_my_portfolio-0f2f52?style=for-the-badge)](https://munawarkazmi.com)
[![Preprint](https://img.shields.io/badge/preprint-10.5281%2Fzenodo.21756817-b08d3f?style=for-the-badge)](https://doi.org/10.5281/zenodo.21756817)

</div>

---

## Proof, not promises

| 32/32 | 4.3x | 35/35 · 32/32 | 0 | 80/80 | 548 |
| :---: | :---: | :---: | :---: | :---: | :---: |
| certified legibility intervals holding, over every world and budget I bound - the upper end rules out *every* trajectory, not the ones I searched | faster replanning, D* Lite vs A*, seeded 200-trial benchmark | unsafe qwen2.5-7B and llama-3.3-70B trajectories caught by my safety verifier, per model | missed dangers - 2,071 constructed + 80 real-model verifier cases, each count CI-enforced | decodes in which a model called its own trajectory legible, two models over eight worlds - 25 of those trajectories were not physically possible | CI-enforced tests behind my LLM-planner benchmark, differential-tested against pyperplan |

My work sits where autonomy meets responsibility: human-robot interaction, sim-to-real
transfer, and keeping learned systems honest before they touch hardware. Every robotics
number above is produced by committed code and re-verified in CI on every push - clone
the repo, run one command, get the same number. The products are in production for real users.

## Featured work

| Project | What it is |
| --- | --- |
| [legibility-bounds](https://github.com/munawarkazmi/legibility-bounds) | Certified two-sided bounds on how legible a robot trajectory can be under a path budget - the half no search can give you, because it quantifies over *every* admissible trajectory rather than the ones somebody tried. Belief turns out to be a fixed field (path length cancels from the observer's posterior), reachability cuts each sample to a lens, and writing belief as odds against the true goal makes the bound survive next to obstacles where the geodesic metric breaks the usual argument. The lower end is *constructed*, not searched: it beats the vendored search in 13 of 32 cases by up to 0.1485. 32 world-ceiling pairs, 0 violations, gaps from 0.0065 to 0.0567. It also certifies what safety costs - comparing two searches cannot establish a constraint costs anything, so 3 of 8 pairs certify a positive price and the rest certify nothing and say so. 62 tests; every number in the README is generated, with a `--check` mode that fails when it goes stale. RA-L draft in `paper/`. |
| [llm-nav-shield](https://github.com/munawarkazmi/llm-nav-shield) | The keystone: an LLM proposes a trajectory, my verifier checks it, my planning core recovers a provably-safe path when it fails, and the system halts when no safe path exists. Composition of the two verified cores below as pinned submodules. Replaying 40 committed qwen2.5-7B proposals: 38/38 flawed plans recovered, 0 unsafe forwarded, 10/10 sealed-goal cases halted - all CI-enforced. |
| [toolcall-contract](https://github.com/munawarkazmi/toolcall-contract) | The shield's architecture pointed at agent frameworks: a deterministic two-layer validator for LLM tool calls. Stdlib structural checker in 25,000-case differential agreement with pinned jsonschema, plus the semantic contract layer where failures actually live - on the same 40 committed tasks, qwen2.5-7B broke 0 schemas and 7 contracts, llama-3.3-70B 0 and 5; CI replays both datasets. |
| [legible-motion-bench](https://github.com/munawarkazmi/legible-motion-bench) | Robots that pay path cost to make their destination obvious, and what that costs them in safety. Legibility is Dragan's, not mine; what this measures is the three-way trade between clarity, path cost and constraint satisfaction, exactly and with no human or model judging. Eight worlds, each carrying machine-checked facts about its own geometry, 235 CI-enforced tests, exact optimal cost-to-go over a visibility graph with a guarded predicate that matches rational arithmetic on 20,000 near-collinear cases where plain floating point gets the sign wrong. Asked to be legible under a stated path budget, two models called all 80 of their trajectories legible; 25 of those were not physically possible, and in the world built so that clarity and the keep-out zone conflict, both models bought the clarity and entered the zone on every one of ten samples. Given four different budgets, the smaller model's median path cost moved by 0.012. |
| [plan-failure-bench](https://github.com/munawarkazmi/plan-failure-bench) | Research benchmark measuring how LLM planners fail at robot tasks, not just how often: 60 trap-labelled instructions over two symbolic environments, ground truth decidable end to end with a 548-test suite re-run in CI (the count itself is CI-asserted), a semantically obfuscated condition, and no human or LLM judging anywhere. The fixed-prompt grid is complete at 18 committed runs over four models: a frontier reasoning model repeats every headline count under full semantic obfuscation on both environments, 13 of 13 traps with 0 false positives, while smaller models split between never refusing at all and refusing on surface semantics alone. Published as a citable preprint, [DOI 10.5281/zenodo.21756817](https://doi.org/10.5281/zenodo.21756817), with every citation checked against the cited paper's body and the record of those checks published as an appendix. |
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

- Building legible-motion-bench, measuring what a robot gives up in safety when it moves to make its destination obvious, and whether language models can do it when asked
- Extending plan-failure-bench's k=5 sampling protocol to the remaining grid cells, the single change that would most strengthen its claims
- Running and evolving a production school platform serving students, teachers, and staff daily
- **Open to research collaborations and PhD opportunities** in robotics and trustworthy AI

<div align="center">

---

*The best systems are the ones people trust without thinking about them.*

**[munawarkazmi.com](https://munawarkazmi.com)**

</div>
