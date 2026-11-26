# DEFENSE — Library Sequence Diagrams

## 1. Intent

I created UML sequence diagrams to describe the internal interactions of the use case **UC-01: Reserve a Book Copy**. My goal was to represent the successful reservation process and two rejection scenarios.

## 2. Implemented Scenarios

I modeled three scenarios:

- **SC-01:** Successful reservation.
- **SC-02:** No available book copies.
- **SC-03:** Selected book copy is already reserved.

I created a separate sequence diagram for each scenario.

## 3. Modeling

I used Mermaid sequence diagrams and provided source (`.mmd`) and rendered (`.png`) files.

Each diagram includes:
- An actor and relevant system participants.
- Requests, responses, and return messages.
- Activation bars.
- Combined fragments where they represent actual interaction behavior.

I used a `loop` fragment in SC-02 to represent repeated availability checks and `break` fragments to represent early termination when a reservation request is rejected.

## 4. Consistency and Audit

I reviewed the diagrams against the available Lab 1 ER model, the UC-01 specification, and the instructor's feedback.

During the review, I identified and corrected three main discrepancies:

1. **SC-02 availability check:** I corrected the use of `bookId` when checking an individual BookCopy and used `copyId` for individual physical copies.
2. **SC-03 reservation status:** I changed the interaction to check for an active Reservation record instead of relying on the BookCopy status.
3. **Scenario logic and validation:** I removed unreachable alternative branches, added request validation to SC-01, and specified the `Active` status when creating a reservation.

I documented these discrepancies and corrections in `audit/sequence-audit.md`.

## 5. AI Usage

I used AI as an assistance tool to review the sequence diagrams, identify inconsistencies, and suggest corrections.

I reviewed the suggestions, compared them with the instructor's comments, and made the final modeling decisions myself. I documented the AI interactions and my evaluation in the AI work log.

## 6. Conclusion

I revised the sequence diagrams to address the instructor's feedback. The updated diagrams describe the three reservation scenarios and show the interactions involved in successful and rejected reservation requests.

I also documented the identified discrepancies, corrections, and my modeling decisions.
