---
title: UML & BPMN Diagram Portfolio
---

# Diagram Portfolio - UML & BPMN

**Purpose:** a small, honest demonstration that I have studied UML and BPMN notation in depth and can apply it correctly to a real-shaped requirements problem. not a claim of years of production modeling experience.

Most of my requirements engineering work (Bosch, Volkswagen, Stellantis, Porsche) used structured text requirements, DOORS/Polarion traceability, and ASPICE work products rather than formal UML/BPMN artifacts as the primary deliverable. This folder is where I closed that gap deliberately: I studied the notations, then built a connected set of diagrams, modeled in Lucidchart, checked against UML 2.5 / BPMN 2.0 notation rules (against one realistic scenario to prove I can actually use them not just recognize the shapes).

## The scenario

All four diagrams model the same synthetic system: an **Appointment Booking System** for a generic clinic (patient books a slot with a provider, gets a confirmation, can reschedule or cancel). It's domain-neutral by design: no employer data, no automotive-specific context so any reviewer can follow it without insider knowledge, and it doubles as a compact requirements-elicitation exercise: actors, behaviors, data, interactions, and process flow all had to stay consistent with each other across four different diagram types.

## What's here

| Diagram | Type | What it shows |
|---|---|---|
| [`01-use-case-diagram`](01-use-case-diagram/) | UML Use Case | Actors, system boundary, `<<include>>`/`<<extend>>` relationships |
| [`02-class-diagram`](02-class-diagram/) | UML Class | Domain model: entities, attributes, operations, multiplicities |
| [`03-sequence-diagram`](03-sequence-diagram/) | UML Sequence | Runtime interaction for the booking flow, including an `alt` fragment |
| [`04-bpmn-process`](04-bpmn-process/) | BPMN 2.0 | End-to-end process across swimlanes (Patient / Booking System / Provider) |

Each subfolder has its own README explaining the notation choices behind that diagram and, where relevant, where I'd push back or dig deeper if this were in a real project.

## Honesty note

These diagrams were modeled by me in Lucidchart, with AI assistance for defining the underlying logic (actors, relationships, message sequences, process flow) and for reviewing each diagram against UML/BPMN notation rules once built. I made the actual modeling decisions and drew every diagram myself, the AI's role was scoping the logic up front and catching notation errors afterward, not producing the artifact.
