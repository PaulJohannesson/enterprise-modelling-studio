# REA Verification Criteria

Use the following criteria to verify the internal quality of a model expressed in REA, the Resource-Event-Agent ontology.

Verification concerns whether the model is internally coherent, consistently formulated, and constructed according to the applicable REA modelling rules. It does not determine whether the model accurately or completely represents an exercise, scenario, specification, or other external source. That comparison belongs to validation.

## Applicable REA scope

These criteria primarily concern an operational-level REA model expressed as a UML class diagram. Such a model may contain:

- economic resources;
- economic events classified as increments or decrements;
- economic agents;
- stockflow relationships;
- participation relationships with provider and recipient roles;
- duality relationships;
- custody relationships;
- exchange and conversion processes.

REA also has extensions for commitments, claims, policies, resource types, event types, value chains, and other abstractions. Do not require these extended constructs unless they are included in the submitted model or explicitly required by another component of the assembled prompt.

If the model uses different but documented notation, assess whether it expresses the equivalent REA semantics. Do not treat a purely visual difference as a modelling error.

## Modelling perspective

REA classifications such as **increment**, **decrement**, **take**, and **give** depend on the economic agent from whose perspective the model is constructed.

Examine whether:

- the focal economic agent is stated or can be identified reliably;
- increment and decrement events are classified consistently from that agent's perspective;
- provider and recipient roles agree with the selected perspective;
- take and give stockflows agree with the selected perspective;
- the perspective remains consistent throughout the model;
- a neutral or multi-agent perspective, if used, is made explicit and does not combine incompatible classifications.

For example, the same transfer may be an increment for the agent receiving a resource and a decrement for the agent providing it. Do not classify an event independently of the model's perspective.

If the perspective cannot be determined, identify the resulting ambiguity. Do not silently choose a perspective merely to make the model appear correct or incorrect.

## Economic resources

An **economic resource** is something of economic value that is under the control of an economic agent and whose rights, quantity, features, or service potential can be affected by an economic event. Economic resources may include cash, goods, and services such as labour service.

For each economic resource, examine whether:

- it represents something of economic value rather than an event, agent, document, record, goal, or commitment;
- it can meaningfully be controlled, transferred, used, consumed, or produced;
- the relevant resource is modelled rather than merely a document that records it;
- it is formulated at a level of abstraction consistent with the other resources;
- its name identifies the resource clearly and does not describe an activity;
- it is not duplicated under different names without a clear modelling reason;
- any distinction between the resource and the economic agent providing it is preserved.

A person is normally an economic agent, whereas a service supplied by that person may be an economic resource. For example, an employee and the employee's labour service should not be treated as the same kind of element.

When an event changes rights to a resource, examine whether the relevant right is sufficiently clear. Depending on the case, this may be an ownership right, use right, income right, or transfer right. Two events involving the same physical object may concern different rights and therefore have different economic meanings.

Internal characteristics such as a person's knowledge, beauty, or skill, and shared relationships such as marriage or citizenship, are not independently transferable economic resources in the basic REA sense. If such a phenomenon is included as an economic resource, its intended interpretation must be made explicit.

## Economic events

An **economic event** is an occurrence that changes the economic value, rights, quantity, features, or service potential of one or more economic resources from the selected perspective.

For each economic event, examine whether:

- it represents an occurrence rather than an enduring object, actor, state, document, or database record;
- it has an identifiable economic effect on at least one economic resource;
- its name expresses the occurrence clearly;
- it is classified as an increment or decrement when the notation requires this;
- its increment or decrement classification agrees with its stockflow relationships;
- its classification is consistent with the focal agent's perspective;
- its level of granularity is reasonably consistent with the other events;
- it is distinct from other event classes rather than duplicating the same occurrence without justification.

An order, agreement, promise, reservation, invoice, or similar item normally represents a commitment or information object rather than an operational economic event. Do not classify it as an economic event merely because it appears in a business process. If an extended REA model includes commitments, they should be distinguished explicitly from events that change economic resources.

An event should not be classified simultaneously as both an increment and a decrement from the same perspective. If one event appears to combine several economically different occurrences, examine whether its classification and relationships remain coherent.

## Economic agents

An **economic agent** is a person, organisation, organisational unit, or clearly defined role capable of participating in economic events.

For each economic agent, examine whether:

- it can meaningfully provide, receive, control, or otherwise participate in economic resources and events;
- it represents an actor or actor role rather than a resource, event, document, product, or technical component;
- its name identifies the relevant person, organisation, or role clearly;
- individual agents and agent types or roles are not mixed at incompatible levels of abstraction;
- the same agent role is not duplicated merely to make different parts of the diagram visually symmetrical;
- different agent classes genuinely represent different roles or categories.

When an agent supplies a service, distinguish the agent from the supplied service. For example, a carrier may be an economic agent, while delivery service may be an economic resource.

## Stockflow relationships

A **stockflow relationship** connects an economic event with an economic resource and describes how the event changes rights to, or features of, that resource from the selected perspective.

Every stockflow relationship must connect:

- one economic event type; and
- one economic resource type.

Do not use a stockflow relationship between two events, between two resources, or between an event and an agent.

Examine whether each stockflow is classified according to the following semantics:

| Stockflow | Event classification | Aspect affected | Meaning from the focal agent's perspective |
|---|---|---|---|
| **Take** | Increment | Rights | The agent obtains or increases rights to the resource. |
| **Give** | Decrement | Rights | The agent relinquishes or transfers rights to the resource. |
| **Produce** | Increment | Features, quantity, or existence | The resource is created, increased, or given economically valuable features. |
| **Consume** | Decrement | Features, quantity, or service potential | The resource is expended, transformed, or depleted as an input. |
| **Use** | Decrement | Features, capacity, or service potential | The resource contributes to an activity without normally being consumed as a whole. |

For each stockflow relationship, examine whether:

- the selected stockflow type corresponds to the actual kind of economic change represented;
- take and give are used for changes in rights;
- produce, consume, and use are used for changes in resource features, quantity, existence, capacity, or service potential;
- the stockflow agrees with the event's increment or decrement classification;
- the resource at the other end of the relationship is the resource actually affected;
- the relationship label is explicit and readable;
- the nature of a transferred right is stated when it would otherwise be ambiguous;
- several stockflows attached to the same event remain mutually consistent.

An increment event should therefore use a **take** or **produce** stockflow. A decrement event should use a **give**, **consume**, or **use** stockflow. Treat a different combination as a weakness unless the model explicitly defines an alternative REA interpretation.

## Participation relationships

A **participation relationship** connects an economic event with an economic agent. In an exchange, the relationship normally identifies the provider and recipient of the economic value affected by the event.

For each participation relationship, examine whether:

- it connects an economic event and an economic agent;
- the agent genuinely participates in the event;
- the provider and recipient roles are stated clearly when they are relevant;
- the provider is the agent from whom the relevant resource or right flows;
- the recipient is the agent to whom the relevant resource or right flows;
- the roles agree with the event classification, stockflow, and selected perspective;
- agents responsible for performing an event are not confused with agents providing or receiving its economic value.

For an exchange modelled from the focal agent's perspective, the focal agent is normally the recipient in an increment event and the provider in a decrement event. The counterparty normally has the complementary role.

An exchange event must have enough agent participation to make the transfer understandable. Do not automatically require both a provider and recipient for a purely internal conversion event if the selected modelling scope does not represent such transfer roles.

## Duality relationships

A **duality relationship** connects economic events that form the economic rationale of a business process: an agent gives up, consumes, or uses one economic resource in order to obtain or produce another.

For each duality relationship, examine whether:

- it connects economic events rather than resources or agents;
- it connects at least one increment event with at least one decrement event;
- the linked events belong to the same economically meaningful exchange or conversion;
- the relationship expresses reciprocity or transformation rather than merely temporal sequence, causation, or data flow;
- the stockflows of the linked events are compatible with the process represented;
- the relationship is labelled clearly when its meaning would otherwise be uncertain.

Do not assume that duality must be one-to-one. One payment may be dual to several deliveries, and one production event may be dual to several consumption or use events. The multiplicity must reflect the represented business rules.

In a complete operational process, increment events should not remain economically unexplained by any decrement event, and decrement events should not remain unrelated to the value they help obtain. If the submitted model intentionally shows only part of a process, identify the boundary before treating an unpaired event as a violation.

## Custody relationships

A **custody relationship** connects an economic agent with an economic resource and expresses continuing possession, control, or responsibility for that resource.

If custody is represented, examine whether:

- it connects an economic agent and an economic resource;
- the agent can meaningfully possess, control, or be responsible for the resource;
- it is distinguished from participation in a particular event;
- it is distinguished from the event through which rights to the resource are transferred;
- its multiplicities and role names agree with its intended meaning.

Do not require custody relationships when they fall outside the stated scope of the model. Do not use custody as a substitute for an economic event that changes control or rights.

## Exchange and conversion processes

An **exchange process** concerns transfers of rights between agents. A **conversion process** concerns producing resources or changing their features, quantity, capacity, or service potential.

If the model identifies or clearly groups business processes, examine whether:

- an exchange process uses **take** and **give** stockflows;
- a conversion process uses **produce**, **consume**, and **use** stockflows;
- a complete exchange contains at least one increment event and at least one decrement event connected through duality;
- a complete conversion contains at least one production event and at least one consumption or use event connected through duality;
- input and output resources can be traced through the events and their stockflows;
- provider and recipient roles in an exchange are reciprocal across the dual events;
- a process does not mix exchange and conversion semantics without an explicit decomposition or explanation;
- the process contains economically related events rather than activities grouped only because they occur near one another in time.

An exchange may contain several increment or decrement events. For example, acquiring a product and a delivery service may be compensated by one payment. A conversion may similarly contain one production event and several consumption or use events.

Do not require an explicit process element when the model represents the REA pattern directly through events and duality relationships.

## Multiplicities and structural constraints

When UML multiplicities are shown, examine whether:

- each multiplicity is readable and attached to the correct association end;
- minimum and maximum values are syntactically valid;
- the multiplicities at both ends express a coherent business rule;
- the multiplicities agree with the meaning of the stockflow, participation, duality, or custody relationship;
- different relationships do not impose contradictory constraints on the same classes;
- optional participation is not used where the relationship is necessary for the represented event to have its stated REA meaning.

Apply the following structural minima when the model represents a complete operational REA process:

- every economic event affects at least one economic resource through a stockflow relationship;
- every exchange event has the agent participation needed to identify its provider and recipient;
- every increment or decrement event participates in an economically meaningful duality relationship;
- every relationship connects permissible REA element types.

Do not impose universal one-to-one multiplicities. Exact multiplicities depend on business rules and event granularity. For example, one payment may settle several shipments, several payments may settle one shipment, or several input events may support one production event.

If multiplicities are omitted, identify which structural questions cannot be verified. Do not invent exact multiplicities from general REA principles alone.

## Model structure and coherence

Examine whether:

- every core element participates in the REA pattern represented by the model;
- no economic event is isolated from the resource it affects;
- relationships connect the correct kinds of elements;
- increment and decrement classifications agree with all connected stockflows;
- provider and recipient roles agree with the direction of economic value;
- duality relationships create understandable exchange or conversion structures;
- the model does not contain contradictory representations of the same economic phenomenon;
- duplicate classes and relationships have been avoided unless they express genuinely different roles or meanings;
- the model uses a reasonably consistent level of abstraction and event granularity;
- boundaries around partial processes or omitted details are made clear when their absence would otherwise appear to create an incomplete REA pattern.

Do not treat every business-related class as part of the REA core. A model may contain contextual classes, but their relationship to the REA elements should be understandable, and they should not be assigned REA stereotypes that conflict with their meaning.

## Language and UML notation

Examine whether:

- REA stereotypes or equivalent classifications are applied consistently;
- economic resources, events, and agents can be distinguished without relying only on colour or position;
- increment and decrement events are marked unambiguously;
- stockflow, participation, duality, and custody relationships are named or otherwise identified clearly;
- provider and recipient role names appear at the correct association ends;
- class names are concise, meaningful, and normally expressed as singular noun phrases;
- event names identify occurrences rather than using vague labels such as `Process`, `Transaction`, or `Activity` without qualification;
- the same term is used consistently for the same concept;
- relationship lines, labels, multiplicities, and association ends can be read without guessing;
- arrowheads, layout, proximity, or colour are not used as substitutes for explicit relationship semantics;
- attributes, if included, describe the class to which they belong and are not confused with classes or relationships.

Minor spelling or grammatical problems are weaknesses only when they make a model element or relationship difficult to interpret.

## Verification limits

Base the verification only on the submitted model and the REA rules included in the assembled prompt.

Do not claim that verification establishes whether:

- the model accurately or completely represents an external scenario;
- all relevant resources, events, agents, or processes from a source have been included;
- a stated business rule or multiplicity is factually correct in the real organisation;
- a resource has the alleged economic value or transferability in practice;
- an event actually occurred;
- an omitted commitment, policy, type, or value-chain element was required when the stated scope is limited to the operational REA model.

Distinguish among:

- clear violations of the stated REA rules;
- internal inconsistencies;
- semantically questionable modelling decisions;
- decisions that depend on an unstated perspective, scope, or business rule;
- matters that cannot be determined from the model alone.

Do not invent weaknesses merely to ensure that every criterion produces a finding. When more than one interpretation is reasonable, state the uncertainty rather than automatically selecting the interpretation that produces the strongest criticism.
