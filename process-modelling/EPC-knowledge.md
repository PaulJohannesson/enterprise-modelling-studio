# EPC Knowledge

## Purpose and applicability

This component provides declarative knowledge about **Event-driven Process Chains (EPCs)** as used for process modelling in Enterprise Modeling Studio. It centralises the definitions, semantic distinctions, modelling rules, and conventions shared by verification and validation.

The selected task component determines which assessment is performed and which evidence is admissible. Including this knowledge does not by itself request verification or validation. The shared role component determines the coaching approach, and the selected feedback-mode component determines presentation and interaction.

The scope is **events, functions, organizational units, logical connectors (AND, OR, and XOR), control flow, and organizational assignments**. Organizational units belong to the extended EPC (eEPC) tradition; this component uses **EPC** for the teaching profile that includes them. Additional constructs, such as information objects, application systems, and process interfaces, are not mandatory unless the supplied notation or task requires them.

### Status of the statements

- **Definitions** specify the meanings of constructs in this profile.
- **Rules** specify required semantic or structural conditions within their stated scope.
- **Conventions** guide clarity, consistency, and appropriate abstraction. A departure requires interpretation in context and is not automatically a formal rule violation.
- **Examples** illustrate meanings without imposing requirements on another model.

The rules below establish a conventional EPC teaching profile. Explicitly supplied course rules or notation may establish a different profile, which must be identified when interpreting the model. Case-specific activities, responsibilities, conditions, and completeness requirements come from the submitted material; they are not supplied by the examples in this component.

## Processes and process instances

**Definition.** A business process is an organised set of activities directed towards an identifiable business result. An EPC represents the conditions under which activities occur, their possible ordering, and the states reached as the process progresses. EPC is an established process-modelling notation within ARIS. [ARIS: Event-driven process chain](https://ariscommunity.com/event-driven-process-chain).

A **process instance** is one particular execution of the process, such as the handling of one customer order. Branch selection, synchronization, and completion are interpreted for the relevant instance. Two mutually exclusive outcomes may occur in different instances without contradicting each other.

**Convention.** The model's scope makes clear what is being handled, where the process begins, and which results count as completion. Whether it describes an existing or proposed process is identifiable when this matters.

## Events

**Definition.** An event represents a relevant state or occurrence that enables subsequent work or describes an outcome of preceding work. Events are passive: they do not themselves perform activities or make decisions.

**Rules.**

- An event expresses something that has happened or a condition that holds at the relevant point in an instance.
- Its meaning remains distinguishable from the work required to establish, discover, or respond to that condition.
- A preceding function and its outcome events have a coherent interpretation; an enabling event is relevant to the following function.

**Examples.** **Registration request received**, **Identity verified**, and **Registration rejected** are events. **Verify identity** is a function. **Identity** alone names a subject without identifying a state or occurrence.

An outcome need not be a physical change. **Check subscription status** may establish that **Subscription is active**; the checking activity need not have activated the subscription.

**Conventions.** Event labels normally combine an identifiable subject with a state or completed occurrence. Labels such as **Done** or **Ready** need enough context to establish what is done or ready. An event describes a condition, not the duration of waiting for it.

## Functions

**Definition.** A function represents work performed in the process: an activity that transforms something, produces a result, evaluates information, or establishes a decision.

**Rules.**

- A function identifies meaningful work, rather than only a condition, organizational unit, object, or connector operation.
- Its enabling conditions and possible outcomes are semantically compatible with that work.
- Any evaluation needed to distinguish alternative outcomes is identifiable in the function or an explicitly documented preceding activity.

**Examples.** **Verify identity**, **Create user account**, and **Notify applicant of rejection** identify functions. **Account created** identifies an outcome. **Accounts Department** identifies an organizational unit.

**Conventions.** Function labels normally use an action verb and an object, such as **Review registration request**. A function expresses one coherent activity at the selected level of detail. **Process request** may be adequate in an overview but insufficient where the task requires the review, decision, and notification steps separately.

Functions may be performed manually, automatically, or through combined human and system activity. A separate function called **Make decision** is unnecessary when another function, such as **Assess eligibility**, already includes that decision.

## Organizational units and assignments

**Definition.** An organizational unit is an identifiable part of an organization, such as a department, division, or team. An **organizational assignment** connects a unit to a function and specifies its responsibility for, or participation in, that work.

Extended EPCs distinguish organizational units from other organizational elements, including roles and positions, and can distinguish carrying out work from deciding, supporting, consulting, or receiving information. These distinctions must follow the supplied notation. [ARIS: EPC in ARIS, organizational elements and connections](https://ariscommunity.com/system/files/cs-aris-epc-en-24.pdf).

**Rules.**

- A unit identifies an organizational entity; its label does not merely repeat an activity or outcome.
- An assignment connects the unit to the relevant function and has an identifiable meaning.
- Organizational assignments remain distinguishable from control-flow connections. A unit is not a step between an event and a function.
- Several assignments to the same function preserve the distinction between their responsibilities where those responsibilities differ.

**Examples.** **Student Services** may carry out **Review registration request**, while **Admissions Committee** decides on **Assess exceptional admission**. The two units do not become sequential process steps merely because both appear in the model.

One unit may participate in several functions. Several units may participate in one function. Neither situation is automatically erroneous. An unlabeled assignment can be sufficient if the legend establishes its meaning; it does not automatically express every possible responsibility.

**Conventions.** Responsibilities are visible where needed to understand who performs or oversees the work. **Admissions officer** normally identifies a role or position; treating it as an organizational unit requires an explicitly simplified notation. A software application is not an organizational unit merely because it executes a function.

**Conditional completeness rule.** Every function must have the assignments required by the applicable task or course rules. This component does not impose exactly one unit per function or require a complete organizational hierarchy.

## Control flow and structural rules

**Definition.** A control-flow connection is a directed relationship indicating possible progression between events, functions, and connectors. It expresses ordering or logical dependency, rather than organizational responsibility or data transfer.

**Rules for a complete EPC in this profile.**

1. The process has at least one start event and at least one end event.
2. A start event has no incoming control flow and one outgoing flow. An end event has one incoming flow and no outgoing flow. An intermediate event has one incoming and one outgoing flow.
3. Each function has exactly one incoming and one outgoing control-flow connection. Organizational assignments do not count towards these numbers.
4. Events and functions alternate along each path, allowing connectors between them. Direct event-to-event and function-to-function connections are invalid; inserting a connector does not remove the alternation requirement.
5. Branching and merging use explicit connectors. Several arrows into or out of an event or function do not establish an implicit AND, OR, or XOR.
6. Control-flow endpoints and direction are identifiable, and the process forms a connected structure.

These structural principles follow conventional EPC syntax. Formal treatments distinguish syntax from the behaviour a syntactically valid model permits. [Van der Aalst: Formalization and Verification of Event-driven Process Chains, Section 3](https://www.vdaalst.com/publications/p74.pdf).

An explicitly identified fragment may have boundaries outside the submitted view. Its missing surrounding context remains unspecified; it is not automatically a complete process with defective start or end points.

## Logical connectors

**Definition.** A logical connector specifies how control flow branches or merges. Its meaning depends on both its operator and its position in the flow.

- A **split** has one incoming connection and at least two outgoing connections.
- A **join** has at least two incoming connections and one outgoing connection.

**Rule.** A connector acts as either a split or a join. Where both operations are needed, they are represented by separate connectors. A connector performs no business activity of its own.

### AND, XOR, and OR

| Connector | Split meaning | Join meaning in this teaching profile |
|---|---|---|
| **AND** | All outgoing branches are activated. | All incoming branches must arrive before the flow continues. |
| **XOR — exclusive OR** | Exactly one outgoing branch is activated. | Mutually exclusive alternatives merge; the selected incoming branch permits continuation. Concurrent branches are not synchronized. |
| **OR — inclusive OR** | One or more outgoing branches are activated, possibly all. | The branches activated for this continuation are synchronized; inactive alternatives are not awaited. |

The distinction between all paths, one path, and one or more paths is central to EPC connectors. [ARIS: EPC in ARIS, core elements](https://ariscommunity.com/system/files/cs-aris-epc-en-24.pdf).

An AND split does not require activities to start or finish at exactly the same time. It makes all branches necessary while leaving their relative execution order unconstrained, except for dependencies elsewhere in the model.

An OR join does not simply continue when the first branch arrives. For example, if two of three service checks were activated, the join waits for both selected checks, but not for the third. In general structures, determining whether another arrival remains possible may require information about other parts of the process.

EPC join semantics have several formal interpretations. Here, XOR joins are used for exclusive alternatives and OR joins synchronize the relevant active branches. Complex cycles and overlapping branches may require an explicitly specified semantics; visual inspection alone does not resolve every case. [Kindler: On the semantics of EPCs, Sections 1–2](https://www2.compute.dtu.dk/~ekki/publications/copies/tr-ri03.pdf).

### Connector placement

**Rules.**

- A connector structure links events to functions or functions to events, preserving alternation on every branch. It does not mix events and functions as equivalent alternatives on the same side.
- In this profile, an XOR or OR split occurs on the function-to-event side. The preceding function establishes the outcome on which routing depends.
- An AND split may follow an event or a function, with the subsequent elements preserving alternation.
- AND, OR, and XOR joins may combine events before a function or functions before an event, provided their meanings and the alternation rule are respected.

The restriction on XOR and OR splits reflects the conventional principle that events do not decide between subsequent functions. It does **not** prohibit an XOR or OR join after several events. Some EPC variants relax the split restriction, so an explicitly supplied alternative profile must be distinguished from the default used here.

Consecutive connectors can express compound logic. They are not automatically invalid, but their combined meaning and the surrounding event–function alternation must remain clear.

### Branch conditions and examples

**Rules.** The possible outcomes are compatible with the selected connector. XOR alternatives are mutually exclusive for one decision; OR alternatives may coexist; AND branches are all required by the represented behaviour.

**Examples.**

- **XOR:** **Assess registration request** produces either **Request approved** or **Request rejected**. If the case also permits deferral, these two outcomes alone do not cover that case.
- **AND:** **Registration approved** enables both **Create user account** and **Prepare welcome package** through an AND split. Their completion events can meet at an AND join before **Confirm onboarding completion**.
- **OR:** **Assess support needs** establishes **Language support required**, **Accessibility support required**, or both. Each selected event enables its corresponding support function. An OR join can combine the completion events before the process continues.

An OR split does not express the selection of zero branches. If an instance may require neither support service, that possibility needs an explicit route or an appropriately scoped alternative structure.

**Convention.** Outcome labels and linked explanations make the routing conditions understandable. A connector label alone does not explain why a branch applies. Coverage concerns the outcomes included in the stated scope; it does not require every imaginable exception.

## Branches, joins, and completion

**Rules.** Dependencies introduced by splits and joins must be consistent with the branch behaviour. A process must not require an arrival that its own routing makes impossible.

**Examples of problematic combinations.**

- If an XOR split selects only one review route, an AND join that requires both routes to complete cannot proceed.
- If an AND split activates two checks, an XOR join does not express the requirement to wait for both checks. It is unsuitable where the next activity needs both results.
- If an OR split activates a variable subset of checks, an AND join requires every input, including an unselected check, unless another route supplies that input.

**Convention.** Structured branches that reconverge normally use a matching split and join operator. This is a useful design convention, not a universal requirement that every split must have a paired join. Alternative branches may terminate separately, and more complex structures require analysis of the actual paths.

Several start or end events are allowed. Their collective meaning must be understandable: multiple starts may describe alternative triggers or jointly required conditions; multiple ends may describe alternative outcomes or the completion of different branches. Reaching one end event does not automatically complete concurrent work elsewhere in the same instance.

## Loops and behavioural coherence

**Definition.** A loop permits part of the process to occur again, such as returning an incomplete registration request for correction.

**Rules.** A loop preserves the event, function, and connector rules. Its entry, repeated work, and exit have an identifiable interpretation. For a process intended to finish, the represented behaviour must permit completion rather than force endless repetition or permanent waiting.

**Example.** A request may undergo review repeatedly until its information is complete. If unsuccessful review returns the request to the same check without any correction or new information, the model needs an explanation of how a different outcome becomes possible.

**Conventions.**

- Repetition conditions and exit conditions are understandable.
- The model avoids functions that can never become enabled and branches that can never be completed.
- Completion does not leave required activities unresolved.
- Unintended repetition or duplicate execution is distinguishable from deliberate repeated work.

A loop is not an error merely because repetition is possible. Likewise, drawing an exit does not establish that it can be reached. Waiting for an external response is not automatically a structural deadlock; that judgement depends on the represented conditions and assumptions.

## Model structure and abstraction

**Conventions.**

- The process has an identifiable purpose, scope, and business object or case.
- Connected functions use compatible levels of detail, or an explicit refinement explains the difference.
- Event labels preserve distinctions that matter for later routing or work.
- Repeated occurrences of the same organizational unit preserve its identity; they do not imply additional departments.
- Similar labels for different activities or conditions do not obscure meaningful differences.
- Layout makes sequence, alternatives, concurrency, and responsibility assignments readable.

A function may be refined into another EPC. When such refinement is supplied, its entry conditions and possible results must be compatible with the function's meaning in the parent model. Decomposition is not mandatory for every broad function.

**Conditional completeness rule.** Required activities, responsibilities, outcomes, and exceptions depend on the task and the represented process scope. Internal coherence alone does not establish that a model accurately represents an exercise, source description, or real organization.

## Language and notation

**Conventions.**

- Labels are concise, grammatically interpretable, and sufficiently specific.
- Terms for the same object, condition, or unit remain consistent; abbreviations are explained where necessary.
- Event wording identifies a condition or occurrence, while function wording identifies work.
- Connector operators and control-flow directions are legible.
- Organizational assignments are visually distinguishable from control flow.
- Any notation extending or simplifying the profile is documented sufficiently to interpret its meaning.

Common EPC notation uses hexagons for events, rounded rectangles for functions, and circles containing AND, OR, or XOR symbols for connectors. Organizational units use the symbol established by the modelling tool or legend, often an ellipse. Colour, exact dimensions, and layout direction are presentation conventions unless the applicable notation assigns them a specific meaning.

An unfamiliar symbol, an unreadable label, or an ambiguous connection has an unresolved interpretation. It does not justify inventing missing content or treating a preferred drawing style as a semantic rule.

