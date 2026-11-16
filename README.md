# Sara Kamyar

**AI/ML Engineer · Computer Vision · RAG · Python · MSc Computer Engineering, İstinye University**

I build ML systems end to end, from training a model to serving it behind a tested API. Each project reports results on held-out data, says how uncertain they are, and includes what didn't work.

📍 Istanbul · Open to AI/ML engineering internships and junior roles in Türkiye and Europe · [LinkedIn](https://www.linkedin.com/in/sarakamyar/)

## Featured

### 🔬 [Blood Cell VisionOps](https://github.com/SARAHKAMYAR/blood-cell-visionops)

Detects and counts red cells, white cells and platelets in microscopy images, marks each result PASS, REVIEW or FAIL, and writes an LLM report whose numbers are checked against the detector output.

- **0.946 mAP@0.5** on a held-out test set with a fine-tuned YOLO11n, at **18.9 ms per image on CPU** (ONNX)
- **58% lower red-cell counting error** with per-class thresholds chosen on validation data, never on the test set
- **Paired bootstrap confidence intervals** for every model comparison, including the comparisons the test set is too small to resolve
- **Grounded Gemini reports:** a rule-based checker rejects any narrative with an invented or wrong number and falls back to a template
- **70 tests** and Docker builds in CI · audit trail in PostgreSQL · Streamlit review dashboard

`PyTorch` `YOLO11` `ONNX Runtime` `FastAPI` `PostgreSQL` `Gemini` `Docker` · Research use only, not a medical device

<a href="https://github.com/SARAHKAMYAR/blood-cell-visionops"><img src="https://raw.githubusercontent.com/SARAHKAMYAR/blood-cell-visionops/main/docs/assets/dashboard.png" alt="Blood Cell VisionOps review dashboard showing cell counts, QC status and detections" width="720"></a>

### 🏠 [Real Estate RAG Chatbot](https://github.com/SARAHKAMYAR/Real-Estate-RAG-Chatbot)

Answers questions from documents and property listings, citing the sources it retrieved.

- Hybrid search (pgvector + full-text, merged with RRF) and a tool-calling agent that filters listings with SQL
- 17/17 document retrieval checks passed on a fixed evaluation set
- Python and frontend tests in CI

`FastAPI` `PostgreSQL` `pgvector` `Docker` · [▶ Watch the demo](https://github.com/user-attachments/assets/4e3fc3f4-5062-4f06-9774-263bd414f447)

## More projects

| Project | Result | Stack |
|---|---|---|
| [Telco Customer Churn](https://github.com/SARAHKAMYAR/telco-customer-churn) | Chose the decision threshold on validation data: recall rose from 78.3% to 93.0%, with the cost in precision stated | `scikit-learn` `pandas` |
| [Gradient Boosting Benchmark](https://github.com/SARAHKAMYAR/gradient-boosting-classification) | 96.64% test macro-F1 on obesity classification, falling to 85.56% once height and weight were removed. Shows what the model really relies on | `XGBoost` `LightGBM` `CatBoost` |
| [ML Resource Drift Sentinel](https://github.com/SARAHKAMYAR/ml-resource-drift-sentinel) | CLI that fails CI when a dataset's schema breaks. Tested on Python 3.11–3.13 | `Python` `GitHub Actions` |

## Stack

**ML and computer vision:** PyTorch · Ultralytics YOLO · ONNX Runtime · scikit-learn · XGBoost · LightGBM · pandas

**LLM and retrieval:** RAG · hybrid search · pgvector · tool calling · structured outputs · Gemini API

**Engineering:** Python · FastAPI · Pydantic · PostgreSQL · SQL · Docker Compose · GitHub Actions · pytest · Streamlit

**Now:** working toward an MSc thesis in computer vision for medical imaging
