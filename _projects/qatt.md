---
layout: page
title: QATT Control Paradigm
description: A new paradigm for uncertainty quantification in control systems.
img: assets/img/qatt_preview.jpg # 이 프로젝트를 대표할 이미지 파일명
importance: 1
category: Research
---

This project documents an intellectual odyssey. It began with a straightforward, albeit naïve, attempt to improve a quadrotor controller and culminated in the foundational principles of my research vision: a new paradigm for quantifying uncertainty by interpreting the internal conflicts within a control architecture.

---

### Phase 1: The Naïve Fusion Hypothesis
My research began upon receiving the QATT problem from my advisor, Prof. Rifat Sipahi. Inspired by the impressive results from literature on **Differential Flatness (DF)** and the robustness of **Sliding Mode Control with a Disturbance Observer (SMC+DOB)**, I formed a simple hypothesis: combining the two would yield superior performance for aggressive maneuvers.

The Result: **Systematic Failure.** Rigorous SITL simulations proved this approach was a failure, forcing me to confront a fundamental flaw in my reasoning and ask a more profound question.

---

### The Pivotal Question: "Why are these signals different in the first place?"

This question shifted my entire research focus from signal fusion to signal analysis, leading to the discovery of the **'Gap'**.

---

### The Breakthrough: The 'Gap' as a Rich Information Signal
I redefined this 'Gap' not as a nuisance to be eliminated, but as a real-time, high-fidelity symptom of **'Lumped Uncertainty'**—the sum of all unmodeled dynamics, parameter uncertainties, and external disturbances that the ideal mathematical model fails to capture.

This re-framing elevated the project from a technical exercise to a new paradigm for real-time uncertainty quantification.

*(...여기에 QATT 프로젝트의 나머지 상세 설명, 이미지, 수식 등을 추가하세요...)*
