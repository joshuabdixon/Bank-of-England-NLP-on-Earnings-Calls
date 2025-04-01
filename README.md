## Bank of England & University of Cambridge NLP Project
**Harnessing Retrieval-Augmented Generation (RAG) for Financial Risk Analysis**

This repository focuses on the **RAG** component of a collaborative AI project. It uses **2024 quarterly earnings call transcripts from JPMorgan Chase and Deutsche Bank** to demonstrate how NLP can help detect early warning signs of financial distress.

---

### Project Overview
- **Objective**: Utilise **RAG** to extract and summarise key risk indicators from banks’ earnings calls.  
- **Approach**:  
  - **Topic Modelling & Summaries** – Identify major themes in Q&A sessions.  
  - **Retrieval-Augmented Generation** – Store embedded text in a FAISS index for rapid, context-aware answers.  
  - **Use Case** – Enhances oversight by surfacing language clues indicative of financial health or instability.

#### My Role
- **Project & Strategic Leadership** – Aligned stakeholders’ goals (Bank of England & Cambridge) into a clear roadmap.  
- **RAG Pipeline Development** – Built an end-to-end flow, from data extraction to embedding and querying.  
- **Team Coordination** – Oversaw development milestones, code reviews, and timely prototype delivery.

---

### Repository Structure

```
1_data/
├── [Raw quarterly earnings call PDFs]
2_extracted_data/
├── [Q&A segments extracted from PDFs]
3_processed_json/
├── [Processed JSON data post NLP pipeline]
4_processed_json_correct_pages/
├── [Corrected JSON metadata]
```

- **1_data/**: Place raw transcripts here. After running the notebooks in sequence, outputs appear in the subsequent folders automatically. This user-friendly workflow minimises manual effort.

---

### Repository Contents

1. **pdf_QnA_section_extractor.ipynb**  
   - Extracts Q&A segments from each PDF in `1_data/`. Outputs to `2_extracted_data/`.
2. **Q&A_pdf_to_json.ipynb**  
   - Converts extracted text into structured JSON and saves to `3_processed_json/`.
3. **JSON_page_number_update_folder_based.ipynb**  
   - Corrects page references in JSON, finalising data in `4_processed_json_correct_pages/`.
4. **rag_stable_output.ipynb**  
   - Demonstrates the RAG pipeline, using FAISS to deliver context-rich answers from the final JSON data.

---

### Setup & Installation
1. **Python 3.7+ Environment**  
2. The full list of required packages is maintained in the **requirements.txt** file.
3. **Install**:  
   ```bash
   pip install -r requirements.txt
   ```
4. **API Keys**:  
   - Store any required keys (e.g. OpenAI, as shown in code) in a `.env` file. See `env.template` for guidance.

---

### Usage
1. **Data Extraction**  
   - Run `pdf_QnA_section_extractor.ipynb` to scan PDF transcripts in `1_data/` and generate Q&A text.  
2. **JSON Conversion**  
   - Use `Q&A_pdf_to_json.ipynb` to produce structured JSON in `3_processed_json/`.  
3. **Page Number Updates**  
   - Execute `JSON_page_number_update_folder_based.ipynb` to correct references in `4_processed_json_correct_pages/`.  
4. **RAG Pipeline**  
   - Open `rag_stable_output.ipynb` for an end-to-end demonstration of FAISS-based retrieval and summarisation.

---

### Known Issues & Future Improvements
- **Parsing Errors**: Occasional JSON parsing issues; planning to enhance robustness.  
- **API Responses**: Improved handling of model outputs to reduce manual post-processing.  
- **Predictive Analytics**: Potential for linking sentiment/topic trends to future financial outcomes.  
- **Scalability**: Further integration into regulatory pipelines and expansion to additional institutions.

---

### Acknowledgements
Many thanks to the Bank of England and the University of Cambridge for their guidance and collaboration. This RAG-focused work aims to streamline regulatory oversight, offering timely, data-driven insights into financial health. Special thanks to my teammates for their invaluable contributions to building this innovative NLP solution.