# Specification — Library Reservation System

## 1. System Intent
The purpose of this specification is to describe the internal interactions of the use case **UC-01: Reserve a Book Copy** using UML sequence diagrams.

## 2. Use Case
**UC-01: Reserve a Book Copy**

**Primary Actor:** Reader

**Preconditions:**
- The reader is registered in the library system.
- The reader can access the library catalog.

## 3. Scenarios

### SC-01: Successful reservation
1. Reader selects an available book copy.
2. Reader submits a reservation request.
3. The system validates the request.
4. The system creates a reservation linked to the reader and book copy.
5. The system confirms successful reservation.

### SC-02: No available book copies
1. Reader selects a book that has no available copies.
2. Reader submits a reservation request.
3. The system checks book copy availability.
4. The system informs the reader that no copies are available.
5. No reservation is created.

### SC-03: Selected book copy is already reserved
1. Reader selects a book copy.
2. Reader submits a reservation request.
3. The system checks the selected copy status.
4. The system detects that the copy is already reserved.
5. The system rejects the request and informs the reader.
6. No new reservation is created.

## 4. Participants
- **Reader** — initiates the reservation request.
- **ReservationUI** — receives user input and displays results.
- **ReservationService** — processes and validates reservation requests.
- **BookCopy** — represents a physical book copy and its status.
- **Reservation** — represents a reservation record.

## 5. Modeling Rules
- Each scenario must have a separate sequence diagram.
- Diagrams must show actors, participants, messages, return messages, and activation bars.
- Each diagram must contain at least one combined fragment (`alt`, `opt`, or `loop`).
- Participants and interactions must be consistent with the Lab 1 data model and Lab 2 Gherkin scenarios.