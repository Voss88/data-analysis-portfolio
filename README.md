# Thomas Voss — Data Analysis Portfolio

A static portfolio website showcasing data analysis and data science projects, built with pure HTML/CSS/JavaScript and hosted on GitHub Pages.

**Live site:** [www.thomasvoss.co.uk](https://voss88.github.io/data-analysis-portfolio/)

---

## Projects

### 1. Finding Replacement Players in the Transfer Market
`project-live/project-football-transfer-analysis.html`

Using **K-means clustering in R** to find potential replacements for three aging Premier League players (Giroud, Fernandinho, Vardy). Players born after 1997 were grouped by Goals+Assists and Expected Goals+Assists per 90 minutes to identify the closest statistical profile matches among younger talent.

**Stack:** R · K-means Clustering · ggplot2 · Football Analytics

---

### 2. Building a Health Metrics Calculator [1/2] — Functions
`project-live/project-define-health-metrics.html`

A modular Python calculation engine that derives **7 key health metrics** from 5 user inputs (weight, height, age, sex, activity level). Uses the Mifflin-St Jeor equation for BMR and activity multipliers for calorie targets, with each metric isolated as an independent function for maintainability.

**Stack:** Python · Functions · Health & Wellbeing

---

### 3. Building a Health Metrics Calculator [2/2] — GUI
`project-live/project-health-metric-gui.html`

Wraps the calculation engine from Part 1 in a **PyQt5 desktop GUI**. Users input metrics through form fields (text inputs, radio buttons, dropdowns) and receive all 7 health metric results in a formatted display — 5 widget types total.

**Stack:** Python · PyQt5 · Desktop GUI

---

### 4. Using Logistic Regression to Predict Bank Loan Outcomes
`project-live/project-bank-loan-regression.html`

Built a loan approval prediction model using **Logistic Regression** on a mix of raw and engineered features, achieving **75.7% accuracy**. Feature analysis revealed that Credit History is the most influential predictor, while income-related features had surprisingly minimal impact.

**Stack:** Python · scikit-learn · Logistic Regression · Feature Engineering

---

### 5. Building an LLM Chatbot for Car Buyers
`project-live/project-chatbot-llm.html`

Built a chatbot using **GCP, Vertex AI, and Gemini 2.0 Flash** that reads car advert data from AutoTrader's marketplace and answers buyer questions about specific vehicles. Includes guardrails to keep responses polite, accurate, and on-topic while refusing to fabricate information.

**Stack:** Python · GCP · Vertex AI · Gemini 2.0 Flash · LLM · Prompt Engineering

---

## Repository Structure

```
.
├── main-pages/           # Core site pages (index, projects, cv)
├── project-live/         # Individual project article pages
├── project-templates/    # Templates for new project pages
├── project-image/        # Images used in project articles
├── main-page-image/      # Site-wide assets (logo, hero images)
├── icons/                # Icon assets
└── .github/              # GitHub Pages config
```

> **Note:** `private-projects/` and `working-docs/` are excluded from this repository via `.gitignore`.

---

## Tech Stack

| Category | Tools |
|---|---|
| Languages | Python, R|
| ML / Stats | scikit-learn, K-means, Logistic Regression |
| Visualisation | ggplot2, Matplotlib, Seaborn |
| AI / LLM | Vertex AI, Gemini 2.0 Flash, GCP |
| GUI | PyQt5 |

---

## Contact

- **Email:** [thomas_voss@hotmail.co.uk](mailto:thomas_voss@hotmail.co.uk)
- **LinkedIn:** [linkedin.com/in/thomas-voss-30a321172](https://linkedin.com/in/thomas-voss-30a321172)
- **Portfolio:** [www.thomasvoss.co.uk](https://voss88.github.io/data-analysis-portfolio/)
