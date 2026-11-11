# Phase I – GenAI Interaction Record

**Project:** Investigating Negation Sensitivity in DistilBERT Sentiment Classification

**Model:** `distilbert/distilbert-base-uncased-finetuned-sst-2-english`

**Dataset:** Stanford Sentiment Treebank (SST-2)

**GenAI Tool:** ChatGPT

---

## Interaction 01 – Defining the Research Questions

**Prompt (paraphrased):**

Help us develop our project idea about investigating the effects of negation and contrastive phrasing on a pretrained sentiment classifier. What should we investigate during Phase I?

**AI Suggestions:**

- Investigate how negation changes predicted sentiment.
- Compare positive and negative original sentences.
- Examine the effects of contrastive conjunctions such as "but" and "and".
- Investigate whether reversing clause order affects predictions.
- Examine changes in model confidence.

**Decision:** Accepted the first, second, and fifth suggestions. Rejected the suggestions about contrastive conjunctions and clause ordering to keep the investigation focused on negation sensitivity.

**Impact on Investigation:**

The research scope was narrowed to investigating how negation affects sentiment predictions and whether its effect differs between originally positive and negative sentences. Changes in model confidence will also be examined.

---

## Interaction 02 – Understanding Phase I Requirements

**Prompt (paraphrased):**

Explain how our project should be organized according to the Phase I assignment requirements.

**AI Suggestions:**

- Treat DistilBERT as a black box.
- Focus exclusively on inputs and outputs.
- Use SST-2 validation examples and synthetic inputs.
- Use controlled sentence pairs to investigate linguistic changes.
- Avoid internal representations and token attribution techniques during Phase I.

**Decision:** Accepted.

**Impact on Investigation:**

The suggestions helped distinguish Phase I behavioral analysis from Phase II interpretability analysis and established a focus on controlled input-output comparisons.

---

## Interaction 03 – Designing the Negation Experiments

**Prompt (paraphrased):**

Suggest controlled experiments for investigating how negation affects sentiment classification.

**AI Suggestions:**

- Compare original sentences with versions containing negation.
- Investigate negation in originally positive and negative sentences.
- Keep sentence modifications as controlled as possible.
- Compare predictions before and after introducing negation.

**Decision:** Accepted as the initial experimental direction.

**Impact on Investigation:**

This established the use of paired sentences, allowing model predictions to be compared before and after negation is introduced.

---

## Interaction 04 – Identifying Model Output Measurements

**Prompt (paraphrased):**

What measurements should we collect to investigate how negation affects sentiment classification?

**AI Suggestions:**

- Positive and negative class probabilities.
- Predicted sentiment labels.
- Whether a prediction changes between paired inputs.
- Change in positive probability.
- Change in predicted-class confidence.

**Decision:** Accepted.

**Impact on Investigation:**

These measurements were incorporated into the planned experimental results table to support the investigation of negation sensitivity.

---

## Interaction 05 – Interpreting Initial Model Predictions

**Prompt (paraphrased):**

Why does DistilBERT produce extremely high confidence for a sentence such as "The movie was okay", and why does adding "not" reverse the prediction?

**AI Suggestions:**

- Distinguish model confidence scores from actual prediction correctness.
- Consider the binary nature of SST-2 sentiment classification.
- Investigate whether high confidence persists after predictions change.
- Test additional examples before drawing conclusions.

**Decision:** Accepted.

**Impact on Investigation:**

This introduced an additional analytical question: whether the model's confidence reflects the expected sentiment of a sentence, particularly when negation changes its meaning.

**Experimental Evidence:**

Three initial negation comparisons were tested. All showed substantial changes in positive probability:

- "The movie was okay." → "The movie was not okay.": -0.9996
- "The story and structure are well-honed." → "The story and structure are not well-honed.": -0.9995
- "The acting was excellent." → "The acting was not excellent.": -0.9996

These are preliminary observations from three examples and are not sufficient to establish systematic behavior.

---

## Interaction 06 – Designing the Visualizations

**Prompt (paraphrased):**

Suggest interactive visualizations that could help investigate original versus negated sentiment predictions.

**AI Suggestions:**

1. A scatter plot comparing original and modified positive probabilities.
2. A box plot comparing probability changes between originally positive and negative sentence groups.
3. An interactive sentence explorer for inspecting individual examples.

**Decision:** Accepted as initial visualization concepts.

**Impact on Investigation:**

These suggestions established a possible visualization structure, combining an overview of prediction changes with group comparisons and inspection of individual examples.

The final visualization design will be refined after collecting and exploring the experimental results.

---

## Interaction 07 – Dataset and Experimental Organization

**Prompt (paraphrased):**

How should we organize the experimental inputs and project structure?

**AI Suggestions:**

- Store original and modified sentences in a structured CSV file.
- Record the original sentiment label and source dataset index.
- Record the type of negation modification.
- Store model predictions and analysis results separately.
- Maintain an AI interaction record and a GenAI reflection report.

**Decision:** Accepted.

**Impact on Investigation:**

This helped establish a reproducible experimental workflow and an organized repository structure.

---

## Interaction 08 – Controlled Negation Dataset Construction

**Prompt (paraphrased):**

How should we construct a systematic dataset for investigating
negation sensitivity using SST-2?

**AI Suggestions:**

- Select originally positive and negative SST-2 examples.
- Exclude sentences that already contain explicit negation.
- Prefer sentences with suitable auxiliary verbs.
- Introduce "not" after the first suitable auxiliary verb.
- Manually review modified examples for grammatical correctness
  and semantic ambiguity.

**Decision:** Accepted as the initial dataset construction strategy.

**Impact on Investigation:**

This provides a controlled method for generating paired sentences,
allowing comparisons between original and negated inputs.

The generated examples will be manually reviewed before being
included in the final experimental dataset.

---

## Interaction 09 – Reviewing the Candidate CSV
Prompt (paraphrased): Review the uploaded candidate CSV, accept or reject each original/modified pair based on linguistic suitability, return the reviewed file, and use a distinct filename so it is not overwritten by rerunning the candidate-generation cell.

**AI review criteria:**
- Accept a pair when the modified sentence is reasonably grammatical and “not” meaningfully negates the intended predicate or proposition.
- Do not reject a pair merely because the expected sentiment does not completely reverse. For example, “not terrible” may be neutral or mildly positive; this can be an interesting model-behavior case.
- Reject malformed double-negation outputs, awkward constructions, and transformations where “not” mainly changes an adverb, comparative, or unrelated clause rather than the intended sentiment-bearing expression.
- Make inclusion decisions without looking at the model's predictions, to avoid selecting examples based on the desired outcome.
**Decision:** ChatGPT performed a first-pass linguistic review and assigned accepted or rejected to all 80 candidates. The reviewed file was saved separately as phase1_negation_reviewed_ai_v1.csv.

**Impact:** The review removed unsuitable automatic transformations while retaining valid cases even when negation might not produce a simple positive-to-negative or negative-to-positive reversal. The AI review is a screening aid, not ground truth; the human pair should verify the accepted examples before final analysis.

---

---

## Interaction 10 – Establishing Candidate Review Criteria

**Prompt (paraphrased):**

How should we decide which automatically generated negation pairs should be accepted or rejected?

**AI Suggestions:**

- Accept sentences when the negation is grammatically natural and targets the intended sentiment-bearing expression.
- Reject grammatically incorrect or linguistically unsuitable transformations.
- Do not reject a valid sentence simply because negation does not reverse its sentiment.
- Keep prediction behavior separate from sentence suitability.

**Decision:** Accepted.

**Impact on Investigation:**

The review criteria were refined to avoid selecting examples based on the model's predictions. This ensures that unexpected model behavior remains part of the investigation rather than being excluded from the dataset.

---

## Interaction 11 – AI-Assisted Candidate Review

**Prompt (paraphrased):**

Review the generated SST-2 sentence pairs and classify each transformation as accepted or rejected based on linguistic suitability.

**AI Suggestions:**

Use grammatical correctness and meaningful negation as the main acceptance criteria.

**Decision:** Accepted as a first-pass AI-assisted review.

**Implementation and Outcome:**

A candidate dataset containing 80 sentence pairs was reviewed.

- 51 pairs were accepted.
- 29 pairs were rejected.
- Accepted positive originals: 29.
- Accepted negative originals: 22.

The reviewed dataset was exported as `phase1_negation_reviewed_ai_v1.csv`.

Further human verification remains necessary, particularly for ambiguous or complex constructions.

**Impact on Investigation:**

The review process reduced the initial candidate set to sentences considered suitable for controlled negation comparisons.

---

## Interaction 12 – Batch Inference and Behavioral Measurements

**Prompt (paraphrased):**

How should we process the accepted sentence pairs and systematically measure the effects of negation?

**AI Suggestions:**

- Run inference on original and modified sentences in batches.
- Extract positive and negative class probabilities.
- Compare original and modified predictions.
- Calculate changes in positive probability and predicted-class confidence.
- Identify prediction flips.

**Decision:** Accepted and implemented.

**Experimental Outcome:**

Inference was performed on 51 accepted sentence pairs.

The resulting analysis showed:

| Measurement | Originally positive | Originally negative |
|---|---:|---:|
| Number of pairs | 29 | 22 |
| Mean original positive probability | 0.9593 | 0.0914 |
| Mean modified positive probability | 0.1385 | 0.5086 |
| Mean probability change | -0.8208 | +0.4172 |
| Prediction flip rate | 89.66% | 54.55% |
| Mean confidence change | -0.0182 | -0.0551 |

**Impact on Investigation:**

The results revealed a possible asymmetry in how the model responds to negation depending on the original sentiment of the sentence. This became a central direction for further analysis.

---

## Interaction 13 – Visualization Design and Implementation

**Prompt (paraphrased):**

Suggest interactive visualizations for comparing original and modified sentiment predictions and investigating changes in confidence.

**AI Suggestions:**

- A scatter plot comparing original and modified positive probabilities.
- A box plot comparing probability changes across original sentiment groups.
- A prediction-transition visualization.
- A confidence-change distribution.
- An interactive inspection of exceptional sentence pairs.

**Decision:** The scatter plot and group-comparison approach were implemented as the initial visualization. Additional views were proposed for further exploration.

**Implementation Outcome:**

The scatter plot showed a visible separation between originally positive and negative examples and revealed several unusual prediction patterns.

The plot also showed that many predictions were concentrated near extreme probability values, making individual example inspection important.

**Impact on Investigation:**

The visualization moved the analysis beyond aggregate measurements by allowing individual sentence pairs and their probability changes to be examined.

---

## Interaction 14 – Visualization Debugging

**Prompt (paraphrased):**

Help resolve a Plotly visualization error stating that `nbformat>=4.2.0` is required.

**AI Suggestion:**

Install the missing notebook rendering dependencies and restart the kernel.

**Decision:** Accepted.

**Outcome:**

The missing dependencies were installed, allowing Plotly visualizations to render in the local Jupyter environment.

**Impact on Investigation:**

This resolved an implementation issue and enabled visual exploration of the experimental results.

---

## Interaction 15 – Interpreting Prediction Transitions

**Prompt (paraphrased):**

Interpret the scatter plot and prediction-transition results, and suggest further analyses.

**AI Suggestions:**

- Compare prediction transitions separately for originally positive and negative sentences.
- Distinguish prediction changes by direction rather than reporting only overall flip rates.
- Examine changes in confidence.
- Investigate examples that behave differently from the dominant pattern.
- Examine whether linguistic structures distinguish exceptional examples.

**Decision:** Accepted as further investigative directions.

**Impact on Investigation:**

The analysis was extended to distinguish positive-to-negative and negative-to-positive transitions. Additional visualizations and sentence-level inspection were proposed to investigate the observed asymmetry.

---

---

## Interaction 16 – Investigating Prediction Transitions

**Prompt (paraphrased):**

How can we investigate the direction of prediction changes after introducing negation, rather than only reporting the overall prediction flip rate?

**AI Suggestions:**

- Separate positive-to-negative and negative-to-positive transitions.
- Compare unchanged predictions across originally positive and negative sentences.
- Use a stacked bar chart to compare transition percentages between the two groups.

**Decision:** Accepted.

**Implementation:**

A stacked bar chart was developed using the original and modified predictions for all accepted sentence pairs.

**Impact on Investigation:**

This visualization makes differences in prediction transitions between originally positive and negative sentences easier to compare.

---

## Interaction 17 – Investigating Confidence Changes

**Prompt (paraphrased):**

How can we visualize whether negation affects the model's confidence differently for originally positive and negative sentences?

**AI Suggestions:**

- Compare the change in predicted-class confidence across the two original sentiment groups.
- Use box plots to investigate the distribution of confidence changes.
- Display individual sentence pairs to identify unusual behavior.

**Decision:** Accepted.

**Implementation:**

A box plot with individual data points was proposed to compare confidence changes across originally positive and negative sentence groups.

**Impact on Investigation:**

This extends the analysis beyond changes in predicted sentiment and allows us to investigate whether confidence changes consistently across the two groups.

---

## Verification and Remaining Limitations

The numerical observations were obtained from the actual DistilBERT inference results.

AI-generated interpretations are treated as hypotheses rather than ground truth.

The candidate review was AI-assisted and requires human verification. The modified sentences also require separate human sentiment annotations before prediction correctness can be assessed.

Further interactions and findings will be documented as the investigation progresses.

---
## Verification and Limitations

The suggested analytical directions and interpretations will be evaluated against actual DistilBERT outputs.

**In particular:**

- Initial experiments contain too few examples to support systematic conclusions.
- Modified sentences do not automatically inherit the original SST-2 labels.
- Some negated sentences may be ambiguous or unnatural.
- High model confidence does not necessarily indicate correct sentiment.
- Visualization suggestions must be evaluated using the actual experimental data.

Further interactions, analytical decisions, accepted or rejected suggestions, and experimental outcomes will be documented as the investigation progresses.