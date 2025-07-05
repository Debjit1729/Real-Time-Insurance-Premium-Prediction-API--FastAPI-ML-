# Insurance Premium Prediction API

A production-ready machine learning project to predict insurance premiums based on demographic and lifestyle features, using a trained regression model deployed through a FastAPI web API. The project allows users to send JSON requests with personal details such as age, gender, BMI, smoking status, number of children, and region, and receive a predicted premium amount in response.

---

## 🚀 Features

* End-to-end ML pipeline for predicting health insurance charges
* Trained regression model using scikit-learn
* Real-time REST API built with FastAPI
* Docker support for portable deployments
* Modular, clean Python code
* Input validation using Pydantic

---

## 🗂️ Project Structure

```
insurance-premium-prediction-fastapi/
│
├── artifacts/
│     └── model.pkl                # Trained regression model
│
├── docker/
│     └── Dockerfile               # Dockerfile for containerization
├── app.py                         # FastAPI app
├── requirements.txt               # Project dependencies
└── README.md                      # Project documentation
```

---

## 📊 How it Works

1. **Model Training** (`insurance/train.py`)

   * Loads insurance data (CSV dataset, external)
   * Preprocesses data (encoding categorical features, scaling if needed)
   * Trains a regression model

2. **Prediction** (`insurance/predict.py`)

   * Loads the saved model
   * Transforms incoming JSON data into model-ready format
   * Outputs a predicted premium

3. **FastAPI Application** (`app.py`)

   * Exposes the `/predict` POST endpoint
   * Receives JSON input
   * Returns the predicted insurance premium in JSON

4. **Deployment**

   * Can run locally with Uvicorn
   * Or deploy with Docker for portability

---

**Install the dependencies:**

```bash
pip install -r requirements.txt
```

---

## 🛠️ Usage

### 1️⃣ Train the model

*(Ensure you have the appropriate CSV dataset present if you want to retrain.)*

### 2️⃣ Run the FastAPI server

```bash
uvicorn app:app --reload
```

Visit the interactive docs:

```
http://127.0.0.1:8000/docs
```

---

## 🛰️ Docker Deployment

You can also deploy using Docker:

```bash
docker build -t insurance-api .
docker run -p 8000:8000 insurance-api
```

---

## 📡 API Endpoint

### POST `/predict`

#### Example Request

```json
{
  "age": 22,
  "weight": 64,
  "height": 1.6,
  "income_lpa": 4,
  "smoker": true,
  "city": "Kolkata",
  "occupation": "freelancer"
}
```

#### Example Response

```json
{
  "response": {
    "predicted_category": "Low",
    "confidence": 0.63,
    "class_probabilities": {
      "High": 0,
      "Low": 0.63,
      "Medium": 0.37
    }
  }
}
```

---

## 🧩 Technologies Used

* Python 3
* scikit-learn
* pandas, numpy
* FastAPI
* Uvicorn
* Pydantic
* Docker

---

## 📈 Future Improvements

* Add a Streamlit front-end for easier interaction
* Add user authentication and security
* Incorporate more advanced models
* Add CI/CD workflows

---

## Screenshots

### 1st
![1st](https://github.com/Debjit1729/Real-Time-Insurance-Premium-Prediction-API--FastAPI-ML-/blob/main/Screenshot%202025-07-06%20011034.png)

### 2nd
![1st](https://github.com/Debjit1729/Real-Time-Insurance-Premium-Prediction-API--FastAPI-ML-/blob/main/Screenshot%202025-07-06%20011100.png)

### 3rd
![1st](https://github.com/Debjit1729/Real-Time-Insurance-Premium-Prediction-API--FastAPI-ML-/blob/main/Screenshot%202025-07-06%20011210.png)


## 🤝 Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.

---
