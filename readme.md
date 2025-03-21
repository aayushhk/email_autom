# 📧 AI-Powered Email Management System

This project provides real-time email synchronization, AI-based categorization, searchable email storage using Elasticsearch, Slack notifications, webhook automation, and a frontend UI for managing emails efficiently.

---

## 🚀 **How to Run Locally**

### 1️⃣ **Clone the Repository**
```sh
git clone https://github.com/your-repo/email-management.git
cd email-management
```

### 2️⃣ **Set Up Virtual Environment**
```sh
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3️⃣ **Install Dependencies**
```sh
pip install -r requirements.txt
```

### 4️⃣ **Set Up Environment Variables**
Create a `.env` file in the root directory and add the following:
```
SLACK_WEBHOOK_URL=https://hooks.slack.com/services/XXX/YYY/ZZZ
IMAP_SERVER=imap.gmail.com
IMAP_USERNAME=your-email@gmail.com
IMAP_PASSWORD=your-app-password
ELASTICSEARCH_HOST=http://localhost:9200
```

### 5️⃣ **Run Docker Services (Elasticsearch & Vector DB)**
Ensure you have **Docker** installed, then run:
```sh
docker-compose up -d
```

### 6️⃣ **Start the Backend Server**
```sh
uvicorn main:app --reload
```

### 7️⃣ **Test API Endpoints Using Postman or cURL**
#### ✅ **Send a Slack Notification:**
```sh
curl -X 'POST' 'http://localhost:8000/slack/send-slack' \
     -H 'Content-Type: application/json' \
     -d '{"message": "🚀 New Interested Email Received!"}'
```
#### ✅ **Search Emails in Elasticsearch:**
```sh
curl -X 'GET' 'http://localhost:8000/search/emails?query=meeting'
```

### 8️⃣ **Run the Frontend (If Implemented)**
Navigate to the `frontend` folder and start the app:
```sh
cd frontend
npm install  # Install dependencies
npm start    # Run the frontend
```

---

## 📌 **Project Structure**
```
backend/
│── main.py                     # FastAPI application entry point
│── models/
│   │── email_model.py         # Schema for emails
│   │── ai_model.py            # AI model for categorization
│   │── vector_db.py           # Vector database (FAISS, Pinecone, or ChromaDB)
│── services/
│   │── imap_sync.py           # IMAP email synchronization service
│   │── email_categorization.py # AI-based email classification
│── routes/
│   │── email_routes.py         # Email sync endpoints
│   │── slack_routes.py         # Slack notification endpoints
│   │── search_routes.py        # Elasticsearch search endpoints
│   │── webhook_routes.py       # Webhook endpoints
│── database/
│   │── elasticsearch_setup.py  # Elasticsearch connection
│   │── db_connection.py        # Vector DB connection (FAISS/Pinecone)
│── utils/
│   │── email_utils.py          # Email processing helpers
│   │── slack_utils.py          # Slack notification functions
│   │── webhook_utils.py        # Webhook trigger functions
│── .env                        # Environment variables
│── docker-compose.yml          # Docker setup for Elasticsearch
│── requirements.txt            # Dependencies
│── README.md                   # Documentation (this file)
```

---

## 🎯 **Features Implemented**
✅ **Real-Time Email Synchronization** (IMAP IDLE mode)
✅ **Searchable Email Storage** (Elasticsearch indexing)
✅ **AI-Based Email Categorization** (Interested, Spam, etc.)
✅ **Slack & Webhook Integration** (Notifications & Automation)
✅ **Frontend UI for Email Management**
✅ **AI-Powered Suggested Replies** (RAG with Vector DB & LLM)

---

## 🛠 **Contributing**
Feel free to fork this repository and create pull requests for improvements!

---

## 📄 **License**
This project is licensed under the MIT License.

