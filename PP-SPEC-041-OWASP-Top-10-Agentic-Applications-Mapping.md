# PP-SPEC-041: Proof of Efficacy Mapping to OWASP Top 10 for Agentic Applications

| Field | Value |
|---|---|
| Status | DRAFT v0.1 |
| Author | Craig Ellrod, Nebulonium, Inc. (dba HACKERverse®) |
| Date | October 1, 2026 |
| License | CC BY 4.0 |
| Maps to | OWASP Top 10 for Agentic Applications |
| Series | Proof Protocol Framework Mapping Specifications |

---

## 1. Purpose

This specification defines how risk categories and adversarial conditions from the OWASP Top 10 for Agentic Applications can be bound to Proof Protocol test cases, evidence, and efficacy results.

OWASP remains authoritative for its own risk definitions, identifiers, terminology, and guidance. This document defines a **Proof Protocol mapping** and does not supersede or modify the OWASP project.

## 2. Scope

The OWASP Top 10 for Agentic Applications supplies agentic-application risk context that can identify what should be exercised. Proof Protocol supplies an independent evidence model for determining what happened during a test and whether a selected defensive control performed as claimed.

Independent witnessing and evidence-capture implementation are defined elsewhere in the Proof Protocol specification family.

## 3. Core Question

Proof of efficacy asks:

> **Was there a control, and did it work?**

An OWASP risk category identifies a class of concern. A product, architecture, policy, or safeguard may claim to mitigate that concern. Proof Protocol binds the risk context, adversarial test, control, observed behavior, downstream outcome, and evidence into a result that can be independently examined.

## 4. Metric Definitions

Against a defined adversarial corpus, each case is recorded as **blocked**, **detected**, **missed**, or **INVALID**.

Relevant measurements include:

- containment rate;
- detection rate;
- miss rate;
- false-positive rate against paired benign cases;
- robustness against manipulation, bypass, escalation, poisoning, tool misuse, identity abuse, memory abuse, or other applicable agentic attack variants;
- version-level results; and
- INVALID status when required evidence is incomplete or broken.

Target levels are engagement- and risk-specific rather than imposed by this mapping.

## 5. Evidence Produced

Mapped tests can produce:

- **Proof records** binding OWASP risk context, test case, control, system/version, verdict, timestamp, and evidence references;
- **ProofStamp™** trusted timestamps bound to evidence/verdict objects;
- **ProofBundle™** packages containing proof records, metrics, corpus manifests, and environment/context;
- **ProofRegister™** records for issued proof artifacts; and
- corpus and environment manifests identifying the tested agentic conditions.

## 6. Mapping to OWASP Top 10 for Agentic Applications

The exact OWASP risk identifiers and names SHOULD be taken from the authoritative version being mapped and recorded in the ProofBundle™. This specification does not redefine those categories.

| OWASP agentic-risk context | Proof Protocol treatment | Evidence |
|---|---|---|
| Risk identifier/category | Bind the authoritative OWASP identifier and version to the test case. | Corpus/test metadata |
| Adversarial condition | Represent the risk as one or more reproducible independently authored test cases. | Corpus manifest |
| Control/mitigation claim | Record the asserted prevention, detection, or response behavior separately from observed effect. | Control descriptor |
| Agent action | Capture what the agent attempted and what actions/tools were invoked. | Execution evidence |
| Detection outcome | Record whether the tested condition was identified. | Detection result |
| Prevention/containment outcome | Determine whether the adversarial objective reached the protected target or caused the prohibited action. | Outcome evidence |
| Tool/permission boundary | Exercise actions inside and outside asserted authority or policy limits. | Proof records |
| Identity/context/memory boundary | Exercise manipulation, substitution, poisoning, or unauthorized-use conditions where applicable. | Robustness evidence |
| Downstream effect | Obtain target, application, tool, SIEM, vendor, or equivalent evidence when necessary to establish efficacy. | Outcome evidence |
| System/version context | Bind material agent, model, policy, tool, control, and environment versions to the result. | Environment descriptor |

## 7. Interoperability Rules

1. The authoritative OWASP project/version and applicable risk identifier SHOULD be recorded.
2. OWASP identifiers, risk names, and terminology MUST NOT be silently redefined.
3. Proof Protocol verdicts are Proof Protocol results; they are not OWASP scores, certifications, or endorsements.
4. A control's presence, configuration, activation, and efficacy are distinct facts.
5. A policy decision, alert, or control trigger does not by itself establish efficacy when the claim concerns a downstream protected outcome.
6. Target, application, tool, SIEM, vendor, or equivalent evidence SHOULD complete the evidence round trip when required to establish the result.
7. Missing required evidence MUST yield **INVALID**, not PASS.
8. Material changes to the tested agent, model, policy, tools, permissions, control, environment, OWASP mapping, or corpus SHOULD trigger retesting where they can affect the result.

## 8. Framework-Agnostic Architecture

> **Threat frameworks are pluggable inputs to Proof Protocol. Proof Protocol is framework-agnostic.**

External frameworks can identify **what to test**: threats, vulnerabilities, risk categories, controls, design assertions, identity claims, tool permissions, or other risk conditions. Proof Protocol independently establishes **whether the control worked and what evidence proves that result**.

No external framework is required for Proof Protocol to operate. A Proof Protocol implementation MAY use the OWASP Top 10 for Agentic Applications, MITRE ATLAS, NIST AI 100-2, MAESTRO, AIVSS, a proprietary threat model, another recognized framework, or no external framework at all when the test condition is otherwise sufficiently defined.

Adding, replacing, muting, or removing a framework mapping does not alter the Proof Protocol architecture, evidence model, Proof of Efficacy determination, ProofBundle™, ProofStamp™, ProofRegister™, or independent corroboration requirements.

A framework mapping therefore establishes **interoperability**, not architectural dependency.

## 9. Relationship to Proof Protocol

This mapping is part of the Proof Protocol specification family maintained by Nebulonium, Inc.

The relationship is intentionally asymmetric:

> **OWASP supplies agentic-application risk context. Proof Protocol supplies the evidence model for determining whether a selected defensive control performed as claimed.**

No affiliation, endorsement, certification, or sponsorship by OWASP is implied.

## 10. Source Framework, Attribution, and License

The OWASP Top 10 for Agentic Applications is external OWASP work. OWASP names, risk identifiers, trademarks, and expressive framework content remain subject to OWASP's applicable terms.

OWASP GenAI Security Project materials are generally published under Creative Commons terms; the applicable license for the exact upstream artifact/version SHOULD be verified at its authoritative source before substantial reuse.

This Proof Protocol mapping is independently authored and licensed under **CC BY 4.0**. It references OWASP identifiers and concepts for interoperability and does not relicense OWASP material.

## 11. Versioning

This mapping is versioned independently of the OWASP Top 10 for Agentic Applications. Material upstream changes SHOULD trigger a mapping review and, where necessary, a new version identifying the OWASP revision mapped.

---

*Proof Protocol · proofprotocol.io · CC BY 4.0*
