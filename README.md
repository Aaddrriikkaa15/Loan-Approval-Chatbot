# 🏦 Loan Approval Prediction using RAG (Retrieval-Augmented Generation)

This project implements a **Loan Approval Classifier** using a **Retrieval-Augmented Generation (RAG)** approach. It predicts whether a loan will be approved (`y`) or not (`n`) based on applicant details using semantic search on past loan data.

---

## 📂 Dataset

> [Kaggle Dataset Link](https://www.kaggle.com/datasets/sonalisingh1411/loan-approval-prediction?select=Training+Dataset.csv)]

- `Training Dataset.csv` – historical loan applications with status (`Loan_Status`)
- `Test Dataset.csv` – new loan applications to predict for
- `Final_Submission.csv` – output predictions in required format

---

## 🧠 Approach

We use **RAG-style classification**:

1. 🔄 **Tabular-to-Text Transformation**  
   Convert each row into a descriptive text form.
2. 🧠 **Semantic Embedding**  
   Use `sentence-transformers` (MiniLM) to embed case descriptions.
3. 🔍 **Similarity Search with FAISS**  
   Retrieve top-k similar past examples.
4. 🗳️ **Majority Vote**  
   Predict loan status based on retrieved examples.

---

## 📦 Tech Stack

| Component        | Tool / Library                        |
|------------------|----------------------------------------|
| Embedding Model  | `all-MiniLM-L6-v2` (Hugging Face)     |
| Similarity Search| FAISS (Facebook AI Similarity Search) |
| Programming Lang | Python 3.x                            |
| Data Handling    | Pandas                                |

---

## 🚀 How to Run

1. **Clone the repo:**
   ```bash
   git clone https://github.com/yourusername/loan-approval-rag.git
   cd loan-approval-rag

2. **Isntall dependencies :**
   pip install -r requirements.txt

3. **Run the Script : **
   python loan_approval_rag.py

4. **Output : **
   A CSV file named Final_Submission.csv with predictions (y / n)


📊 Sample Output (Final_Submission.csv)
Loan_ID	Answer
LP001002	y
LP001003	n
LP001005	y

✅ Future Improvements
🔧 Fine-tune a lightweight classifier after retrieval

💬 Add a Streamlit-based Q&A chatbot interface

📈 Evaluate on validation split if available

🙌 Credits
Hugging Face Transformers & Sentence-Transformers

FAISS by Facebook AI

Inspired by Retrieval-Augmented Generation (RAG) techniques

📜 License
This project is licensed under the MIT License.

yaml
Copy
Edit

---

### ✅ Bonus: `requirements.txt` (for reference)

```txt
pandas
sentence-transformers
faiss-cpu
