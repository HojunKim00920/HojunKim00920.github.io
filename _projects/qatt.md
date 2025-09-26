---
layout: page
title: QATT Control Paradigm
description: A new paradigm for uncertainty quantification by re-defining the command 'Gap' as a rich information signal. # 프로젝트 목록에 표시될 한 줄 요약
img: assets/img/qatt_preview.jpg # 프로젝트 목록에 표시될 썸네일 이미지
importance: 1 # 숫자가 낮을수록 프로젝트 목록 위에 표시됩니다
category: Independent Research # 프로젝트 카테고리
---

This project documents an intellectual odyssey. It began with a straightforward, albeit naïve, attempt to improve a quadrotor controller and culminated in the foundational principles of my research vision: a new paradigm for quantifying uncertainty by interpreting the internal conflicts within a control architecture.

---

### Phase 1: The Naïve Fusion Hypothesis
My research began upon receiving the QATT problem from my advisor, Prof. Rifat Sipahi. Inspired by the impressive results from literature on **[Differential Flatness (DF)](https://arxiv.org/abs/1809.04048)** and **Sliding Mode Control with a Disturbance Observer (SMC+DOB)**, I formed a simple hypothesis: combining the two would yield superior performance for aggressive maneuvers.

* **Baseline Controller (C1):** The robust SMC+DOB framework from [Jing et al] (https://www.mdpi.com/2504-446X/6/9/261).
* **Experimental Controller (C5):** My initial modification, replacing the reference attitude signals in the SMC loop with values derived from DF.
* **Blended Controller (C6):** A further attempt creating a linear combination of the two signals.

I implemented these controllers in a high-fidelity SITL simulation environment (MATLAB/Simulink) and tested them against 10 aggressive trajectories.

**The Result: Systematic Failure.**
Across all tests, neither C5 nor C6 demonstrated any clear, consistent performance improvement over the baseline C1. The approach was a failure, forcing me to confront a fundamental flaw in my reasoning: I lacked theoretical justification for why this fusion *should* work.

---

### The Pivotal Question: A Shift in Perspective
This systematic failure became the project's most valuable outcome. It forced me to abandon the superficial question of "How do we best mix these signals?" and ask a more profound one:

> **"Why are these signals different in the first place?"**

This question shifted my entire research focus from signal fusion to signal analysis.

---

### The Breakthrough: The 'Gap' as a Rich Information Signal
Even in a pristine simulation environment with no external disturbances, I observed a persistent, non-zero discrepancy—the **'Gap'**—between the outer loop's demand (`ϕ_des`) and the DF-derived ideal (`ϕ_DF`).

I redefined this 'Gap' not as a nuisance to be eliminated, but as a real-time symptom of **'Lumped Uncertainty'**—the sum of all unmodeled dynamics, parameter uncertainties, and other discrepancies. This re-framing elevated the project from a technical exercise to a new paradigm for real-time uncertainty quantification.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/your_gap_graph.png" title="Fig 1: The observed 'Gap' between command signals" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A graph from simulation plotting `ϕ_des` and `ϕ_DF` over time, clearly showing the persistent 'Gap'.
</div>


---

### Future Directions: From a Special Case to a General Theory
My doctoral research will be dedicated to transforming this fascinating symptom into a reliable engineering tool.

* **The 'Gap' as a Nonlinear Observer:** My goal is to design a framework to mathematically isolate the pure uncertainty information from the observed 'Gap'.
* **Causal Inference:** The next step is to solve the nonlinear inverse problem: to infer the physical forces (the cause) from the purified 'Gap' signal (the symptom).
* **Generalization of the Principle:** I plan to investigate how the 'Gap' manifests in other control architectures, like Model Predictive Control (MPC), to develop a unified theory.

---

### Connection to My Research Interests
This intellectual journey is the bedrock of my passion for **Robust Control, Optimization, and Nonlinear Dynamics**. The 'Gap' philosophy is my first concrete step toward achieving **Provably Safe Autonomy**.
