<div align="center">

# Munawar Kazmi

### Robotics & AI Research Engineer

**Keeping learned systems honest before they reach hardware.**

MSc AI & Robotics (Commendation) · University of Hertfordshire

[![Portfolio](https://img.shields.io/badge/munawarkazmi.com-visit_my_portfolio-0f2f52?style=for-the-badge)](https://munawarkazmi.com)
[![Preprint](https://img.shields.io/badge/preprint-10.5281%2Fzenodo.21756817-b08d3f?style=for-the-badge)](https://doi.org/10.5281/zenodo.21756817)

</div>

---

| **4.3x** | **0 / 2,151** | **32 / 32** |
| :---: | :---: | :---: |
| faster replanning<br>D* Lite vs A*, 200 seeded trials | unsafe trajectories missed<br>by my LLM safety verifier | certified legibility bounds holding<br>every world, every budget |

**Every number here is checkable.** Each is produced by committed code and re-verified in CI on every
push. When the evidence behind an earlier claim was lost, the claim was withdrawn rather than restated
on trust, and the withdrawal stays published beside it.

## Between a language model and a robot

Not four projects but one line of work: measure how models fail, catch it, compute a correct
alternative, then decide between fixing the plan and stopping.

- **[plan-failure-bench](https://github.com/munawarkazmi/plan-failure-bench):** how LLM planners fail at robot tasks, not just how often. 60 trap-labelled instructions, ground truth decidable end to end, no human or model judging anywhere, 548 proofs re-run in CI. [Preprint](https://doi.org/10.5281/zenodo.21756817).
- **[ros2-llm-safety-verifier](https://github.com/munawarkazmi/ros2-llm-safety-verifier):** a deterministic gate between the model and Nav2. 35/35 unsafe qwen2.5-7B and 32/32 unsafe llama-3.3-70B trajectories caught, zero misses, zero false positives, microsecond latency.
- **[ros2-dynamic-path-planning](https://github.com/munawarkazmi/ros2-dynamic-path-planning):** A* and D* Lite as Nav2 plugins over a ROS-free C++20 core. 4.3x faster replans on average, validated against Dijkstra across 185,237 fuzzed cases.
- **[llm-nav-shield](https://github.com/munawarkazmi/llm-nav-shield):** the three composed into verify, recover, or halt when nothing safe exists. 38/38 flawed plans recovered, 0 unsafe forwarded, then replayed on three public ROS bags where real costmaps break assumptions the synthetic ones never could.
- **[toolcall-contract](https://github.com/munawarkazmi/toolcall-contract):** the same question away from robots. Two layers for LLM tool calls, where the semantic layer catches 7 contract breaks that the schema layer scores as clean.

## Motion that explains itself

A robot that signals where it is going is easier to work beside, and that clarity is not free. One
project bounds it, the other prices it.

- **[legibility-bounds](https://github.com/munawarkazmi/legibility-bounds):** certified two-sided bounds on how legible a trajectory can be under a path budget, quantified over every admissible trajectory rather than the ones somebody searched. 32 world-ceiling pairs, 0 violations. RA-L draft in `paper/`.
- **[legible-motion-bench](https://github.com/munawarkazmi/legible-motion-bench):** what that clarity costs in safety and path length, measured with no judging anywhere. Two models called all 80 of their trajectories legible; 25 of those were not physically possible.

## Foundations, and things already running

- **[exact-predicates](https://github.com/munawarkazmi/exact-predicates):** geometric predicates that cannot be wrong, grown from a real key-tie bug in my own D* Lite. 657 adversarial cases where CI asserts the float version is wrong and the exact one is right. Exactness costs about 2x, measured.
- **[degregorio-blowup](https://github.com/munawarkazmi/degregorio-blowup):** finite-time blowup in a 1D model for 3D Euler. Regressing an unknown constant against a known one cancels the discretisation error and collapses the spread 800-fold: `beta = 3.0024227 +/- 5e-6`, excluding the natural guess of exactly 3.
- **[safina-portal-showcase](https://github.com/munawarkazmi/safina-portal-showcase):** school management system in production for a real institute. Seven roles, admissions, prorated cash billing, payroll, and an append-only audit trail written by triggers. Built, shipped and operated solo.
- **[esp32-cam-motion-detector](https://github.com/munawarkazmi/esp32-cam-motion-detector):** deterministic motion-detection firmware from a commercial prototype. No ML, no vision libraries, compiled for the target board in CI on every push.

## Toolbox

C++20, Python, ROS 2 and Nav2, Docker, Git and CI. TensorRT, Jetson Nano and Orin, ESP32, LoRa mesh.
React, TypeScript, PostgreSQL with row-level security, Supabase.

## Currently

- Extending plan-failure-bench's k=5 sampling to the remaining grid cells, the single change that would most strengthen its claims
- Preparing the legibility-bounds RA-L draft for submission
- Running a production school platform used daily by students, teachers and staff
- **Open to research collaborations and PhD opportunities** in robotics and trustworthy AI

<div align="center">

**[munawarkazmi.com](https://munawarkazmi.com)**

</div>
