SentinelAI – The AI Guard

🔐 “Protecting privacy without sacrificing data utility.”
SentinelAI is a local-first PII anonymization and evaluation framework built to detect and anonymize Personally Identifiable Information (PII) in text or CSV files — all securely processed on your device.

🚀 Overview

This project provides a robust, hybrid solution for detecting and anonymizing PII in unstructured and semi-structured text data.
It combines spaCy’s Named Entity Recognition (NER), regular expressions (Regex), contextual rules, and custom overrides for highly accurate and explainable anonymization.

Unlike traditional, cloud-dependent anonymizers, SentinelAI is local-first — ensuring sensitive data never leaves your system.

🧠 How It Works

The framework follows a two-step pipeline:

Anonymization: Detect and replace PII entities using hybrid NLP-based and rule-based logic.

Evaluation: Compute quantitative metrics (Precision, Recall, and F1-Score) to assess anonymization quality.

Here’s the flow:

flowchart LR
A[Input Text/CSV] --> B[PII Detection: spaCy NER + Regex + Rules]
B --> C[Anonymization & Replacement]
C --> D[Evaluation: Precision, Recall, F1]
D --> E[Anonymized Output + JSON Log]

⚙️ Key Features
Feature	Description
🧩 Multi-Layered PII Detection	Combines spaCy NER, Regex, and contextual rules for comprehensive PII coverage.
⚖️ Confidence-Based System	Assigns confidence scores and prioritizes high-certainty detections.
🔄 Overlap Resolution	Handles overlapping entities intelligently by prioritizing higher-confidence spans.
📜 Anonymization Logging	Generates a JSON log mapping each detected PII entity to its anonymized placeholder.
🧪 Evaluation Metrics	Calculates Precision, Recall, and F1-Score for performance validation.
🔁 Second-Pass Anonymization	A follow-up layer to capture regex-definable PII missed in the first pass.
🧰 Project Structure
│
├── anonymizer.py          # Core anonymization logic (NER + regex + contextual rules)
├── main_script.py         # Entry point for anonymization & evaluation
├── final_dataset.csv      # Example input dataset
├── anonymized_output.csv  # Example anonymized output
├── anonymization_log.json # Log file mapping original → anonymized text
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation

⚡ Quick Start
🔹 1. Clone the Repository
git clone https://github.com/shashanktyagi0946/SentinelAI-The-AI-Guard.git
cd SentinelAI-The-AI-Guard

🔹 2. Install Dependencies
pip install -r requirements.txt

🔹 3. Download the spaCy Language Model
python -m spacy download en_core_web_lg

🔹 4. Run the Anonymizer

Edit main_script.py to include your input file paths:

input_file = "final_dataset.csv"
output_file = "anonymized_output.csv"
log_file = "anonymization_log.json"


Then run:

python main_script.py


✅ The anonymized output will be saved, and performance metrics (Precision, Recall, F1-Score) will be displayed in the console.

🧾 Example Output
Original Data	Anonymized Output
Liu Zhou, liu.zhou@mail.net
, +86-1573230, "Tower 418, High Street, Shanghai", China	PERSON_3890, EMAIL_REDACTED, +86-1296037, "Building 589, LOC_109, Shanghai", China

📘 Every anonymization step is logged in anonymization_log.json for transparency.

💡 Interactive Ideas (for GitHub Visitors)

Want to experiment? Try the following:

✍️ Add your own sentences with names, emails, or phone numbers to the dataset — see how SentinelAI anonymizes them.

🧪 Adjust confidence thresholds and observe how Precision vs. Recall changes.

🧠 Extend regex rules to detect custom PII formats (e.g., medical IDs, license numbers).

🧩 Tech Stack

Language: Python 🐍

Libraries: spaCy · Regex · Faker · JSON · Pandas

Model: en_core_web_lg

🛠️ Future Enhancements

🧱 Support for semi-structured data (JSON, XML)

🔁 Continuous improvement loops via feedback-based retraining

🧮 Contrastive learning for context-sensitive disambiguation
