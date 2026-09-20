# UML Class Diagram Exercise: Campus Equipment Loans

## Background

A university equipment desk lends cameras, microphones, and other equipment to students. It needs a small information system that records both ongoing and completed loans.

## Business description

Each registered **student** has a unique student ID, a name, and an email address. A student may be registered without ever borrowing anything, and may have many loans over time.

Each **equipment item** is an individual physical object, such as one particular camera. It has a unique item ID and a name. An item may never have been borrowed, or may have appeared in many loans over time.

Each **staff member** has a unique staff ID and a name. A staff member may have registered no loans or many loans.

Each **loan** has a unique loan ID, a loan date, and a due date. It concerns exactly one student and exactly one equipment item, and is registered by exactly one staff member. If a student borrows two items, the desk creates two separate loan records.

When an item is returned, the actual return date is recorded on its loan. Before that, the loan has no return date. Completed loan records are retained, so the same student may borrow the same item again through a new loan record.

The due date must be on or after the loan date. If a return date is present, it must also be on or after the loan date. An item may be returned before or after its due date.

## Task

Construct a **conceptual UML class diagram** for this description.

1. Represent the four main concepts as classes and give a one-sentence definition of each class.
2. Include the stated attributes and suitable data types. Indicate which attribute is optional.
3. Include named associations and show the multiplicity at both ends of each association.
4. State the two date constraints in short notes or natural language.

Your model should make it possible to determine:

- which student borrowed which item on each loan;
- which staff member registered a particular loan;
- which loans are still ongoing and which have been completed;
- which previous loans concern a particular item.

Use ordinary associations. Operations, inheritance, aggregation, and composition are not required. Reservations, payments, reminders, and checks for overlapping loan periods are outside the scope.

## Submission

Submit the diagram, the four class definitions, and the date constraints. State any additional assumptions explicitly. A diagram drawn in a modelling tool or represented in Mermaid is acceptable.

