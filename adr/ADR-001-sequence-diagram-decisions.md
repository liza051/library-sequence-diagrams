# ADR-001: Sequence Diagram Modeling Decisions

## Status
Accepted

## Context
The Library Reservation System requires separate UML sequence diagrams for the three scenarios of UC-01: Reserve a Book Copy. The diagrams must be consistent with the Lab 1 data model, the UC-01 specification, and the instructor's feedback.

## Decision 1: Separate diagrams for each scenario
I decided to create a separate sequence diagram for each scenario:
- SC-01: Successful reservation.
- SC-02: No available book copies.
- SC-03: Selected book copy is already reserved.

This keeps each interaction flow focused on one specific outcome.

## Decision 2: Use of combined fragments
I decided to use combined fragments according to their actual behavior:
- `loop` represents repeated availability checks in SC-02.
- `break` represents early termination when a reservation request is rejected.
- Unreachable or contradictory `alt` branches are not used.

## Decision 3: Checking active reservations
I decided that SC-03 checks for an active Reservation record using `findActiveReservation(copyId)`. The system does not rely on the BookCopy status to determine whether an active reservation exists.

## Consequences
The diagrams represent the three scenarios separately and use interactions that reflect the responsibilities of the modeled participants. These decisions help maintain consistency with the specification