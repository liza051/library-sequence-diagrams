# Specification — Library Reservation System

## 1. System Intent

This specification describes the interactions involved in the use case **UC-01: Reserve a Book Copy**. It defines the successful reservation process and the situations in which a reservation request must be rejected.

## 2. Use Case

**UC-01: Reserve a Book Copy**

**Primary Actor:** Reader

**Preconditions:**
- The reader is registered in the library system.
- The reader can access the library catalog.

## 3. Scenarios

### SC-01: Successful reservation

1. The reader selects an available book copy.
2. The reader submits a reservation request for the selected copy.
3. The ReservationService validates the request.
4. The system checks whether the selected book copy is available.
5. The system creates a Reservation linked to the reader and the selected book copy.
6. The new Reservation receives the status `Active`.
7. The system confirms the successful reservation to the reader.

### SC-02: No available book copies

1. The reader selects a book from the catalog.
2. The reader submits a reservation request for that book.
3. The ReservationService checks the availability of the physical copies associated with the selected book.
4. The system determines that no copies are available.
5. The system rejects the request and informs the reader that no copies are available.
6. No Reservation record is created.

### SC-03: Selected book copy is already reserved

1. The reader selects a book copy.
2. The reader submits a reservation request for the selected copy.
3. The ReservationService checks whether an active Reservation exists for that copy.
4. The system detects an existing active Reservation.
5. The system rejects the request and informs the reader that the copy is already reserved.
6. No new Reservation record is created.

## 4. Participants

- **Reader** — initiates the reservation request.
- **ReservationUI** — receives the reader's input and displays the result.
- **ReservationService** — validates requests, checks availability, and processes reservations.
- **BookCopy** — represents an individual physical book copy and its availability.
- **Reservation** — represents a reservation record linked to a reader and a book copy.

## 5. Modeling Rules

- Each scenario must have a separate UML sequence diagram.
- Diagrams must show the actor, relevant participants, messages, return messages, and activation bars.
- Combined fragments must represent actual interaction behavior. Use `alt` for real alternatives, `opt` for optional behavior, `loop` for repetition, and `break` for early termination.
- Do not include unreachable or contradictory alternative branches.
- In SC-02, availability is checked across the copies of the selected book. A single BookCopy must not be asked to check all copies using a book identifier.
- In SC-03, an existing reservation must be checked through the Reservation record, not through the BookCopy status.
- A newly created reservation must have status `Active`.
- Participants and interactions must remain consistent with the Lab 1 data model and Lab 2 Gherkin scenarios.