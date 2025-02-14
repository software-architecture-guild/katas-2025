# ADR 3: AI/ML as an Assistant, Not a Fully Automated System

**Date**: 2025-02-14

## Status

Proposed

## Context

AI and ML models are powerful tools for augmenting human decision-making but are not infallible. Relying solely on automated AI/ML-based grading or decision-making can introduce significant risks, such as bias, incorrect assessments, or failure to account for nuanced scenarios that require human judgment.

To maintain the integrity of the certification process and ensure reliability, AI/ML will be used exclusively as an **assistant** — providing recommendations, identifying potential issues, and enhancing efficiency—while final decisions remain with human experts.

## Decision

AI/ML usage within our system will adhere to the following principles:

* **AI/ML will only function as an assistant**, never as a fully automated decision-maker.
* **Experts will retain full control over all grading and certification decisions**, with AI/ML acting in a supportive role.
* **AI-generated recommendations will require human validation** before being acted upon.
* **Transparency in AI suggestions must be maintained**, ensuring that experts understand how recommendations are derived.
* **AI-assisted tools should focus on increasing efficiency** rather than replacing human expertise.

## Consequences

### Positive

* Ensures human oversight in all critical decisions, preventing AI-driven errors or biases from negatively impacting certification outcomes.
* Leverages AI's efficiency while preserving expert judgment and domain knowledge.
* Encourages trust in AI-assisted systems by keeping human experts as the final authority.
* Reduces workload on experts while maintaining a high standard of accuracy and quality.
* Improves explainability and accountability by requiring human validation of AI-generated outputs.

### Negative

* Slower decision-making compared to fully automated systems, as human intervention is always required.
* Experts may initially resist adopting AI-assisted workflows if they perceive them as unnecessary or intrusive.
* Increased complexity in system design, as AI must be built to function as an advisory tool rather than an autonomous system.

### Risks

* Over-reliance on AI recommendations could lead to complacency among experts, reducing their engagement in decision-making.
* AI-generated suggestions may still contain biases or inaccuracies, necessitating rigorous validation protocols.
* Inefficient AI assistance could result in longer review times if not properly optimized.

By embedding these principles, we ensure that AI remains a **trusted assistant** rather than an autonomous decision-maker, preserving the credibility and quality of our certification process.
