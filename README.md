# Disease-prediction
Disease prediction system that predicts 41 diseases with 132 symptoms.
# MedPredict — Disease Prediction System

A small Flask-based disease prediction web app with a rule-based chatbot and a synthetic Random Forest model. It lets users register, submit symptoms, get predicted diseases with risk levels, and review prediction history. An admin interface provides user and prediction management.

**Features**
- User registration, login, and dashboard
- Symptom-based disease prediction (Random Forest model)
- Rule-based chatbot for common health questions
- Admin UI: users, predictions, notifications, settings
- SQLite database with seeded admin account

**Tech Stack & Requirements**
- Python 3.8+
- Flask
- numpy, pandas
- scikit-learn
- joblib
- bcrypt

**Quick Setup (Windows)**
1. Create and activate a virtual environment

```powershell
python -m venv venv
venv\Scripts\activate
```

2. Install required packages

```powershell
pip install flask numpy pandas scikit-learn joblib bcrypt
```

(If you prefer, create a `requirements.txt` from the packages above.)

3. (Optional) Train the ML model (creates `model/disease_model.pkl` and `model/label_encoder.pkl`):

```powershell
python train_model.py
```

4. Run the app (this also initializes the SQLite DB on first run):

```powershell
python app.py
```

Then open http://localhost:5000

**Default admin**
- Email: admin@medpredict.com
- Password: Admin@1234

The database file is created at `disease_pred.db` in the project root.

**Important Files**
- [app.py](app.py) — Flask application and routes
- [train_model.py](train_model.py) — dataset generator and model training
- [chatbot.py](chatbot.py) — rule-based chatbot responses
- [db.py](db.py) — SQLite helpers and DB initialization
- model/ — saved model and encoder (created after training)
- templates/ — HTML templates used by Flask
- static/ — static assets (CSS/JS)

**Security & Notes**
- Replace `app.secret_key` in [app.py](app.py) before deploying.
- Use a secure password for the admin account and consider locking registration in production.
- The chatbot provides general information only — it is NOT a substitute for professional medical advice.

**Development Tips**
- To re-seed or reset DB, delete `disease_pred.db` and restart `app.py`.
- Model is synthetic (generated in `train_model.py`) for demo purposes; consider training on validated medical datasets for production.

**License**
This repository has no license file; add one (e.g., MIT) if you plan to publish or share.

---

