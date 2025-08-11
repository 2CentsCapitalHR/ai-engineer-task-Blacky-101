# Corporate Agent — ADGM Compliance Assistant (Prototype)

This is a prototype AI-powered **Corporate Agent** that assists in reviewing, validating, and helping users prepare documentation for business incorporation and compliance within the **Abu Dhabi Global Market (ADGM)** jurisdiction.

## Features
- Upload `.docx` legal documents
- Automatically detect document type (AoA, MoA, etc.)
- Verify required checklist for **Company Incorporation**
- Detect common **red flags** (e.g., wrong jurisdiction, ambiguous terms, missing signatures)
- Insert **inline comments** into the `.docx`
- Generate **structured JSON report** summarizing findings
- Download reviewed `.docx` and JSON

## Tech Stack
- **UI:** Streamlit
- **Document Processing:** python-docx
- **Optional RAG Support:** OpenAI, ChromaDB, sentence-transformers

## Installation

1. **Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/corporate-agent.git
cd corporate-agent
```

2. **Create a virtual environment**
```bash
python -m venv venv
# Activate it:
# Windows (PowerShell)
venv\Scripts\Activate.ps1
# macOS/Linux
source venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

## Usage
Run the Streamlit app:
```bash
streamlit run app.py
```

- Upload one or more `.docx` files.
- The system will:
  - Detect document type(s)
  - Verify against ADGM checklist
  - Flag potential compliance issues
  - Insert comments and allow `.docx` download
  - Provide a JSON summary

## Example Output (JSON)
```json
{
  "process": "Company Incorporation",
  "documents_uploaded": 4,
  "required_documents": 5,
  "missing_documents": ["Register of Members and Directors"],
  "issues_found": [
    {
      "file": "Articles_of_Association.docx",
      "document_section": "para_3",
      "issue": "Jurisdiction clause does not specify ADGM",
      "severity": "High",
      "suggestion": "Update jurisdiction to ADGM Courts."
    }
  ]
}
```
Screenshots :
![image alt](https://github.com/2CentsCapitalHR/ai-engineer-task-Blacky-101/blob/d3fa9257ca90377a3594aa1b00f03c7464cb1eca/2025-08-11.png)
## Roadmap
- **Tier-2 Upgrade:** Integrate Retrieval-Augmented Generation (RAG) to cite official ADGM regulations for every flagged issue.
- Support for more document categories (Licensing, HR Contracts, Commercial Agreements, etc.)

## License
MIT License
