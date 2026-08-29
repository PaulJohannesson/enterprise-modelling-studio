# VDML Verification Criteria

Use the following criteria to verify the internal quality of the submitted VDML exchange diagram.

Verification concerns whether the model is internally coherent, consistently formulated, and constructed according to the modelling rules. It does not determine whether the model accurately or completely represents an external scenario, specification, or other source.

## Participants

In the submitted diagram, you will find a graph with large rectangles and possibly also much smaller rectangles. Each rectangle is intended to correspond to a participant in a business network. 

For each rectangle, examine whether:

* the text in the rectangle does refer to a participant (an participant can be an organisation or an individual)

Examples of participants are: supplier, distributor, bank, IBM.

## Value Propositions

In the submitted diagram, there should be value propositions representing possible resource transfers between participants. These value propositions are represent by labelled small boxes on directed arrows, or labelled arrows.

For each objective, examine whether:

* it quantifies or otherwise makes a goal assessable;
* it measures the property expressed by the associated goal;
* it specifies a measurable target;
* it specifies a target date, deadline, or clearly delimited time frame;
* its central concepts have been operationalised;
* its target population, object, or context is sufficiently clear;
* any baseline needed to interpret an increase or decrease is specified;
* it does not include an activity or solution that belongs in a means.

Operationalisation means specifying how an abstract property will be observed or measured. For example, “Customers are highly satisfied” is not operationalised unless the meaning and measurement of satisfaction are specified.

An objective may contain a numerical value without being adequately measurable. A percentage is insufficient if the population, measurement procedure, baseline, or time frame needed to interpret it is missing.

## Means

For each means, examine whether:

* it describes an action, approach, capability, resource, or other course that can help achieve a goal;
* its contribution to the associated goal is plausible;
* the mechanism through which it supports the goal is sufficiently understandable;
* it is not merely a reformulation of the goal;
* it is not formulated as an already existing fact or external condition;
* it does not unnecessarily duplicate another means;
* it is expressed at an appropriate level of abstraction.

When the contribution depends on an unstated assumption or an intermediate mechanism, identify this as an internal weakness or uncertainty.

## Influencers

For each influencer, examine whether:

* it is formulated as a fact, circumstance, condition, or state that can affect the organisation or its goals and means;
* it is not formulated as a desired state, activity, recommendation, or objective;
* it identifies what exists or occurs, rather than merely stating that something “may” or “could” happen without describing the underlying condition;
* its possible influence on the connected model element is understandable;
* its formulation is sufficiently specific to support its assessment;
* it does not unnecessarily duplicate another influencer.

Verification can determine whether an influencer is formulated as a fact. It cannot determine whether the alleged fact is true without external evidence.

## Strengths, weaknesses, opportunities, and threats

For every classification of an influencer as a strength, weakness, opportunity, or threat, examine whether:

* the classification is clearly shown;
* the classification is plausible from the perspective represented by the model;
* the model makes clear which goal, means, or organisational concern is affected;
* the direction and nature of the influence are understandable;
* an influencer with more than one classification is clearly marked as having multiple effects.

Do not assume that an influencer can have only one classification. The same fact may have different effects on different goals or means, or may have both positive and negative consequences. The model must make such multiple assessments explicit.

## Relationships

For every relationship, examine whether:

* the relationship type is permitted between the connected element types;
* the relationship has the correct direction;
* the relationship has the correct label;
* both endpoints are clearly identifiable;
* the relationship is semantically plausible;
* the relationship expresses a direct contribution, quantification, influence, or other intended connection;
* its interpretation does not depend on an unstated assumption;
* an intermediate element appears to be missing;
* the relationship contradicts another relationship in the model.

In particular, examine whether:

* an objective genuinely quantifies its associated goal;
* a means can plausibly support its associated goal;
* a relationship between goals expresses a coherent contribution or decomposition;
* an influencer can plausibly affect the element to which it is related;
* a strength, weakness, opportunity, or threat classification is consistent with the stated influence.

If the plausibility of a relationship depends on domain information that is not present in the model, identify the relationship as uncertain rather than automatically declaring it incorrect.

## Model structure

Examine the model as a whole for:

* disconnected or isolated elements;
* groups of elements that are not connected to the main goal structure;
* unclear top-level goals;
* incoherent or inconsistent goal hierarchies;
* leaf goals that lack the objectives or means required by the applicable modelling rules;
* duplicated elements;
* contradictory goals, objectives, means, or influencers;
* unexplained circular relationships;
* inconsistent levels of abstraction;
* missing relationships that are strongly implied by the existing elements;
* relationships that bypass an apparently necessary intermediate element.

Do not impose exercise-specific numerical requirements unless those requirements have been supplied separately.

## Language and notation

Examine whether:

* model elements are labelled clearly and concisely;
* the same terminology is used consistently;
* abbreviations are defined;
* spelling and grammar are correct;
* relationship labels are written correctly;
* labels are not incomplete sentence fragments;
* pronouns and references have clear antecedents;
* each label expresses one reasonably coherent idea;
* graphical labels, arrows, and relationship directions are readable and unambiguous.

## Verification limits

Base the verification on the submitted model and the stated BMM modelling rules.

Do not claim that:

* the model is complete in relation to a scenario that has not been provided;
* the model accurately represents stakeholder intentions;
* an influencer is factually true;
* a numerical target is realistic;
* an omitted domain element is required by the source.

These matters require validation against external material or additional domain evidence. When the model alone is insufficient for a definite judgement, state what cannot be determined and why.
