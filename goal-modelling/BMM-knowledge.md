# BMM Knowledge

## Purpose and applicability

This component provides declarative knowledge about the Business Motivation Model (BMM) as used for goal modelling in these prompts. It centralises the definitions, semantic distinctions, modelling rules, and conventions shared by verification and validation.

The selected task component determines which assessment is performed and which evidence is admissible. Including this knowledge does not by itself request verification or validation. The shared role component determines the coaching approach, and the selected feedback-mode component determines presentation and interaction.

The scope is goals, objectives, means, influencers, SWOT assessments, their relationships, model structure, and notation. This is the goal-modelling profile used by the original prompt components, including their broad use of the term **means**. It does not impose the inclusion of every construct in the full BMM specification.

### Status of the statements

- **Definitions** specify the meanings of constructs in this profile.
- **Rules** specify required semantic or structural conditions within their stated scope.
- **Conventions** guide clarity, consistency, and appropriate abstraction. A departure requires interpretation in context and is not automatically a formal rule violation.
- **Examples** illustrate meanings without imposing requirements on another model.

Explicitly supplied notation and task requirements establish any additional conventions, mandatory relationships, or completeness conditions. Case-specific facts, numerical targets, and stakeholder intentions come from the submitted material; they are not supplied by examples in this component.

## Goals

**Definition.** A goal describes a desired state of affairs: an end that an organisation or another relevant actor wants to achieve or maintain.

**Rules.** A goal expresses the desired outcome itself. Its meaning must remain distinguishable from an activity or approach for achieving it, a measurable objective, an existing circumstance, and a directive prescribing particular behaviour.

For example, **Customers are satisfied with the service** expresses a desired state. **Conduct customer surveys** describes an activity and has the character of a means. **Customers currently report dissatisfaction with the service** describes an existing circumstance.

The semantic role depends on the statement's meaning, classification, and context. Present-tense wording can express a desired state when the model identifies it as a goal. Words such as **should**, **shall**, or **to** do not determine the classification by themselves; a requirement can express a desired state or prescribe a particular action.

**Conventions.**

- The actor, object, quality, or outcome relevant to the goal is sufficiently clear.
- Each goal expresses one coherent desired state or an explicitly related combination of states.
- Connected goals have understandable levels of abstraction.
- Goals avoid unnecessary duplication and preserve meaningful distinctions.
- Goals are mutually compatible, or any competing aims and trade-offs are made explicit.

A broad goal need not contain the numerical target or deadline required of an objective. Its formulation must nevertheless identify the desired property clearly enough to support meaningful refinement and assessment.

## Objectives

**Definition.** An objective specifies an assessable target associated with a goal. It makes the relevant desired property measurable and time-targeted.

**Rules.** An objective must:

1. Specify a target whose achievement can be assessed.
2. Measure the property expressed by its associated goal.
3. Specify a target date, deadline, or clearly delimited time frame.
4. Operationalise its central concepts sufficiently to determine whether the target is met.
5. Identify the relevant population, object, or context clearly enough to interpret the target.
6. State any baseline needed to interpret a claimed increase, decrease, or other comparison.
7. Keep the desired result distinguishable from the activity or solution used to achieve it.

**Operationalisation** specifies how an abstract property will be observed or measured. Relevant details may include an indicator, data source, measurement procedure, scale, threshold, population, and observation period. Which details are necessary depends on the objective; they may be provided in an unambiguously linked explanation rather than repeated in every label.

For example, **At least 90% of respondents to the post-service survey during December 2027 rate their overall satisfaction at 4 or 5 on the stated five-point scale** identifies a target, measured population, observation period, and interpretation of satisfaction. It measures satisfaction among those respondents; extending the claim to all customers would require an additional basis.

A numerical value alone does not establish adequate measurability. **Satisfaction increases by 20%** leaves the measure, comparison baseline, population, and time frame unresolved. Relative time frames also require an identifiable reference point when their interpretation depends on one.

An objective can use a clearly defined yes-or-no criterion when this makes achievement assessable; the mere presence or absence of a percentage is not decisive. A proxy measure needs an understandable connection to the goal: counting completed surveys, for example, does not by itself measure customer satisfaction.

Targets are intended to be achievable, but their numerical appearance does not establish that they are realistic. Their operational clarity and internal consistency can be considered separately from their empirical attainability.

## Means

**Definition.** In the teaching profile used here, a means is an action, approach, capability, resource, or other course employed or proposed to help achieve a goal. Its role concerns how an end can be achieved.

**Rules.**

- A means has a plausible contribution to its associated goal or other explicitly identified end.
- The mechanism through which it supports that end is sufficiently understandable from the model and its explanations.
- A means contributes something beyond merely restating the desired result.
- Its intended use or action remains distinguishable from a statement that an existing fact or external condition simply holds.

For example, **Provide staff training in complaint handling** identifies an action that may support service-related goals. **Improve service quality**, when attached to a goal expressing the same desired improvement, may leave the actual means unspecified.

An existing capability and a proposed use of that capability have different roles. A statement about what the organisation currently possesses may function as an influencer; a statement about employing it to achieve an end may function as a means. The label and explanation establish the intended interpretation.

**Conventions.** The responsible actor and relevant object or recipient are identifiable where needed. Means avoid unnecessary duplication, use a coherent level of abstraction, and make significant assumptions or intermediate mechanisms explicit.

A plausible contribution does not imply guaranteed achievement. Where the connection depends on undisclosed domain facts or assumptions, its plausibility remains uncertain.

## Influencers

**Definition.** An influencer is a fact, circumstance, condition, or state that can affect the organisation, its goals, or its means.

**Rules.**

- An influencer identifies an alleged circumstance or underlying condition, with sufficient context to understand what exists or occurs.
- It remains distinguishable from a desired state, prescribed action, recommendation, or objective.
- Its possible influence on the connected organisational concern is understandable.
- Its formulation is specific enough to support an assessment of that influence.

A bare statement that something **may** or **could** happen can leave the underlying circumstance unspecified. Uncertainty may nevertheless be part of a properly described condition, such as the existence of a forecast. Making the statement precise does not justify converting uncertainty into certainty.

For example, **The latest customer survey reports long response times** alleges an existing circumstance. **Response times should be short** expresses a desired state or requirement. **Introduce a new support system** proposes an action.

**Convention.** Influencers use consistent terminology, have identifiable referents, and avoid unnecessary duplication. When internal or external classification is used, the organisational boundary must be identifiable.

An influencer's formulation as a factual statement is separate from the truth of that statement. The model alone does not establish that the alleged circumstance actually holds.

## Assessments and SWOT

**Definition.** An assessment expresses a judgement about how an influencer affects an end or means. BMM distinguishes the circumstance from its assessment; SWOT is one supported categorisation of assessments. Strength concerns an internal advantage, weakness an internal inadequacy, opportunity a potentially favourable impact, and threat a potentially unfavourable impact. [OMG BMM 1.3, Sections 8.5.5–8.5.6](https://www.omg.org/spec/BMM/1.3/PDF#page=55).

In the simplified notation used by these prompts, a SWOT classification may appear directly on an influencer or its relationship. Such notation expresses an assessment of the influencer in context. It does not make the circumstance inherently positive or negative, and it does not require a separate assessment box unless the supplied notation or task requires one.

**Rules.** For each SWOT assessment:

- The classification is clearly identifiable.
- The organisational perspective and affected goal, means, or concern are clear enough to interpret it.
- The classification is plausible in relation to the stated influence.
- The direction and nature of the effect are understandable.
- Multiple classifications or effects remain distinguishable when they are represented.

The same circumstance can support different assessments for different goals, means, perspectives, or effects. For example, increased demand may favour a sales goal while making a response-time goal harder to achieve. Multiple assessments are not contradictory merely because one is positive and another negative.

SWOT labels alone do not explain an influence. The model's relationship and context establish why the circumstance is assessed in that way. Alternative assessment categories are relevant only when supported by the supplied profile or task; this reference introduces no requirement to use every SWOT category.

## Relationships

**Definition.** A relationship expresses a particular semantic connection between identifiable model elements. Its meaning is determined by its type, endpoints, label, direction, and the declared notation.

**Rules.**

- The connected element types support the stated relationship meaning under the applicable notation.
- Both endpoints, the relationship label, and the intended direction are identifiable.
- The particular relationship is semantically plausible; the fact that both elements appear in a diagram does not itself establish a connection.
- A relationship is consistent with the meanings of the connected elements and with other relationships in the model.
- Any assumption or intermediate condition essential to interpreting the relationship is identifiable.

The principal relationship meanings in this goal-modelling profile are:

| Relationship meaning | Semantic interpretation |
|---|---|
| Objective quantifies or makes a goal assessable | The objective measures the desired property expressed by the goal. |
| Means supports an end | The action, approach, or employment of a capability or resource plausibly contributes to the intended result. |
| Goal contributes to another goal | Achieving one desired state plausibly helps achieve another, without merely repeating it. |
| Goal is decomposed into more specific goals | The connected goals express coherent refinements or parts of the broader desired state. |
| Influencer is assessed as affecting an end or means | The relationship expresses an identifiable effect of the circumstance on the relevant concern, with its assessment explicit or represented through the documented shorthand. |

This table describes semantic roles; it does not prescribe one graphical arrow direction for every notation. For example, **contributes to** and **is supported by** express their arguments in different orders. Relationship labels and arrowheads must be interpreted using the supplied convention, rather than a universal assumption that all arrows point towards a top-level goal.

Contribution, decomposition, quantification, and influence express different connections. A direct contribution does not automatically mean that it is sufficient or necessary for achievement. An intermediate element is needed when its absence changes or obscures the stated meaning; every conceivable causal step need not appear.

A type, label, or arrow convention not specified by the supplied knowledge or notation has an unresolved interpretation. Familiarity with a different notation does not establish an error in the submitted one.

## Model structure and abstraction

**Rules.** The model's goals, objectives, means, influencers, assessments, and relationships must form a coherent interpretation within the stated scope. Incompatible targets or claims concerning the same subject, conditions, and period require resolution or an explicit account of alternatives.

**Conventions.**

- Top-level goals and the organisation of the goal structure are identifiable.
- Connected goals form understandable hierarchies, refinements, or contribution structures.
- Isolated elements and groups have an identifiable role within the model's scope.
- Duplicate elements have a justified purpose and preserve their identity.
- Abstraction levels remain understandable across connected elements.
- Circular relationships have a clear interpretation rather than unexplained circular justification.
- Relationships needed to express a connection strongly implied by the model are present or their omission is explained.
- Relationships do not bypass an intermediate element essential to their meaning.

An element's isolation, a cycle, or the presence of several top-level goals is a reason to examine the structure, not an automatic formal violation. A model may represent alternatives, separate concerns, or an intentionally partial view when their roles are clear.

**Conditional completeness rule.** A leaf goal must have the objectives or means required by the explicitly applicable modelling rules or task requirements. This component does not impose an unconditional requirement for every leaf goal to have both, nor does it prescribe minimum or maximum element counts.

## Language and notation

**Conventions.**

- Labels are clear, concise, grammatically interpretable, and correctly spelled.
- Each label conveys one reasonably coherent idea without omitting words essential to its meaning.
- Terminology is consistent, and abbreviations are defined or unambiguous in context.
- Pronouns, shortened names, and other references have clear antecedents.
- Important distinctions are preserved when labels are shortened, combined, or reformulated.
- Relationship labels are written correctly and match their intended meanings.
- Element classifications, graphical labels, arrowheads, endpoints, and relationship directions are readable and unambiguous.

A concise noun phrase can be an adequate label when its meaning is complete in context. An incomplete fragment that leaves the proposition or referent unclear is a different matter. Presentation preferences alone do not establish a semantic error.
