# REA Knowledge

## Purpose and applicability

This component describes the concepts, semantics, structural rules, and modelling conventions of the Resource-Event-Agent (REA) ontology as used in the assembled prompt. It is shared reference knowledge for verification, validation, and other explicitly specified modelling tasks.

The selected task component determines which assessment is performed, which evidence is admissible, and how this knowledge is applied. Including this component does not by itself request verification or validation. The feedback-mode component determines how findings are presented.

The default modelling scope is an operational-level REA model, normally expressed as a UML class diagram. Its core includes economic resources, economic events, economic agents, stockflow, participation, duality, custody, and exchange or conversion processes. Equivalent, documented notation can express the same semantics.

Commitments, contracts, claims, policies, resource types, event types, and value-chain elements are extensions. Their applicability depends on the stated scope, explicit task requirements, or their presence in the submitted model. Their inclusion in this reference does not make them mandatory in every model. Contextual classes may also be present without belonging to the REA core.

The intended purpose, focal economic agent, process boundary, level of abstraction, and relationship between any supplied diagrams establish the model's scope. A complete operational process and an intentionally partial model have different completeness expectations.

### Status of the statements

- **Definitions** specify the meaning of REA constructs in the interpretation used here.
- **Rules** specify required semantic or structural conditions within their stated scope. Conditional rules apply only when their conditions hold.
- **Conventions** guide clarity, consistency, and appropriate abstraction. Departures require interpretation in context and are not automatically formal rule violations.
- **Examples** illustrate possible representations or business rules; they do not impose requirements on another model.

An explicitly supplied REA variant or documented modelling profile may define a different interpretation. Any such variation has an identifiable scope and must remain internally coherent; an unexplained departure does not establish an alternative rule. Case-specific facts, exact business rules, and requirements are supplied by the task or source material, not generated from examples in this component.

## Modelling perspective

**Definition.** The focal economic agent is the agent from whose perspective economic effects are represented. Increment, decrement, take, and give are relative to that perspective.

**Rules.** Event classifications, stockflows, and provider and recipient roles must be consistent with the same selected perspective. The same transfer can be an increment for its recipient and a decrement for its provider. Within one perspective and the same classification scope, an event cannot be classified as both an increment and a decrement.

A neutral or multi-agent representation is possible when its interpretation is explicit and classifications remain attributable to the appropriate perspectives. Separate diagrams may use different perspectives when their relationship is clear.

**Convention.** The focal perspective is explicit or reliably identifiable. An unidentified perspective leaves perspective-dependent meanings indeterminate; it does not justify silently selecting whichever perspective makes a model appear correct or incorrect.

## Economic resources

**Definition.** An economic resource is something of economic value under the control of an economic agent whose rights, quantity, features, capacity, or service potential can be affected by an economic event. Examples include cash, goods, and services such as labour service.

**Semantic distinctions.**

- A resource is distinct from an economic event, economic agent, goal, commitment, or document that merely records the resource.
- A person or organisation is normally an agent; a service supplied by that agent may be a resource. An employee and the employee's labour service are different kinds of element.
- Ownership, use, income, and transfer rights can have different economic meanings. Two events concerning the same physical object may affect different rights.
- A document or record is not the resource merely because it describes or records economic value. A different economic interpretation requires an explicit basis.
- Internal characteristics such as a person's knowledge, beauty, or skill, and relationships such as marriage or citizenship, are not independently transferable resources in the basic interpretation used here. Any resource interpretation of these phenomena requires clarification of what is controlled, provided, or economically affected.
- Mentioning an object or information item in a business context does not by itself establish its role as an economic resource.

**Conventions.** Resource names identify what has economic value rather than an activity. Resource classes use compatible levels of abstraction. Different names for the same resource, or separate classes for it, have a clear modelling reason. Economically important distinctions between resources and between their rights remain identifiable.

## Resource types

A **resource type** represents a category of economic resources that share specified characteristics, such as product category, size, or material. An economic resource can be related to its resource type through an is_instance_of relationship. Resources and resource types may appear together in a model, provided that their distinction and classification relationships are clear; their coexistence is not itself a modelling weakness.

## Economic events

**Definition.** An economic event is an occurrence that changes the economic value, rights, quantity, features, capacity, or service potential of one or more economic resources from the selected perspective.

**Rules.** An operational event has an identifiable economic effect. Its increment or decrement classification, when required by the notation, must agree with its stockflows and focal perspective. Multiple stockflows associated with the same event must have a coherent interpretation.

An event is distinct from an enduring object, actor, state, document, or database record. An order, agreement, promise, reservation, invoice, or similar item normally represents a commitment or information object rather than an operational event. Its appearance in a process does not establish that an economic change has occurred. A commitment and the event that fulfils it remain distinct.

**Conventions.** Event names identify occurrences clearly. Granularity is reasonably consistent unless different levels are intentional and explained. Economically distinct occurrences remain distinguishable, and duplicate event classes have a clear reason. An event combining several occurrences needs a coherent classification and relationship structure.

## Economic agents

**Definition.** An economic agent is a person, organisation, organisational unit, or clearly defined actor role capable of participating in economic events.

An agent can provide or receive economic value, control resources, or perform an economically relevant activity. The agent is distinct from the supplied service, resource, event, document, product, or technical component.

**Conventions.** Agent names identify the relevant actor or role. Individual agents, agent types, and roles use compatible levels of abstraction. Separate agent classes express meaningful differences rather than visual symmetry alone. Responsibility for performing an activity is distinguishable from providing or receiving economic value.

## Stockflow

**Definition.** A stockflow connects an economic event with an economic resource and expresses how the event affects rights to, or features of, that resource from the selected perspective.

**Endpoint rule.** At the class level, a stockflow connects an economic event type and an economic resource type. An event-event, resource-resource, or event-agent relationship cannot serve as a stockflow under this interpretation.

| Stockflow | Event classification | Aspect affected | Meaning from the focal agent's perspective |
|---|---|---|---|
| **Take** | Increment | Rights | The agent obtains or increases rights to the resource. |
| **Give** | Decrement | Rights | The agent relinquishes or transfers rights to the resource. |
| **Produce** | Increment | Features, quantity, or existence | The resource is created, increased, or given economically valuable features. |
| **Consume** | Decrement | Features, quantity, or service potential | The resource is expended, transformed, or depleted as an input. |
| **Use** | Decrement | Features, capacity, or service potential | The resource contributes to an activity without normally being consumed as a whole. |

**Compatibility rules.** Increment events use take or produce stockflows; decrement events use give, consume, or use stockflows. The affected resource, kind of change, and event classification must agree. A different combination requires an explicitly defined alternative REA interpretation.

**Conventions.** Stockflow meanings are explicit and readable. A transferred right is identified where leaving it unspecified would make the economic meaning ambiguous. Several stockflows associated with one event may represent several affected resources, provided their meanings remain coherent.

## Participation

**Definition.** Participation connects an economic event with an economic agent. For an exchange event, participation normally identifies the provider and recipient of the affected economic value.

**Rules.**

- The endpoints are an economic event and an economic agent.
- The provider is the agent from whom the relevant resource or right flows; the recipient is the agent to whom it flows.
- The roles agree with the event's stockflow, classification, and selected perspective.
- In an exchange, the focal agent is normally the recipient in an increment event and the provider in a decrement event. The counterparty normally has the complementary role.

An exchange event has sufficient participation to make the transfer understandable. A purely internal conversion event does not automatically require both transfer roles when they are outside the selected scope.

The agent performing an activity need not be the agent providing or receiving its economic value. Participation concerns the particular event; an agent's involvement elsewhere in a process does not establish participation in every event.

**Convention.** Role labels and their association ends identify the intended participation unambiguously.

## Duality

**Definition.** Duality connects economic events that express an economic rationale: giving up, consuming, or using one resource in order to obtain or produce another.

**Rules.** Duality connects economic events, including at least one increment and at least one decrement, belonging to the same economically meaningful exchange or conversion. Their stockflows must be compatible with that process. Temporal sequence, causation, or data flow alone does not constitute economic duality.

Duality is not universally one-to-one. For example, one payment may be dual to several deliveries, and one production event may be dual to several consumption or use events. Exact multiplicities depend on the represented business rules and event granularity.

**Convention.** The relation's meaning is explicitly labelled when it would otherwise be uncertain. Boundaries around a partial process make clear why an economic counterpart may not appear within the diagram. Completeness requirements are stated below under exchange and conversion processes.

## Custody

**Definition.** Custody connects an economic agent with an economic resource and expresses continuing possession, control, or responsibility for that resource.

**Rules.** Its endpoints are an agent and a resource, and the relation has a meaningful possession, control, or responsibility interpretation. Custody is distinct from participation in a particular event and from the event through which rights or control change.

**Conventions.** Custody role names and multiplicities agree with its intended meaning. Custody is applicable only when continuing control or responsibility is within scope; it is not a mandatory addition to every REA model or a substitute for a represented change event.

## Exchange and conversion processes

**Definitions.** An exchange concerns transfers of rights between agents. A conversion concerns producing resources or changing their features, quantity, capacity, or service potential.

| Process | Characteristic stockflows | Pattern in a complete operational process |
|---|---|---|
| **Exchange** | Take and give | At least one increment and one decrement connected through economic duality, with reciprocal provider and recipient roles. |
| **Conversion** | Produce, consume, and use | At least one production event and at least one consumption or use event connected through economic duality. |

**Structural minima for a complete operational process.**

- Every economic event affects at least one economic resource through a stockflow.
- Every exchange event has participation sufficient to identify its provider and recipient.
- Every increment or decrement event participates in economically meaningful duality.
- Each relationship connects the permissible REA element types.

These completeness conditions are relative to the stated process boundary. An intentionally partial view may omit an economic counterpart outside that boundary; its absence is not by itself proof that the complete process violates REA.

**Coherence rules.** Input and output resources are traceable through the represented events and stockflows. Events grouped into a process share an economic rationale. Mixed exchange and conversion content has an explicit decomposition or coherent explanation.

**Convention.** A separate process element is optional when the events and duality already express the process pattern.

An exchange may contain several increment or decrement events. For example, one payment may compensate for both a product and a delivery service. A conversion may combine several consumption or use events with one production event. These are possible patterns, not case-independent requirements.

## Commitments, contracts, and other extensions

The following distinctions apply when these constructs are within the modelling scope. Their exact notation and additional constraints depend on the supplied modelling profile or task rules.

### Commitments and fulfilment

A **commitment** represents a future-oriented undertaking concerning an economic event. It may specify parties, quantities, dates, or conditions. Orders, promises, reservations, and agreements can provide evidence of commitments, depending on their stated meaning.

Every **commitment must be related to at least one economic resource or resource type, specifying what the promised economic event will affect.** A commitment concerning a particular resource identifies that resource, whereas a commitment concerning a resource type specifies the category of resource promised without necessarily identifying an individual resource. For example, a delivery commitment may concern a particular picture or a picture of a specified type.

A **fulfilment relationship** links a commitment with the economic event that satisfies it. The promised occurrence and the actual occurrence remain distinct. Reciprocal commitments express the corresponding undertakings in a planned exchange; their existence does not establish that the operational exchange has occurred.

### Contracts and containment

In the extended representation used here, a **contract** groups related commitments between parties. **Containment** represents the association of those commitments with the contract. The contract, its commitments, and the events fulfilling them have different roles; containment is distinct from fulfilment and from operational duality.

The number of commitments, the participating parties, their terms, and exact containment or fulfilment multiplicities depend on the specified contract representation and business rules. This component does not impose a universal number of commitments or a single prescribed contract diagram.

### Other extensions

Claims, policies, event types, and value-chain elements may also be included. Their meaning and constraints require the relevant supplied definitions or documented profile; mentioning them here does not provide a complete extended REA metamodel.

A resource type and a resource, an event type and an occurrence, and a policy and an operational event represent different abstraction levels or roles. These distinctions remain identifiable when extensions and operational elements appear together.

## Multiplicities and structural constraints

**Meaning.** Multiplicities express minimum and maximum numbers of related instances. Their association ends determine which participation is constrained. Business rules may also concern optionality, timing, conditions, thresholds, aggregation, or exceptions.

**Rules.**

- Multiplicity values are syntactically valid and attached to the intended association ends.
- Constraints are internally coherent and compatible with the represented relationship semantics.
- Relationships do not impose contradictory constraints on the same represented population.
- Optionality does not remove participation essential to an event's stated REA meaning within a complete operational representation.

General REA principles establish structural conditions, but do not determine all exact business multiplicities. One payment may settle several shipments, several payments may settle one shipment, and several input events may support one production event. The task's business rules and event granularity determine which pattern applies.

Omitted multiplicities leave some structural questions unspecified. A missing value is distinguishable from an invalid value, and neither permits invention of a case-specific constraint. A requirement to show multiplicities is itself dependent on the supplied task or notation requirements.

## Model structure and abstraction

**Semantic rules.**

- Classifications, roles, relationships, and constraints describing the same phenomenon are mutually coherent.
- Core REA elements participate meaningfully in the represented pattern; contextual classes have an understandable relationship to that pattern without inappropriate REA classifications.
- Combining or separating represented phenomena preserves their intended identities and economically important distinctions.

**Conventions.**

- Equivalent concepts use consistent terms, while distinct economic meanings remain distinguishable.
- Duplicate classes or relationships have a clear purpose, such as different roles, perspectives, or views.
- Event granularity and the abstraction levels of resources and agents are reasonably consistent or explicitly distinguished.
- Alternative diagrams, refinements, different perspectives, and complementary parts of one model are distinguishable when several diagrams are supplied.

## Language and notation

**Conventions.**

- REA types or equivalent classifications distinguish resources, events, and agents without relying solely on colour or position.
- Increment and decrement classifications are unambiguous when required by the notation.
- Relationship types, role labels, multiplicities, and association ends are identifiable and readable.
- Documented equivalent notation preserves the same semantics; a visual difference alone is not a semantic difference.
- Class names are meaningful and normally use singular noun phrases. Event names identify occurrences rather than unqualified labels such as `Process`, `Transaction`, or `Activity`.
- Attributes, when present, describe their owning classes and are distinguishable from classes and relationships.
- Arrowheads, layout, proximity, and colour supplement explicit semantics rather than silently replacing them.
- Spelling or grammatical differences matter when they affect interpretation. Different wording can preserve the same economic meaning.

These conventions concern intelligibility and consistency. Their assessment remains sensitive to the selected notation, model purpose, and the evidence available in the active task.
