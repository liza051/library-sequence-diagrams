# Sequence Diagrams Audit

## 1. Purpose

This audit evaluates the consistency of the UML sequence diagrams with the Lab 1 data model, Lab 2 Gherkin scenarios, and the UC-01 specification. It identifies the main discrepancies found during the review and documents the corrections made.

## 2. Top 3 Discrepancies

### Discrepancy 1: Incorrect availability check in SC-02

- **Issue:** The original SC-02 diagram used `checkAvailability(bookId)` on a single `BookCopy` participant. This was incorrect because one physical copy cannot check the availability of all copies belonging to a book.
- **Correction:** The interaction was revised to check individual physical copies using `copyId`. A `loop` fragment represents checking the copies of the selected book. A `break` fragment represents early termination when no available copies are found.
- **Result:** The diagram now distinguishes the book identifier from individual copy identifiers.

### Discrepancy 2: Incorrect reservation status handling in SC-03

- **Issue:** The original SC-03 diagram checked whether the `BookCopy` status was `reserved`. However, an existing reservation must be represented by an active `Reservation` record, not by changing the status of the physical copy.
- **Correction:** The diagram now uses `findActiveReservation(copyId)` and receives `activeReservationExists` from the `Reservation` participant. The request is rejected using a `break` fragment, and no new reservation is created.
- **Result:** The interaction is consistent with the reservation-record responsibility.

### Discrepancy 3: Unreachable alternative branches and missing request validation in SC-01

- **Issue:** The original diagrams contained alternative branches that contradicted results already established by previous messages. In addition, SC-01 did not explicitly show request validation or the required `Active` reservation status.
- **Correction:** Unreachable `alt` branches were removed. SC-01 now includes `validateReservationRequest(readerId, copyId)` and creates a reservation with status `Active`. SC-02 and SC-03 use `break` fragments to represent early rejection.
- **Result:** Each diagram represents one specific scenario without contradictory alternative outcomes.

## 3. Consistency Results

- Each scenario is represented by a separate sequence diagram.
- The participants distinguish interface and service components from data entities.
- SC-01 shows request validation and creation of an active reservation.
- SC-02 checks physical copies individually rather than asking one copy to check all copies by book identifier.
- SC-03 checks for an active Reservation record.
- Combined fragments represent the modeled interaction behavior rather than unreachable alternatives.
- Return messages and activation bars are included.

## 4. Conclusion

The review identified three discrepancies between the original sequence diagrams and the requirements. The diagrams were revised to address these issues. The updated models provide clearer scenario-specific interactions and improve consistency with the specification and the data model.

The updated sequence diagrams were reviewed against the available Lab 1 data model and the requirements documented in the UC-01 specification.