# Sequence Diagrams Audit

## 1. Purpose
This audit checks the consistency of the sequence diagrams with the Lab 1 data model and Lab 2 requirements and scenarios.

## 2. Top 3 Discrepancies

### Discrepancy 1: Participants and data model
- **Issue:** ReservationUI and ReservationService are not entities in the ER model.
- **Correction:** They are treated as interface and service components, while BookCopy and Reservation represent data entities from the ER model.

### Discrepancy 2: Scenario consistency
- **Issue:** Each sequence diagram must reflect its corresponding Gherkin scenario.
- **Correction:** SC-01 describes successful reservation, SC-02 describes the absence of available copies, and SC-03 describes an already reserved copy.

### Discrepancy 3: Conditional behavior
- **Issue:** Alternative outcomes must be represented explicitly.
- **Correction:** Each diagram contains an `alt` fragment showing the main scenario condition and an alternative outcome.

## 3. Consistency Results
- Participants are consistent with the system architecture and ER model.
- Messages describe the steps of the selected use case.
- Each scenario has a separate sequence diagram.
- Return messages and activation bars are included.
- Each diagram contains an `alt` combined fragment.

## 4. Conclusion
The sequence diagrams provide a detailed view of the three reservation scenarios and maintain consistency with the requirements and data model from the previous laboratory assignments.