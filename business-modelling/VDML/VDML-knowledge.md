# VDML Knowledge

## Purpose and applicability

This component describes the concepts, semantics, structural rules, and modelling conventions used in these prompts for business models expressed as VDML exchange diagrams. VDML stands for Value Delivery Modeling Language. The scope of this component is participants and the value propositions exchanged between them; other VDML views and constructs fall outside this reference.

This is shared reference knowledge for verification, validation, and other explicitly specified modelling tasks. The selected task component determines which assessment is performed, which evidence is admissible, and how this knowledge is applied. Including this component does not by itself request verification or validation. The shared role component determines the coaching approach, and the selected feedback-mode component determines presentation and interaction.

The definitions and rules below describe the exchange-diagram convention used by these prompt components. In particular, the interpretation of value propositions as possible resource transfers and the requirement for reciprocal value propositions belong to this convention. They should not be presented as an exhaustive specification of VDML.

### Status of the statements

- **Definitions** specify the meanings of the constructs used here.
- **Rules** specify required semantic or structural conditions within this exchange-diagram convention.
- **Conventions** guide clarity and consistency; a departure is not automatically a formal rule violation.
- **Examples** illustrate meanings without imposing requirements on another model.

Case-specific participants, offerings, business arrangements, and assignment requirements come from the supplied task, model, or source material. Examples in this component do not establish such facts.

## Exchange diagrams

**Definition.** An exchange diagram represents a business network through its participants and directed value propositions, showing what participants may provide to one another.

The diagram expresses possible resource transfers. An arrow alone does not establish that a transfer has already occurred, specify the time of an occurrence, or define a sequence of activities.

**Convention.** The diagram's scope, level of abstraction, and relationship to any accompanying diagrams are identifiable. If several diagrams are supplied, they may represent alternative models, complementary parts of a model, or different views; their relationship affects how their content can be interpreted together.

## Participants

**Definition.** A participant is an organisation or individual taking part in the represented business network. A participant label may identify a named party or a generic role or category of party.

Examples include **Supplier**, **Distributor**, **Bank**, and **IBM**. A role label such as **Supplier** identifies a participant through its role; a name such as **IBM** identifies a particular organisation.

**Notation.** Participants are represented by rectangles, which may differ in size. Small boxes attached to arrows may instead label value propositions. Size alone therefore does not establish an element's type; position, connections, labels, and any supplied legend determine its interpretation.

**Rule.** Every rectangle interpreted as a participant must denote an organisation or individual, either specifically or through a role or category. A resource, activity, goal, or offering does not become a participant merely because it appears inside a rectangle.

**Conventions.**

- A participant's label identifies its intended referent clearly enough to understand its exchanges.
- Names and abbreviations are used consistently across the diagram and its accompanying explanations.
- Distinct roles and distinct parties remain distinguishable when that distinction matters to the model's meaning.
- Repeated representations of the same participant have an identifiable purpose, such as supporting a readable layout, and preserve the participant's identity.

## Economic resources

**Definition.** An economic resource is a resource that can be under the control of a participant and can be traded between participants.

Examples may include goods, money, services, or rights offered by one participant to another. Their interpretation depends on what is being provided, rather than merely on the wording of a label.

An economic resource is conceptually distinct from:

- the participant that controls, provides, or receives it;
- the activity through which it is produced or delivered;
- a desired outcome associated with receiving it;
- a message or record that merely describes a transfer.

For example, a **Transport company**, its **Transport service**, and an activity labelled **Transport goods** express different meanings. Information or a document may itself be an offered resource when its economic interpretation supports this; being an information item alone neither establishes nor excludes resource status.

## Value propositions

**Definition.** In the exchange-diagram convention used here, a value proposition represents a possible transfer of an economic resource from one participant to another.

**Notation.** A value proposition is shown as a labelled directed arrow or as a labelled small box on a directed arrow. The arrow runs from the providing participant to the receiving participant.

**Rules.**

1. Each value proposition has an identifiable providing participant and receiving participant.
2. Each value proposition specifies the economic resource that may be transferred.
3. Each value proposition has an identifiable description whose meaning is consistent with its label, direction, connected participants, and the other relevant parts of the diagram.
4. Each value proposition satisfies the reciprocity rule below.

A sufficiently informative label can supply the description; accompanying text may explain it further. The description requirement does not by itself prescribe a separate document or a minimum length.

**Conventions.**

- Labels make it possible to identify what is offered, such as **Goods**, **Payment**, or **Transport service**.
- Arrow direction consistently expresses provision and receipt throughout the model.
- A label's meaning is interpreted together with its connections and any accompanying explanation. Grammatical form alone does not establish a semantic error.
- A participant's name or a desired benefit alone may leave the offered resource unclear. For example, **Satisfied customers** describes a desired state without identifying what one participant transfers to another.

## Reciprocity

**Rule.** For every value proposition from participant A to participant B, the diagram must contain a reciprocal value proposition from B to A. The reverse direction must connect the same two participants.

For example, **Goods** from a supplier to a buyer may have **Payment** from that buyer to that supplier as its reciprocal value proposition. A transfer from a third participant to the supplier does not satisfy this particular rule for the supplier-buyer pair.

Both directions must have meaningful resource interpretations. Two opposing arrows establish the required direction pattern, but their labels and descriptions must also satisfy the other value-proposition rules.

This rule requires a reciprocal offering between the participants. It does not by itself require equal monetary amounts, simultaneous transfers, or a separate return arrow for each individual offering when one return proposition covers several offerings. A reciprocal proposition is not necessarily monetary.

The rule belongs to the exchange-diagram convention defined here. A business arrangement described in a source may be more complex than this convention captures; such a case requires an explicit account of the representation's scope and limits.

## Internal consistency and clarity

**Rule.** The model's labels, connections, directions, and accompanying descriptions must not express incompatible meanings for the same participant or value proposition.

**Conventions.**

- The same term has a consistent meaning, while synonyms and abbreviations have identifiable referents.
- Merging several participants or offerings, or splitting one into several elements, preserves the intended distinctions and has an understandable basis.
- Endpoints, arrowheads, labels, and the association between a small label box and its arrow are readable and unambiguous.
- A legend or accompanying explanation makes additional notation interpretable.
- Visual differences, such as rectangle size, do not imply semantic distinctions unless the notation or explanation establishes them.

The number of participants or value propositions, required names, and other assignment-specific conditions are determined by explicit task requirements. This knowledge component imposes no minimum or maximum element count.
