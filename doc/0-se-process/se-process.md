# Plan for GSCG development

## Standards for Systems and Software Engineering

The development process for the new Glocal Supply Chain Game (GSCG) implementation is primarily based on IEEE 12207 [1] for software lifecycle structure, INCOSE/ISO 15288 [2] for system-level traceability and verification processes, and RUP [3] for use case-driven functional decomposition. Additional conceptual framing was drawn from SEBoK [4], while simulation-specific architectural needs were informed by IEEE 1516 HLA standards [5].

### IEEE 12207

- Strengths: Covers all software lifecycle steps in clear process categories.
- Weakness: Less scenario-driven; no strong guidance for use cases or simulation-specific concerns.
- Best used for: Process compliance and traceability.


### INCOSE / ISO 15288

- Strengths: Complete system-level process model, strong on requirements, interfaces, and V&V.
- Weakness: More general; less helpful for software-specific modeling or simulation dynamics.
- Best used for: Engineering discipline and system context.


### SEBoK (Systems Engineering Body of Knowledge)

- Strengths: Broad, interdisciplinary guidance; focuses on conceptual consistency, role of models, and lifecycle coherence.
- Weakness: More educational than prescriptive.
- Best used for: Foundational definitions, best practices, and conceptual justification.

### References
- [1] ISO/IEC/IEEE 12207:2017. Systems and Software Engineering — Software Life Cycle Processes.
- [2] INCOSE. (2015). Systems Engineering Handbook: A Guide for System Life Cycle Processes and Activities, 4th ed.
- [3] Kruchten, P. (2003). The Rational Unified Process: An Introduction. Addison-Wesley.
- [4] Adcock, R., et al. (Eds.). (2023). Systems Engineering Body of Knowledge (SEBoK). [SEBoK Wiki](https://www.sebokwiki.org/wiki/Software_Engineering)
- [5] IEEE Std 1516-2010. IEEE Standard for Modeling and Simulation (M&S) High Level Architecture (HLA).



## Process Description

```
1. Define Scope and Stakeholders
2. Capture Use Cases and Operational Scenarios
3. Define System Requirements
   └── Functional, Non-functional, Constraints
4. Architect the System
   ├── High-level Component Breakdown, Interface definitions
   └── Conceptual Database design
5. Design Simulation Components
   ├── Function & Service Design (by use case)
   ├── Class/Object Model (if needed)
   └── Data Model (entities, interactions, timing)
6. Plan & Define Integration Architecture
   └── Time management, federation interfaces, live component links
7. Develop Components & Services
   └── In sprints or iterations, with unit tests
8. Integrate and Test (Incremental)
   ├── Component integration
   ├── Interface testing
   └── Simulation correctness
9. System Verification & Validation
   ├── Against requirements & scenarios
   └── Against stakeholder expectations
10. Final Documentation & Delivery
    └── Code, interfaces, user manuals, test results, web site
```


## Deliverables

1. **Define Scope and Stakeholders**

    - [ ] Description: Identify goals, end-users, and constraints
    - [ ] Deliverables: Project charter, stakeholder map

2. **Capture Use Cases and Operational Scenarios**

    - [ ] Description: Define simulation stories or mission threads
    - [ ] Deliverables: Use case diagrams and descriptions, high-level sequence diagrams

3. **Requirements Definition**

    - [ ] Description: Capture functional needs, performance constraints, and objectives
    - [ ] Deliverables: SRS (Software Requirements Specification) with functional constraints, non-functional constraints, functional objectives, and non-functional objectives

4. **System Architecture**

    - [ ] Description: High-level decomposition: modules, interfaces, runtime context
    - [ ] Deliverables: Architecture document, module / component diagram, conceptual database design

5. **Component & Data Design**

    - [ ] Description: Specify functional behavior and data flow; design data model
    - [ ] Deliverables: Design specifications, lower level UML (activity/class/ER) diagrams

6. **Integration Architecture**

    - [ ] Description: Define simulation framework, timing model
    - [ ] Deliverables: Interface control document, time & event coordination

7. **Development**

    - [ ] Description: Code the simulation components per function
    - [ ] Deliverables: Source code, unit test cases

8. **Integration & Testing**

    - [ ] Description: Combine modules; test against use cases and interfaces
    - [ ] Deliverables: Test reports, simulation logs

9. **Verification and Validation**

    - [ ] Description: Validate against requirements and real-world expectations
    - [ ] Deliverables: Validation report, traceability matrix

10. **Documentation and Delivery**

    - [ ] Description: Final packaging of code, manuals, test evidence
    - [ ] Deliverables: User manual, API reference, release package, web site


## Relation between above Steps and SE Standards

| Step | IEEE 12207 | INCOSE / ISO 15288 | SEBoK |
| ---- | ---------- | ------------------ | ----- |
| 1. Define Scope & Stakeholders | Organizational Processes (Project Management), Acquisition | Stakeholder Requirements Definition (SRD) |  Stakeholder & Business Context |
| 2. Capture Use Cases & Scenarios | Software Requirements (User Requirements) | Stakeholder Needs & Requirements | Concept Definition, Operational Scenarios |
| 3. Define System Requirements | Software Requirements Process | System Requirements Definition (SRD) | Requirements Engineering |
| 4. Architect the System | Architectural Design Process | Architecture Definition | Logical/Physical Architecture |
| 5. Design Simulation Components | Detailed Design Process | Design Definition | Design Engineering |
| 6. Plan Integration Architecture | Interface & Integration Planning | Integration Definition & Planning | Systems Integration Strategy |
| 7. Develop Components & Services | Software Construction | Implementation Process | Software Construction & Implementation |
| 8. Integrate and Test (Incremental) | Integration & Software Testing | Integration Process, Verification | V&V Planning & Execution |
| 9. System Verification & Validation | Software Verification & Validation | Verification & Validation | Independent V&V |
| 10. Final Documentation & Delivery | Documentation Process | Transition / Transition to Operations | Product Support, Configuration Management |
