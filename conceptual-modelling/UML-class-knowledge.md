# UML Class Diagram Knowledge

## Purpose and applicability

This component provides declarative knowledge about **Unified Modeling Language (UML) class diagrams** for Enterprise Modeling Studio. It centralises definitions, semantic distinctions, modelling rules, and conventions shared by verification and validation.

The selected task component determines which assessment is performed and which evidence is admissible. Including this knowledge does not by itself request verification or validation. The shared role component determines the coaching approach, and the selected feedback-mode component determines presentation and interaction.

The primary scope is **conceptual domain modelling**: classes, attributes, data types, associations, role names, multiplicities, generalization, association classes, aggregation, composition, and constraints. Operations, visibility, navigability, dependencies, and packages are included as supporting concepts. Implementation details and advanced UML constructs are not mandatory unless the task requires them.

The semantic baseline is [OMG UML 2.5.1](https://www.omg.org/spec/UML/2.5.1), particularly Clauses 7, 9, 10, and 11. This component is a teaching profile, not a reproduction of the full specification.

### Status of the statements

- **Definitions** specify the meanings of constructs.
- **Rules** specify required semantic or structural conditions within their stated scope.
- **Conventions** guide clarity, consistency, and abstraction. A departure is not automatically a formal UML error.
- **Examples** illustrate meanings without imposing requirements on another model.

Explicit course rules or a supplied notation may establish additional requirements or a simplified profile. Such requirements remain distinguishable from general UML rules. Case-specific concepts, business rules, and completeness requirements come from the supplied material; they are not supplied by the examples in this component.

## Domain models, diagrams, and scope

**Definition.** A conceptual class model describes relevant kinds of things in a domain, their properties, their relationships, and constraints on possible instances. A class diagram presents a view of that model.

A diagram may be partial. Omitted features, relationships, or classes are not necessarily absent from the underlying model. Several diagrams may present different views of the same elements.

**Distinctions.**

- A conceptual model describes domain meaning, such as customers, contracts, and deliveries.
- A software design model may additionally describe implementation responsibilities, interfaces, operations, and technical dependencies.
- A database schema describes storage structures. Tables, foreign keys, and database identifiers are not mandatory elements of a conceptual UML class model.

**Conventions.** The subject, abstraction level, and relevant time perspective are identifiable. Current relationships, historical records, planned arrangements, and temporary states may require different constraints. A class diagram expresses structural possibilities; it does not, by itself, prescribe a business process or the order of activities.

## Classes and instances

**Definition.** A **class** characterises a set of objects with common features and constraints. An **object** is a particular instance. Classes may represent physical things, people, organizations, agreements, transactions, occurrences, or other relevant domain concepts.

**Rules.**

- A class has a coherent interpretation of what counts as one instance.
- Its declared properties and constraints apply to its instances, including instances of its subclasses where inherited.
- A class and an individual instance remain distinguishable. `Customer` may be a class; a particular customer is an instance.

Two objects may have identical attribute values while remaining distinct objects. An identifying attribute is not what creates UML object identity.

**Conventions.** Class names normally use singular nouns or noun phrases, such as `Customer`, `PurchaseOrder`, and `RentalAgreement`. Naming style and capitalization are conventions. Similar names do not prove that two classes are duplicates; different names do not prove different meanings.

A class need not display attributes or operations to be meaningful. It need not have an explicit identifier unless domain identification or the task requires one. Where identifiers matter, their uniqueness scope is clear: a line number may identify a line only within its order.

**Example.** `Payment` can be a class representing individual payment occurrences. A rule that classes must represent only tangible objects would exclude valid conceptual models.

## Attributes, data types, and enumerations

**Definition.** An **attribute** is a property of a class whose values describe its instances. Its type determines the permitted kind of value, and its multiplicity determines the permitted number of values.

Typical attribute notation is `name: Type [multiplicity]`, for example `emailAddress: String [0..1]`. Additional modifiers may express derivation, read-only status, or other properties.

A **data type** represents values rather than objects distinguished by identity. UML primitive types include `Boolean`, `Integer`, `Real`, and `String`. Types such as `Date` and `Money` may be defined or imported for the domain; their names alone do not establish their detailed semantics.

An **enumeration** defines named literals for a type. For example, `OrderStatus` may have the literals `draft`, `confirmed`, and `cancelled`. A new domain object such as a newly registered customer is not normally an enumeration literal.

**Rules.**

- Attribute values conform to the declared type, multiplicity, and constraints.
- Units, currency, precision, and permitted ranges are specified where needed to determine meaning.
- A derived attribute denotes a value determined from other information. Its derivation is compatible with that information and with other constraints.

**Examples.** `/totalAmount: Money` can denote a derived order total. `quantity: Integer` does not by itself state that quantity is positive; that requires a constraint such as `{quantity > 0}`.

**Conventions.** Attributes describe values at an appropriate level of detail. An independently identifiable entity with its own relevant relationships is often clearer as a class connected by an association. However, a class-typed attribute is valid UML; the choice is not governed by a universal prohibition.

Repeating the same fact as both an attribute and a relationship can create ambiguity. Such representations need an explicit correspondence or derivation when both are retained. A foreign-key attribute is not required alongside an association in a conceptual model.

## Associations, links, and role names

**Definition.** An **association** specifies a relationship between instances of its participating types. A **link** is a particular instance of an association. This profile primarily uses binary associations between two classes.

An **association-end name**, often called a **role name**, identifies the role played by instances at that end. An association name describes the relationship as a whole.

**Rules.**

- The relationship has an identifiable meaning between instances of the connected classes.
- End labels, multiplicities, and other adornments attach unambiguously to the intended ends.
- Different associations between the same classes remain distinguishable where they express different relationships.

**Example.** `Person` may have both an `employer` and a `serviceProvider` association to `Organization`. Sharing the same endpoint classes does not make these associations redundant.

**Reflexive associations.** A class may be associated with itself. A `Person`–`Person` association with roles `parent` and `child` relates different roles played by person instances. Reflexivity does not mean that an object must relate to itself. Restrictions such as “a person cannot be their own parent” require an appropriate constraint.

**Conventions.** Names and roles support an understandable reading in both directions. An association need not have both a central name and two role names if its meaning is already clear, unless the task requires them.

An association is not a message, process sequence, or causal arrow. The visual position of classes does not establish direction, timing, responsibility, or ownership.

## Multiplicity

**Definition.** A multiplicity specifies lower and upper bounds on the number of permitted values or related instances. In a binary association, the multiplicity next to one class is read for **one fixed instance of the opposite class**.

| Multiplicity | Meaning |
|---|---|
| `1` or `1..1` | Exactly one. |
| `0..1` | Zero or one. |
| `*` or `0..*` | Zero or more, with no finite upper bound specified. |
| `1..*` | One or more, with no finite upper bound specified. |
| `m..n` | At least `m` and at most `n`, inclusive. |

**Example.** In a `Customer`–`Order` association, `1` next to `Customer` and `0..*` next to `Order` mean:

- Every order is associated with exactly one customer.
- Every customer is associated with zero or more orders.

The bounds are not reversed. They do not state the total number of customers or orders in the business.

**Rules.**

- A lower bound is a non-negative integer. A finite upper bound is at least the lower bound; `*` denotes an unlimited upper bound.
- A lower bound of zero permits absence; a positive lower bound requires participation in every state covered by the constraint.
- Bounds and other constraints must be jointly consistent for the instances the model is intended to permit.
- Multiplicity alone does not express ordering, eventual participation, duration, or a sequence of changes.

An upper bound of `1` does not prohibit replacing one related object with another over time. If a rule means “at most one active contract at a time,” a relationship containing all historical contracts needs additional temporal or status conditions.

**Omitted information.** A multiplicity not displayed at an association end does not establish `1`; UML permits multiplicities to be suppressed in a diagram. This differs from defaults in a fully specified UML model and shorthand in attribute notation. An explicit teaching convention may require all multiplicities to be visible or define how shorthand is read. Without that convention, missing display information remains unresolved. [OMG UML 2.5.1, Sections 9.5.4 and 11.5.4](https://www.omg.org/spec/UML/2.5.1/PDF).

**Convention.** Multiplicities are explicit where they communicate important business rules. Numeric bounds require support from the case or an identified modelling assumption; typical business practice is not sufficient evidence.

## Generalization and specialization

**Definition.** **Generalization** relates a more specific class, the subclass, to a more general class, the superclass. Every instance of the subclass is also an instance of the superclass. The subclass inherits applicable features and constraints.

**Rules.**

- Generalization expresses a genuine “is a kind of” relationship.
- A subclass is compatible with inherited meaning and constraints. Specialization does not make a superclass requirement optional.
- A generalization hierarchy has no directed cycle: a class cannot be its own ancestor.

**Examples.** `Employee` may specialize `Person`. `Department` is not a subclass of `Organization` merely because a department belongs to an organization; membership and specialization express different claims.

Multiple inheritance is permitted in UML. It requires a coherent interpretation of inherited features and constraints; it is not automatically a modelling error.

**Abstract classes.** An abstract class cannot have direct instances, although objects may instantiate its concrete subclasses. Its name is normally italicized or marked `{abstract}`. An abstract superclass does not, by itself, declare that every possible subclass is displayed.

### Generalization sets

A **generalization set** groups specializations of the same superclass and can constrain coverage and overlap.

| Constraint | Interpretation |
|---|---|
| `{disjoint}` | An instance cannot belong to more than one subclass in the set. |
| `{overlapping}` | Membership in more than one subclass in the set is permitted. |
| `{complete}` | Every instance of the superclass belongs to at least one subclass in the set. |
| `{incomplete}` | The set does not require all superclass instances to be covered by its subclasses. |

Coverage and overlap are separate dimensions. `{complete, disjoint}` means exactly one subclass in the set for each superclass instance. The constraints apply to that set, not automatically to every subclass of the superclass.

**Example.** `Student` and `Employee` may be overlapping specializations of `Person`: one person may be both. They may be incomplete because other persons are neither.

**Convention.** Coverage and overlap are stated when they matter. Two subclass boxes placed side by side do not establish an exhaustive, disjoint partition.

## Aggregation and composition

**Definition.** Aggregation and composition are forms of whole–part association. Neither is a substitute for generalization. A diamond is drawn at the **whole end** of the association.

**Rule.** UML aggregation and composition apply to binary associations, with an aggregation or composition adornment at only one end.

### Shared aggregation

**Shared aggregation**, shown with a hollow diamond, indicates a grouping or whole–part interpretation. UML does not give it one precise lifecycle meaning applicable to every domain. The intended semantics therefore depend on the modelling context. [OMG UML 2.5.1, Section 9.5.3](https://www.omg.org/spec/UML/2.5.1/PDF).

A hollow diamond alone does not establish exclusive ownership, deletion of parts, or a particular multiplicity.

**Convention.** An ordinary association is often sufficient when no useful additional whole–part meaning is defined. Shared aggregation is used where its interpretation is explained or established by the course notation.

### Composition

**Composition**, shown with a filled diamond, expresses stronger ownership of parts.

**Rules.**

- A part object belongs to at most one composite whole object at a time.
- Deleting a composite object deletes its part objects that remain included in that composition.
- A part may be detached before deletion of the whole where other constraints permit this. Composition does not impose a universal ban on independent existence at every stage of a part's lifetime.
- Composite containment is acyclic at the instance level: an object cannot contain itself, directly or indirectly.
- In a binary composition, the upper multiplicity at the whole end cannot exceed `1`. Whether that end is optional or mandatory is a separate constraint.

The number of parts is specified by the multiplicity at the part end, not by the diamond. Object deletion is also distinct from a business status change such as cancellation or archival unless the model explicitly equates them.

**Example.** An `Order` may compose `OrderLine` objects, while each order line refers to a `Product` through an ordinary association. Deleting the order and its lines does not thereby delete the product.

A reflexive composition, such as a folder containing subfolders, is possible at the class level. Each permitted hierarchy of folder instances must still be acyclic.

## Association classes and relationship objects

**Definition.** An **association class** has both association and class semantics. It represents a relationship that itself has features, such as attributes, operations, or associations.

**Example.** `Membership` may connect `Person` and `Club`, with attributes such as `joinedOn` and `membershipCategory`. These values describe a particular membership, not the person or club in isolation.

**Rules.**

- Features of the association class describe instances of the relationship itself.
- Its endpoint multiplicities and other constraints are consistent with that interpretation.
- Standard notation connects the class box to the association line by a dashed line. The box and association together represent one model element; the dashed line is not another business association.

UML 2.5.1 permits multiple association-class instances connecting the same endpoint objects, even when the association ends are unique. Consequently, a universal “only one relationship object per endpoint pair” rule must not be imposed without an additional constraint or an explicitly stated course restriction. [OMG UML 2.5.1, Section 11.5.3.2](https://www.omg.org/spec/UML/2.5.1/PDF).

**Alternative representation.** A relationship may instead be represented by an ordinary class with associations to its participants. For example, `Loan` can connect a `Borrower` and a `BookCopy`, while carrying borrowing and return dates. This is useful for repeated occurrences and their histories. Equivalence to an association-class representation depends on the endpoint constraints and intended identity; it is not automatic.

## Constraints and derived information

**Definition.** A **constraint** restricts valid instances or states beyond what is already expressed by the diagram's other elements. Constraints may be written in braces, attached notes, linked natural language, or a formal constraint language such as OCL.

**Rules.**

- Each constraint has an identifiable subject and scope.
- Its meaning is compatible with types, multiplicities, generalizations, and other constraints.
- A derived attribute or association has a coherent derivation where that derivation is needed to determine its meaning.
- Claims about dates, status, uniqueness, or relationships across several associations are not assumed to follow from multiplicity alone.

**Examples.** A loan's return date must not precede its borrowing date. An order total may equal the sum of its line amounts. A manager may be required to work in the department they manage. These restrictions require more than simply drawing the relevant associations.

**Convention.** Natural language is sufficient when it is precise enough for the task. OCL is not mandatory unless requested. Constraints describe required conditions; they need not specify an algorithm for enforcing them.

## Supporting UML constructs

### Operations and visibility

An **operation** specifies a callable service or behaviour associated with a class, for example `calculateTotal(): Money`. It is distinct from an attribute holding a value. An operation declaration does not, by itself, provide the implementation of that behaviour.

Visibility symbols include `+` public, `-` private, `#` protected, and `~` package. These express access visibility, not business confidentiality or authorization policy by themselves.

**Convention.** Operations and visibility are normally optional in conceptual domain models. Their absence is not a defect unless the modelling purpose or task requires them.

### Navigability and dependencies

**Navigability** concerns access to associated instances. An open arrowhead at an association end indicates navigability towards that end. A small reading-direction triangle next to an association name serves a different purpose: it tells the reader how to read the name.

A plain association line does not universally establish bidirectional navigability; a diagram may suppress navigability information. The supplied notation or legend determines its interpretation.

A **dependency**, shown as a dashed arrow from client to supplier, states that the client depends on the supplier. It is not a substitute for an association between domain instances and does not carry association-end multiplicities.

**Convention.** Navigability and dependencies are included when relevant to the modelling purpose. They do not represent process control flow.

### Packages and stereotypes

A **package** groups model elements and provides a namespace. Package containment is not a business whole–part relationship between instances.

A **stereotype** extends UML within a defined profile and may add constraints or properties. Labels such as `«entity»` require an understood profile or convention; they do not have one universal meaning in every class diagram. No particular stereotype family is mandatory in this component.

## Notation and readability

| Construct | Standard visual cue |
|---|---|
| Class | Rectangle, optionally divided into name, attribute, and operation compartments. |
| Association | Solid line between participating classes. |
| Generalization | Solid line with an unfilled triangular arrowhead pointing to the superclass. |
| Shared aggregation | Association with a hollow diamond at the whole end. |
| Composition | Association with a filled diamond at the whole end. |
| Association class | Class box connected to its association line by a dashed line. |
| Dependency | Dashed arrow pointing from client to supplier. |
| Derived property | Slash before the property name. |
| Enumeration | Classifier rectangle marked `«enumeration»`, normally listing its literals. |

**Rules.** Symbols and labels have an identifiable, consistent interpretation under the supplied notation. Distinct relationship kinds remain distinguishable.

**Conventions.** Labels are readable, connections meet the intended elements, and end labels are placed clearly. An omitted compartment does not prove that the corresponding features do not exist. Alternative layouts and declared notation simplifications are acceptable where they preserve the required distinctions.

Object diagrams depict particular instances, commonly using underlined labels such as `order17: Order`. A class diagram normally names the type itself. Mixing type-level and instance-level statements requires a clear explanation.

## Coherence and completeness

**Rules.** The model's constraints must be consistent with the instances and business situations it claims to represent. The same concept, fact, or relationship retains compatible meanings wherever it appears.

**Conventions.**

- The model uses a consistent level of abstraction, with finer detail introduced where the purpose requires it.
- Redundant representations have an explicit relationship rather than silently expressing conflicting facts.
- A path through several associations does not automatically establish an additional direct association or all its constraints.
- Cycles of ordinary associations are not automatically errors. They differ from prohibited generalization cycles and instance-level composition cycles.
- Disconnected groups of classes may be appropriate in a partial view. Connectedness alone does not determine correctness.
- Alternative valid modelling choices are interpreted through their semantics and the supplied requirements, not solely through resemblance to one reference diagram.

**Conditional completeness rule.** The model contains the concepts, relationships, properties, and constraints required by the selected task and case. This component does not require every domain noun to become a class, every class to have an identifier, every association to be navigable, or every possible UML construct to appear.

Unclear labels or suppressed details can limit interpretation without proving a specific semantic error. Whether external domain evidence may resolve such uncertainty is determined by the selected task component.

## Integrated example: confirmed customer orders

The following example models confirmed orders and their lines. It assumes that a confirmed order must have at least one line. Draft orders and their lifecycle are outside this example's scope.

| Relationship | Multiplicity at first class | Multiplicity at second class | Meaning |
|---|---|---|---|
| `Customer` — `Order` | `1` at `Customer` | `0..*` at `Order` | Each order has one customer; a customer may have any number of orders. |
| `Order` — `OrderLine` | `1` at `Order` | `1..*` at `OrderLine` | Each line belongs to one order; each order has at least one line. |
| `Product` — `OrderLine` | `1` at `Product` | `0..*` at `OrderLine` | Each line refers to one product; a product may occur on any number of lines. |

`Order` composes `OrderLine`, so the filled diamond is at `Order`. `OrderLine`–`Product` is an ordinary association.

An order line may have `quantity: Integer` and `agreedUnitPrice: Money`. Quantity is constrained to be positive. The agreed unit price describes the sale recorded on that line and need not equal the product's current listed price.

The example illustrates how classes, attributes, associations, multiplicities, composition, and constraints work together. Its assumptions are not requirements for another case.

## Reference

[Object Management Group: Unified Modeling Language, Version 2.5.1](https://www.omg.org/spec/UML/2.5.1). Relevant specification areas include multiplicity and constraints (Clause 7), generalization and properties (Clause 9), data types (Clause 10), classes and associations (Clause 11), and packages and profiles (Clause 12).
