# AI Reflection – Phase I

## AI-Aided Pair Members
- [First Name] [Last Name] – [Student ID]
- [First Name] [Last Name] – [Student ID]

## 1. Use of Generative AI

We used ChatGPT as an active collaborator throughout the investigation, including research planning, dataset construction, model inference, analysis, and visualization design.

Initially, ChatGPT suggested investigating both negation and contrastive phrasing. We narrowed the scope to negation sensitivity, focusing on differences between originally positive and negative sentences and changes in prediction confidence.

## 2. Influence on the Investigation

ChatGPT helped us develop a controlled sentence-pair generation procedure and suggested additional measurements beyond prediction accuracy, including probability changes, prediction transitions, and confidence changes.

It also suggested several interactive visualizations, which we implemented using Plotly.

The human-only pair independently constructed 16 test pairs and used Matplotlib and Seaborn for static visualizations. Our pair used 51 reviewed pairs and developed four interactive visualization views.

Both approaches identified substantial prediction changes after introducing negation, although the magnitude differed. Since the pairs used different examples and sample sizes, these differences cannot be attributed to GenAI alone.

## 3. Limitations and Verification

Some automatically generated sentence modifications were grammatically awkward or did not negate the intended expression. These examples were filtered through AI-assisted review and required further human verification.

We also learned that high model confidence does not necessarily indicate correct predictions. Modified sentences require separate human assessment before their predictions can be evaluated for correctness.

Additionally, some suggested interpretations and visualizations required refinement after examining the actual results.

## 4. Lessons Learned

GenAI helped us explore additional analytical directions, accelerate implementation, and develop richer interactive visualizations.

However, its suggestions were not always suitable without modification. Dataset quality, numerical results, and interpretations required independent verification.

Overall, GenAI broadened our exploratory process, while critical human evaluation remained essential to producing reliable findings.