# Social Media Privacy Risk Assessment Framework

A full-stack cybersecurity + AI/ML web application that analyzes social media profile information and detects potential privacy risks such as exposed PII, location leaks, public handles, DOB disclosure, unsafe links, and contextual oversharing.

## Live Project

Frontend: `PASTE_VERCEL_LINK_HERE`
Backend API: `https://social-media-privacy-risk-assessment.onrender.com`

## GitHub Repository

`https://github.com/himanshu-04022006/social-media-privacy-risk-assessment`

## Features

* Email exposure detection
* Phone number exposure detection
* Date of birth detection
* Location/address hint detection
* Public URL detection
* Social media handle detection
* ML-based contextual privacy risk prediction
* Privacy risk score generation
* Remediation suggestions
* Assessment history using SQLite
* Statistics dashboard
* Full-stack deployment with Render and Vercel

## Tech Stack

### Frontend

* React
* Vite
* CSS

### Backend

* FastAPI
* Python
* SQLite

### Machine Learning

* Scikit-learn
* TF-IDF Vectorizer
* Logistic Regression
* Joblib

### Deployment

* Frontend: Vercel
* Backend: Render
* Version Control: Git + GitHub

## Project Architecture

```text
User Input
   ↓
React Frontend
   ↓
FastAPI Backend
   ↓
Risk Engine
   ├── Regex-based PII Detection
   └── ML-based Contextual Risk Detection
   ↓
Risk Score + Findings
   ↓
SQLite Database
   ↓
Dashboard / Stats
```

## Machine Learning Workflow

```text
privacy_posts.csv
   ↓
TF-IDF Vectorizer
   ↓
Logistic Regression Model
   ↓
privacy_model.pkl
vectorizer.pkl
   ↓
FastAPI Integration
```

## Risk Detection Approach

This project uses a hybrid detection system:

### Rule-Based Detection

Used for structured and predictable patterns such as:

* Email addresses
* Phone numbers
* DOB patterns
* URLs
* Social media handles
* Address/location keywords

### ML-Based Detection

Used for contextual privacy risks such as:

* Daily routine exposure
* Hostel/college timing disclosure
* Personal lifestyle oversharing
* Indirect location hints
* Social engineering risk indicators

## Example Input

```json
{
  "username": "himanshu",
  "email": "himanshu@gmail.com",
  "phone": "9876543210",
  "bio": "I leave hostel every day at 7 AM and live near MG Road Pune"
}
```

## Example Output

```json
{
  "username": "himanshu",
  "risk_score": 45,
  "ml_prediction": "risky",
  "findings": [
    {
      "category": "PII",
      "item": "Valid email is publicly visible",
      "risk_points": 10,
      "fix": "Remove public email or use a contact form."
    },
    {
      "category": "LOCATION",
      "item": "Possible address or location detail detected in bio",
      "risk_points": 15,
      "fix": "Avoid posting exact location, address, or routine places."
    },
    {
      "category": "ML",
      "item": "ML detected contextual privacy risk",
      "risk_points": 10,
      "fix": "Avoid sharing routines, sensitive personal context, or exploitable details."
    }
  ]
}
```

## Backend Setup

```bash
cd backend
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
uvicorn app:app --reload
```

Backend runs at:

```text
http://127.0.0.1:8000
```

Swagger API docs:

```text
http://127.0.0.1:8000/docs
```

## Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Frontend runs at:

```text
http://localhost:5173
```

## Training the ML Model

```bash
cd backend
python train_model.py
```

This generates:

```text
privacy_model.pkl
vectorizer.pkl
```

## API Endpoints

### GET `/`

Returns backend health status.

### POST `/analyze`

Analyzes profile data and returns risk score, ML prediction, and findings.

### GET `/stats`

Returns total assessments, average score, highest score, and top risk records.

## Deployment

### Backend on Render

Root Directory:

```text
backend
```

Build Command:

```bash
pip install -r requirements.txt
```

Start Command:

```bash
uvicorn app:app --host 0.0.0.0 --port $PORT
```

### Frontend on Vercel

Root Directory:

```text
frontend
```

Build Command:

```bash
npm run build
```

Output Directory:

```text
dist
```

## Key Learning Outcomes

* Built a full-stack cybersecurity project
* Implemented FastAPI backend APIs
* Created a regex-based privacy risk engine
* Trained a machine learning model using TF-IDF and Logistic Regression
* Integrated ML model into FastAPI backend
* Used SQLite for assessment history
* Built a React + Vite dashboard
* Deployed backend on Render
* Deployed frontend on Vercel
* Debugged CORS, Git, deployment, and ML integration issues

## Future Improvements

* Expand ML dataset to 1000+ examples
* Add severity-based ML classification
* Add user authentication
* Add downloadable PDF reports
* Add charts for risk trends
* Add advanced NLP detection for obfuscated PII
* Add admin dashboard

## Author

**Himanshu Sahu**
Cybersecurity Student
GitHub: [himanshu-04022006](https://github.com/himanshu-04022006)

## Disclaimer

This project is created for educational and cybersecurity awareness purposes. It is not intended to collect, misuse, or expose real personal data.
