# DEFENSE — Library Sequence Diagrams

## 1. Intent
The purpose of this project is to describe the internal interactions of the use case UC-01: Reserve a Book Copy through UML sequence diagrams.

## 2. Implemented Scenarios
Three scenarios from Lab 2 were detailed:
- SC-01: Successful reservation.
- SC-02: No available book copies.
- SC-03: Selected book copy is already reserved.

## 3. Modeling
Each scenario has a separate Mermaid sequence diagram in both source (`.mmd`) and rendered (`.png`) formats.

The diagrams include:
- Actor and system participants.
- Requests, responses, and return messages.
- Activation bars.
- `alt` combined fragments for alternative outcomes.

## 4. Consistency and Audit
The diagrams were reviewed against the Lab 1 ER model and Lab 2 Gherkin scenarios.

The audit identifies three areas of consistency:
1. Participants correspond to system components and data entities.
2. Interaction steps match the selected use case scenarios.
3. Alternative outcomes are represented using `alt` fragments.

## 5. AI Usage
AI was used as an assistance tool for reviewing the structure of the sequence diagrams and identifying possible inconsistencies. The student reviewed and selected the final modeling decisions.

## 6. Conclusion
The project provides detailed interaction flows for all three reservation scenarios and demonstrates how the system processes successful and unsuccessful reservation requests.
