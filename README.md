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

### ⚖️ [Groundtruth](https://github.com/SARAHKAMYAR/groundtruth): retrieval evaluation for a legal RAG assistant

Measures whether a change to a RAG retriever made it better or worse, and blocks the pull request when it got worse. Runs on a 100-query golden set where every answer is tied to an exact passage in a 430-document legal corpus.

- **recall@10 from 0.695 to 0.960** (+26.5 pts, 95% CI [+18.5, +35.0]), chosen from **16 retriever configs**: BM25, dense, hybrid, reranker and chunk-size variants
- **Citation lookups from 0.21 to 0.87** recall@10: the statute and docket queries that dense-only search missed
- **CI regression gate** fails any PR that drops recall@10 by more than 1 point. A "harmless" chunk-size change was [caught at −5.5 pts](https://github.com/SARAHKAMYAR/groundtruth/blob/main/docs/CI_GATE_DEMO.md)
- **Honest about the result:** estimates ~1.7 pts of optimism from picking the winner on the same queries, and reports that plain BM25 with document headers is statistically tied on recall ([why hybrid was still chosen](https://github.com/SARAHKAMYAR/groundtruth/blob/main/docs/RECOMMENDATION.md))
- LLM-judge generation layer (faithfulness, answer relevance) is built and tested, but its scores have not been measured yet

`Python` `sentence-transformers` `BM25` `BGE` `pytest` `GitHub Actions` · Fictional corpus, the method transfers to a real archive

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

**LLM and retrieval:** RAG · hybrid search (BM25 + dense, RRF) · rerankers · pgvector · sentence-transformers · tool calling · structured outputs · Gemini API

**Evaluation:** recall@k · MRR · nDCG · bootstrap confidence intervals · LLM-as-judge validation · CI regression gates

**Engineering:** Python · FastAPI · Pydantic · PostgreSQL · SQL · Docker Compose · GitHub Actions · pytest · Streamlit

**Now:** working toward an MSc thesis in computer vision for medical imaging
