# REA Validation Criteria

Use the following criteria to validate a model expressed in REA, the Resource-Event-Agent ontology, against the supplied source material and the stated modelling purpose.

Validation concerns whether the model adequately represents the relevant content of an exercise, scenario, specification, interview, policy document, stakeholder statement, or other source. It examines alignment between the model and external material rather than merely the model's internal construction.

These criteria primarily concern an operational-level REA model, normally expressed as a UML class diagram. Such a model may represent economic resources, economic events, economic agents, stockflows, participation, duality, custody, and exchange or conversion processes. Extended REA constructs, such as commitments, claims, policies, resource types, event types, and value-chain elements, are relevant only when they fall within the stated modelling scope or are explicitly required.

Do not treat validation and verification as interchangeable. A model element may follow REA rules but still misrepresent the source. Conversely, a model element may preserve part of the source meaning while containing an internal REA weakness. Keep source alignment and internal REA correctness distinct unless verification criteria have also been included in the assembled prompt.

## Validation scope

Before assessing alignment, determine:

* which material constitutes the source;
* what the model is intended to represent;
* which part of the source falls within the intended modelling scope;
* which economic agent's perspective the model is intended to adopt;
* whether the model concerns an exchange process, a conversion process, or both;
* whether the source contains explicit modelling requirements;
* whether commitments or other extended REA constructs fall within scope;
* whether several diagrams represent alternatives, refinements, different perspectives, or parts of one model;
* whether some source material is contextual and not expected to appear in the model.

Do not assume that every sentence in the source must be represented. Assess completeness in relation to the modelling purpose, selected perspective, stated process boundary, and any explicit requirements.

If the modelling purpose, scope, perspective, or relationship among several diagrams is unclear, identify this as a limitation affecting the validation.

If several sources are supplied, determine whether they have different roles or levels of authority. Do not silently resolve material conflicts among sources.

## Traceability from source to model

For each source statement that is relevant to the modelling purpose, examine whether:

* it has a corresponding model element, classification, relationship, multiplicity, or process structure;
* the corresponding model content can be identified unambiguously;
* all economically important parts of the source statement have been represented;
* the model preserves the meaning of the source statement;
* the model preserves relevant distinctions among agents, resources, events, rights, commitments, and processes;
* several distinct source statements have been combined in a way that changes or obscures their meaning;
* the source statement has been represented more than once without a clear reason;
* the representation depends on an assumption not stated in the source.

When identifying a correspondence, quote or reference both:

1. the relevant source passage; and
2. the corresponding model element, relationship, classification, or constraint.

Do not claim that a source statement is represented merely because the source and model use similar words. Examine whether their economic meanings actually correspond.

## Traceability from model to source

For each model element, classification, relationship, multiplicity, and process structure, examine whether:

* it is directly supported by the source;
* it is a reasonable interpretation of the source;
* it depends on an additional assumption;
* it extends the source with unsupported content;
* it contradicts the source;
* no identifiable source basis can be found.

A model element does not need to repeat the exact wording of the source. Reformulation is acceptable when the original economic meaning is preserved.

Distinguish clearly between an unsupported addition and an assumption. An assumption extends the source and may be acceptable when assumptions are permitted and made explicit. An unsupported addition is presented as though it came from the source even though no basis for it can be identified.

Do not assume that model content is false merely because it is absent from the source. Classify it according to the available evidence and the rules concerning assumptions below.

## Coverage and completeness

Examine whether the model includes all source content that is relevant to the stated purpose, including, where applicable:

* the focal economic agent and modelling perspective;
* the principal internal and external economic agents;
* the economic resources transferred, consumed, used, or produced;
* the rights, quantities, features, capacities, or service potential affected;
* the economically significant events;
* the providers and recipients participating in exchange events;
* the stockflows between events and resources;
* the duality relationships that express economic reciprocity or transformation;
* custody relationships that are relevant to continuing control or responsibility;
* the exchange and conversion processes described by the source;
* commitments, claims, policies, types, or other REA extensions explicitly included in the scope;
* stated cardinalities, optionality, temporal constraints, and other business rules;
* distinctions among separate transactions, process stages, agent roles, and resource types.

Identify source content that is relevant to the modelling purpose but missing from the model. Explain why the omitted content matters to the intended REA representation.

Do not treat contextual facts as omissions merely because they concern the same organisation or business process. A source statement is relevant only when it contributes to the model's stated purpose or fulfils an explicit task requirement.

## Faithfulness of the modelling perspective

REA classifications such as increment, decrement, take, and give depend on the economic agent from whose perspective the model is constructed.

Examine whether:

* the focal economic agent agrees with the task or source;
* the source provides a focal perspective or the modeller has introduced one as an explicit assumption;
* transfers described by the source are interpreted consistently from that perspective;
* the provider and recipient of each transfer correspond to the source;
* increment and decrement classifications preserve the direction of economic value stated or implied by the source;
* take and give relationships preserve the direction of rights described by the source;
* several agent perspectives have been combined in a way that changes or obscures the source meaning;
* a change of perspective between diagrams is stated explicitly and supported by the modelling purpose.

If the source is neutral about perspective, do not declare a reasonable selected perspective contradictory merely because another perspective was possible. Determine whether the selection is explicit, consistently applied, and suitable for the stated modelling purpose.

If the perspective cannot be determined from either the source or the model, classify perspective-dependent judgements as assumptions or as matters that cannot be determined.

## Faithfulness of economic resources

For each economic resource, examine whether:

* it corresponds to something of economic value described or reasonably implied by the source;
* the model preserves the identity and nature of the resource;
* distinctions among goods, money, services, rights, capacity, labour, and other resources are preserved when relevant;
* the relevant ownership, use, income, or transfer right is preserved when the source distinguishes among rights;
* quantities, conditions, qualities, or service potential stated in the source are represented without changing their meaning;
* a resource has been replaced by a document or record that merely describes it;
* a person or organisation has been represented as the service that the agent provides, or vice versa;
* separate source resources have been merged in a way that obscures economically important differences;
* one source resource has been divided into several model resources without support;
* an important source-described resource is missing;
* a modelled resource has no identifiable source basis.

Do not require every physical object or informational item mentioned in the source to become an economic resource. Its relevance depends on its economic role in the process being modelled.

## Faithfulness of economic events

For each economic event, examine whether:

* it corresponds to an occurrence described or reasonably implied by the source;
* the event preserves the economically relevant action or change described by the source;
* the affected resource, relevant right, quantity, feature, capacity, or service potential is preserved;
* the participating agents and their roles agree with the source;
* the event's increment or decrement meaning agrees with the source when interpreted from the selected perspective;
* the event's granularity corresponds to the source rather than combining economically distinct occurrences without support;
* one source occurrence has been duplicated as several events without a clear modelling reason;
* an order, agreement, promise, reservation, invoice, or similar source item has been transformed into an operational event even though the source describes a commitment or information object;
* an event described by the source is missing;
* a modelled event has no identifiable source basis.

When the source describes an activity but does not state whether it changes an economic resource, distinguish between a supported economic-event interpretation, an assumption, and a matter that cannot be determined.

## Faithfulness of economic agents

For each economic agent, examine whether:

* it corresponds to a person, organisation, organisational unit, or actor role described or reasonably implied by the source;
* the model preserves the distinction between internal and external agents when relevant;
* the represented role agrees with the role that the actor performs in the source;
* the provider and recipient roles assigned to the agent preserve the direction of economic value described by the source;
* responsibility for performing an activity has been confused with providing or receiving economic value;
* an individual agent, an organisational agent, and an agent type or role have been mixed without source support;
* an agent has been merged with another actor that the source treats as distinct;
* one source actor has been divided into several agents without a clear reason;
* a service has been represented as the agent that provides it, or vice versa;
* an important source-described agent is missing;
* a modelled agent has no identifiable source basis.

Differences in organisational terminology are acceptable when the model preserves the source role unambiguously.

## Faithfulness of stockflow relationships

For each stockflow relationship, examine whether:

* the source supports an economic effect between the represented event and resource;
* the affected resource corresponds to the resource described in the source;
* the stockflow preserves whether the source concerns a change in rights, quantity, features, capacity, existence, or service potential;
* take and give preserve the direction of rights described by the source from the selected perspective;
* produce, consume, and use preserve the kind of resource transformation described by the source;
* the nature of a transferred right is preserved when the source distinguishes among different rights;
* several resources affected by one event have all been represented when they fall within scope;
* a source-supported stockflow is missing;
* a modelled stockflow depends on an unstated assumption or has no identifiable source basis;
* the stockflow contradicts the economic change described by the source.

A stockflow may be internally well formed according to REA but still be a validation weakness if it represents a different resource, right, or economic effect from the one described in the source.

Do not infer a particular stockflow solely because an event and a resource are mentioned near one another. The source must support or reasonably imply the economic effect represented by the relationship.

## Faithfulness of participation relationships

For each participation relationship, examine whether:

* the source supports the agent's participation in the represented event;
* the provider and recipient roles agree with the source;
* the model preserves which agent provides and which agent receives the relevant resource or right;
* the roles agree with the selected perspective without reversing the source meaning;
* an agent responsible for performing an event has been confused with an agent providing or receiving its economic value;
* several participants or roles described by the source have been merged or omitted;
* participation has been added merely because an agent appears elsewhere in the same process;
* a source-supported participation relationship is missing;
* a modelled participation relationship has no identifiable source basis.

Do not assume that every agent mentioned in connection with a process participates in every economic event. Establish correspondence at the level of the particular event.

## Faithfulness of duality relationships

For each duality relationship, examine whether:

* the source supports an economic reciprocity or transformation between the linked events;
* the linked events belong to the same economically meaningful exchange or conversion described by the source;
* the relationship preserves what is given, consumed, or used in order to obtain or produce something else;
* a temporal sequence, causal dependency, or data flow has been transformed into duality without economic support;
* separate exchanges or conversions described by the source have been combined into one duality structure;
* one exchange or conversion has been divided into several unrelated structures without support;
* the source supports one-to-one, one-to-many, or many-to-many correspondence among the linked events when such a business rule is represented;
* a source-supported economic counterpart is missing;
* a modelled duality relationship depends on an unstated assumption or has no identifiable source basis.

Do not infer duality merely because two events occur close together in time. The source must support the economic rationale that connects them.

## Faithfulness of custody relationships

If custody falls within the modelling scope, examine whether:

* the source supports continuing possession, control, or responsibility between the represented agent and resource;
* the responsible agent and controlled resource correspond to the source;
* custody has been confused with participation in a particular event;
* custody has been confused with the event through which rights or control change;
* the duration, optionality, or multiplicity of custody preserves any source-stated business rule;
* a relevant source-described custody relationship is missing;
* a modelled custody relationship has no identifiable source basis.

Do not require custody merely because the source mentions ownership or possession if continuing control lies outside the intended model scope.

## Faithfulness of exchange and conversion processes

For each exchange or conversion process, examine whether:

* the process corresponds to the economic purpose and boundary described by the source;
* a transfer of rights between agents is represented as an exchange when that is the source meaning;
* production, consumption, use, or transformation of resources is represented as a conversion when that is the source meaning;
* economically related events are grouped together without including events that belong to a different transaction or process;
* all relevant input and output resources can be traced through the represented events;
* exchanges preserve the reciprocal provider and recipient roles described by the source;
* conversions preserve the source-described relationship among inputs, transformation, and outputs;
* mixed exchange and conversion content is decomposed or explained when the source distinguishes the processes;
* process stages, alternatives, repetitions, or dependencies stated in the source have been preserved;
* a process boundary omits source content necessary to understand the represented economic rationale;
* a modelled process or grouping has no identifiable source basis.

Do not require operational details that lie outside the intended REA scope merely because they occur within the broader business process.

## Commitments and other REA extensions

If commitments or other extended REA constructs are included in the stated scope, examine whether:

* each commitment corresponds to a promise, order obligation, agreement, reservation, or other future-oriented undertaking described by the source;
* the promised economic event, resource, quantity, date, or condition preserves the source meaning;
* the parties to the commitment and their roles correspond to the source;
* fulfilment relationships correspond to the events that the source describes as satisfying the commitments;
* reciprocal commitments preserve the economic exchange described by the source;
* a commitment has been confused with the operational event that fulfils it;
* claims, policies, resource types, event types, or value-chain elements preserve the distinctions made in the source;
* an extended construct required by the source or task is missing;
* a modelled extended construct has no identifiable source basis.

Do not require commitments, claims, policies, types, or value-chain elements when they are not included in the stated scope or explicit task requirements.

## Multiplicities and business rules

For each multiplicity or other structural constraint, examine whether:

* it corresponds to a business rule stated or reasonably implied by the source;
* minimum and maximum participation preserve whether a relationship is mandatory, optional, singular, or repeated;
* the constraint is attached to the correct classes and relationship ends;
* one payment covering several deliveries, several inputs supporting one production event, or another aggregation rule is represented as described by the source;
* time periods, conditions, thresholds, or exceptions relevant to the relationship are preserved;
* an exact multiplicity has been introduced even though the source provides no basis for it;
* a source-stated constraint is missing from the model;
* constraints in different parts of the model represent the source consistently.

When the source does not determine an exact multiplicity, classify the modelled value as an assumption or state that its alignment cannot be determined. Do not derive exact business rules from general REA principles alone.

## Terminology and referential consistency

Examine whether:

* important source terms are represented consistently;
* synonyms or abbreviations in the model preserve the source meaning;
* the same agent, resource, event, commitment, process, organisation, product, or service is referred to consistently;
* a model label introduces ambiguity not present in the source;
* pronouns or shortened names cause uncertainty about the intended referent;
* distinctions made in the source have been collapsed;
* one source concept has been divided into several model concepts without justification;
* several source concepts have been merged into one model concept without justification;
* similar labels have been used for economically different concepts;
* different labels have been used for the same concept without an evident reason.

Differences in wording are not weaknesses by themselves. The relevant question is whether the economic meaning and intended referent have been preserved.

## Assumptions

Examine whether:

* assumptions introduced by the modeller are stated explicitly;
* assumptions are clearly distinguishable from source-derived content;
* the model depends on assumptions that have not been disclosed;
* an assumption contradicts the source;
* an assumption changes the intended scope, perspective, process boundary, or economic meaning of the model;
* classifications, relationships, multiplicities, and process structures based on assumptions can be identified;
* an assumption fills a genuine gap in the source rather than overriding available evidence.

Do not automatically treat every assumption as a weakness. Identify an assumption as problematic when it is hidden, contradictory, implausible in relation to the supplied material, or inconsistent with the modelling purpose.

## Explicit task requirements

If the source or task description includes explicit modelling requirements, examine whether they have been satisfied. These may concern:

* required REA element types;
* required economic agents, resources, or events;
* required exchange or conversion processes;
* required relationships or role names;
* required increment or decrement classifications;
* required stockflow types;
* required multiplicities or other business rules;
* required commitments or other REA extensions;
* required source items;
* required assumptions;
* required notation or labels;
* required model perspective, boundary, or level of abstraction;
* minimum or maximum numbers of elements.

Distinguish failure to meet an explicit task requirement from a more general source-alignment weakness. Quote the relevant requirement when identifying non-compliance.

Do not invent requirements that are not contained in the supplied task or source.

## Alignment classifications

Use the following classifications when describing correspondence between source and model:

* **Aligned:** The model adequately represents the relevant source content.
* **Partially aligned:** Some meaning is preserved, but an important part is missing, altered, weakened, or expanded.
* **Missing from the model:** Relevant source content has no identifiable representation.
* **Unsupported addition:** Model content has no identifiable basis in the source and is not stated as an assumption.
* **Contradictory:** The model conflicts with the source.
* **Assumption:** The model extends the source through an explicitly or implicitly introduced supposition.
* **Cannot be determined:** The available material is insufficient for a reliable judgement.

Apply these classifications to particular source statements, model elements, classifications, relationships, constraints, or process structures. Do not assign one classification to the complete model without explaining the individual correspondences on which it is based.

## Validation limits

Base the validation on the supplied model, source material, modelling purpose, selected perspective, and explicit task requirements.

Do not claim that:

* the source itself is factually correct;
* the model is suitable for purposes outside the stated scope;
* every detail in the source belongs in the model;
* an unsupported addition is false merely because it is absent from the source;
* a source omission can be resolved through unstated domain knowledge;
* a missing model element is a weakness unless the omitted source content is relevant to the modelling purpose;
* a reasonable assumption is directly supported by the source;
* an ambiguity can be resolved without evidence;
* internal REA correctness has been established unless REA verification criteria have also been applied.

When the supplied material is insufficient for a definite judgement, state what cannot be determined and why. When a finding concerns both source alignment and internal REA construction, report the validation finding separately from any verification finding.
