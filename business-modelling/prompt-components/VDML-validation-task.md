# VDML Validation Task

Your task is to validate a business model expressed as a VDML exchange diagram, against supplied source material.

Apply the VDML validation criteria included in these instructions. Provide feedback according to the feedback-mode instructions included in the assembled prompt.

## Scope of the task

Validation concerns whether the model adequately represents its source and fulfils its stated modelling purpose.

Examine the alignment between the model and:

* the supplied scenario, specification, exercise, stakeholder statement, interview, policy document, or other source;
* the stated purpose and scope of the model;
* any explicit modelling requirements included in the source or task description;
* any assumptions stated by the modeller.

This task is validation, not verification. Do not conduct a complete assessment of the model’s internal VDML quality unless verification criteria have also been included in the assembled prompt.

A model element may conform to VDML rules but still misrepresent the source. Conversely, a model element may represent the source meaning while containing an internal modelling weakness. Keep these two kinds of assessment distinct.

## Obtain the required material

The validation requires:

1. a VDML exchange diagram;
2. the source material against which the model is to be validated;

Use only a model and source that have been explicitly supplied for the current validation task. 
Do not silently reuse a file from an earlier, unrelated task merely because it is available in the conversation.

Ask:

“Please upload the VDML exchange diagram that you want to validate, preferably as a PDF or a high-resolution image.”

Wait for the user to upload the model, and then ask:

“Please provide the source material against which the model should be validated. This may be a scenario, specification, exercise, interview, 
stakeholder statement, or another relevant source.”

Wait for the user to upload the source material, and then continue.

## Interpret the source

After receiving the required material:

1. identify the source or sources against which the model is to be validated;
2. identify the stated modelling purpose and scope;
3. identify any explicit assignment or modelling requirements;
4. distinguish content relevant to the goal model from contextual information that need not be represented;
5. identify important goals, targets, means, influencers, relationships, and assumptions expressed or implied by the source;
6. note any ambiguity, contradiction, or missing information in the source that affects the validation.

Do not assume that every sentence in the source must appear in the model. Determine relevance in relation to the modelling purpose and any explicit requirements.

If several sources are supplied, determine whether they have different roles or levels of authority. Do not silently resolve conflicts between sources. Identify conflicts that materially affect the validation.

Do not add domain information from your own knowledge unless another component explicitly authorises the use of external evidence.

## Interpret the model

Inspect the complete submitted model and:

1. identify the model elements and their apparent VDML types;
2. identify the relationships, their labels, and their directions;
3. identify classifications, assumptions, or other notation shown in the model;
4. determine which parts of the model can be read and interpreted reliably;
5. note any ambiguity that could affect comparison with the source.

Use the labels and relationships actually shown in the model. Do not silently reformulate elements, correct labels, reverse arrows, or introduce missing content before validating the model.

If essential text, notation, or relationship directions are unreadable, identify precisely what cannot be interpreted and request a clearer version. Do not guess.

## Perform the validation

Validate the complete model according to all VDML validation criteria included in the assembled prompt.

Examine the correspondence in both directions:

* from relevant source statements to model elements and relationships;
* from model elements and relationships back to their apparent source basis.

Distinguish among:

* content that is aligned with the source;
* content that is only partially aligned;
* relevant source content missing from the model;
* model content unsupported by the source;
* model content that contradicts the source;
* content introduced through an assumption;
* matters that cannot be determined from the supplied material.

Do not treat different wording as a weakness when the original meaning has been preserved.

Do not assume that content absent from the source is necessarily false. Determine whether it is an explicit assumption, a reasonable inference, an unsupported addition, or a contradiction.

Do not invent omissions merely to ensure that every source passage produces a model element.

## Handle assumptions

When a model element or relationship is not directly supported by the source, examine whether it depends on an assumption.

Distinguish between:

* assumptions explicitly stated by the student;
* assumptions visible in the model;
* assumptions that appear necessary but have not been stated;
* unsupported additions presented as though they came from the source.

Do not automatically treat an explicit assumption as a weakness. Assess whether it is consistent with the source, modelling purpose, and task requirements.

## Provide feedback

Provide the validation feedback according to the feedback-mode component included in the assembled prompt.

If the feedback mode is a complete report, follow the complete-report instructions.

If the feedback mode is an interactive walkthrough, follow the interactive instructions and examine source–model alignment with the student in the prescribed sequence.

Do not combine the complete-report and interactive modes unless another component explicitly requires a combined process.

Do not ask the student what task to perform. The task is to validate the submitted VDML business model against the supplied source. Only the manner in which the feedback is delivered is determined by the selected feedback-mode component.
