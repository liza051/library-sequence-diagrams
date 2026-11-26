# AI Work Log

## 1. Purpose

AI was used as an assistant during the preparation, review, and correction of the UML sequence diagrams for UC-01: Reserve a Book Copy.

The student reviewed AI suggestions and made the final modeling decisions.

## 2. AI Interaction Records

### Interaction 1: Reviewing sequence diagram scenarios

**Prompt (Student):**

"Review the three sequence diagrams and identify inconsistencies with the instructor's feedback."

**AI Response:**

The review identified unreachable `alt` branches, missing request validation in SC-01, an incorrect availability check using `bookId` in SC-02, and incorrect use of the BookCopy status in SC-03.

**Student Critique:**

I agreed that the alternative branches were contradictory and needed correction. I also agreed that SC-03 should check an active Reservation record instead of relying on the BookCopy status.

### Interaction 2: Correcting SC-01

**Prompt (Student):**

"Check SC-01 against the instructor's comments."

**AI Response:**

The diagram should show the registered-reader precondition, request validation, and creation of a reservation with status `Active`.

**Student Critique:**

I accepted these corrections because they make the successful reservation scenario consistent with the specification.

### Interaction 3: Correcting SC-02

**Prompt (Student):**

"Correct the availability check in SC-02."

**AI Response:**

The original call `checkAvailability(bookId)` was incorrect when sent to a single BookCopy. The diagram was revised to check individual physical copies using `copyId` and to use a `loop` for repeated checks. A `break` fragment represents rejection when no copies are available.

**Student Critique:**

I accepted the correction because a single physical copy cannot determine the availability of all copies of a book. I also checked that the rejection message is displayed to the reader.

### Interaction 4: Correcting SC-03

**Prompt (Student):**

"Check SC-03 and correct the handling of an already reserved book copy."

**AI Response:**

The diagram should use `findActiveReservation(copyId)` and receive `activeReservationExists` from the Reservation participant. The request should be rejected using a `break` fragment, without creating another reservation.

**Student Critique:**

I accepted this approach because reservation information belongs to the Reservation record. I checked that no new reservation is created in this scenario.

### Interaction 5: Reviewing the audit

**Prompt (Student):**

"Review the sequence diagrams audit and correct the discrepancies according to the instructor's comments."

**AI Response:**

The audit should identify actual modeling problems rather than repeat general requirements. It should describe the incorrect availability check, the incorrect reservation status handling, and unreachable alternative branches.

**Student Critique:**

I agreed that the original audit did not identify real discrepancies. I accepted the revised audit because it describes specific problems and the corrections made.

## 3. Student Decisions

I reviewed the AI suggestions, compared them with the instructor's feedback and the available Lab 1 data model, and decided which corrections to apply.

I retained separate diagrams for all three scenarios and checked their rendered versions. I also decided not to introduce additional participants or changes that were not required by the instructor's comments.

## 4. Limitations

AI suggestions were treated as recommendations, not as automatically correct solutions.

The student remained responsible for reviewing the diagrams, checking their consistency, and making the final modeling decisions.

The final review must be based on the project specification, the Lab 1 data model, the Lab 2 scenarios, and the instructor's feedback.