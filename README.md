# Air Quality Cloud Dashboard  
*A Flask web application for querying, storing, and displaying real-time air quality data from the OpenAQ API.*

---

## **Overview**
This project is a Flask-powered web application that retrieves real-time air quality measurements from the OpenAQ API, stores them locally using SQLAlchemy, and displays potentially risky PM2.5 readings in a simple dashboard.

It demonstrates:

- REST API integration  
- Flask routing and templating  
- SQLite database modeling with SQLAlchemy  
- Filtering and serving real-time environmental data  
- Basic dashboard logic for environmental analytics  

---

## **Features**

### **Live Data Retrieval**
Pulls real-time air quality data (e.g., PM2.5) from the OpenAQ API.

### **Database Integration**
Stores retrieved measurements locally using **Flask-SQLAlchemy**, enabling:

- persistence  
- filtering  
- historical querying  

### **Custom Data Model**
The `Record` model defines:

- **location**  
- **parameter**  
- **value**  
- **timestamp**  

with a clean `__repr__` for debugging and introspection.

### **Risk-Based Dashboard**
The main route queries the database for **PM2.5 readings above a risky threshold** and serves them through a lightweight dashboard page.

---

## **Tech Stack**

- **Flask** (app framework)  
- **Flask-SQLAlchemy** (ORM + SQLite)  
- **Requests** (OpenAQ API calls)  
- **OpenAQ API** (https://docs.openaq.org/)  
- **SQLite** for local database storage  

---

## **Project Structure**

```
air-quality-cloud-app/
│
├── aq_dashboard.py        # Main Flask application
├── openaq.py              # OpenAQ API helper module
├── models.py              # SQLAlchemy model(s)
├── requirements.txt       # Python dependencies
├── README.md              # Project documentation
│
└── instance/
    └── air_quality.sqlite # Local SQLite database (auto-created)
```

---

## **How It Works**

1. `openaq.py` fetches measurements from the OpenAQ API  
2. Data is validated and stored in the `Record` model  
3. Flask routes query the database for high-risk PM2.5 readings  
4. Results are displayed in a dashboard webpage  

The app can be extended with charts, location filters, health-risk scoring, or cloud deployment.

---

## **Running the App**

```bash
# Install dependencies
pip install -r requirements.txt

# Run the Flask app
export FLASK_APP=aq_dashboard.py
flask run
```

Then visit:  
**http://127.0.0.1:5000**

---

## **Next Steps & Extensions**

Potential upgrades:

- Add a full dashboard UI (Plotly Dash, Bootstrap, or HTMX)
- Deploy to Render / Railway / Azure App Service
- Add cron-like scheduled ingestion jobs
- Expand the database schema for multi-parameter tracking
- Integrate historical charts & trends

---

## **Summary**
This project showcases full-stack data workflow skills:

- API ingestion  
- Data modeling  
- Database persistence  
- Backend routing  
- Live analytic filtering  

It represents foundational data engineering + applied analytics in a clean, approachable Flask application.
