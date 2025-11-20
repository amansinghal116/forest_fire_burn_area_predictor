# 🌲 Forest Fire Burn Area Predictor

A **FastAPI-based machine learning web application** that predicts the
**burn area of forest fires** using meteorological and geographical
features.\
This project includes an intuitive HTML interface, a pre-trained Keras
model, and fully containerized deployment using Docker.

------------------------------------------------------------------------

## 🔥 Overview

Forest fires can lead to extensive environmental and economic losses.
Predicting the burn area helps in resource allocation, planning, and
early response measures.

This application provides:

-   ⚡ A high-performance **FastAPI** backend\
-   🔍 Burn area predictions using a **Keras regression model**\
-   🎨 A clean **Jinja2 UI** for user inputs\
-   🐳 **Docker support** for easy deployment\
-   🧮 Support for a **custom MSE loss function** used during model
    training

------------------------------------------------------------------------

## 🏗 Project Structure

    forest_fire_project/
    │
    ├── app/
    │   ├── main.py                 # FastAPI application entry point
    │   ├── forest_fire_model.keras # Pre-trained Keras model
    │   ├── templates/              # HTML templates for the app
    │   │   ├── index.html          # User input form
    │   │   └── result.html         # Prediction results page
    │   └── static/                 # CSS, images, JS
    │
    ├── Dockerfile                  # Docker build configuration
    ├── requirements.txt            # Python dependencies
    └── README.md                   # Project documentation

------------------------------------------------------------------------

## 🧠 Technologies Used

  Technology               Purpose
  ------------------------ ----------------------------
  **FastAPI**              Backend API framework
  **TensorFlow / Keras**   Model training & inference
  **Jinja2**               HTML template rendering
  **Uvicorn**              ASGI server
  **Docker**               Containerized deployment
  **Python 3.x**           Programming language

------------------------------------------------------------------------

## 🚀 Run Locally (Without Docker)

### 1️⃣ Navigate to project directory

``` bash
cd forest_fire_project
```

### 2️⃣ Install dependencies

``` bash
pip install -r requirements.txt
```

### 3️⃣ Enter the app folder

``` bash
cd app
```

### 4️⃣ Start the FastAPI server

``` bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

### 5️⃣ Access the application

Open in browser:

    http://0.0.0.0:8000

------------------------------------------------------------------------

## 🐳 Run Using Docker

### 1️⃣ Build the Docker image

``` bash
docker build -t forest_fire_predict .
```

### 2️⃣ Run the container

``` bash
docker run --name forest_fire -p 8000:8000 forest_fire_predict
```

### 3️⃣ Access the app

    http://0.0.0.0:8000

### Optional --- If port 8000 is busy:

``` bash
docker run --name forest_fire -p 8080:8000 forest_fire_predict
```

------------------------------------------------------------------------

## 🌦 Input Features

The model predicts burn area based on the following:

### 📍 Geographical Inputs

-   **X** --- X-axis coordinate\
-   **Y** --- Y-axis coordinate

### 🗓 Temporal Inputs

-   **Month** --- Month of occurrence\
-   **Day** --- Day of the week

### 🔥 Fire Weather Indexes

-   **FFMC** --- Fine Fuel Moisture Code\
-   **DMC** --- Duff Moisture Code\
-   **DC** --- Drought Code\
-   **ISI** --- Initial Spread Index

### 🌡 Weather Conditions

-   **Temp** --- Temperature\
-   **RH** --- Relative humidity\
-   **Wind** --- Wind speed\
-   **Rain** --- Rainfall

------------------------------------------------------------------------

## 🛠 Troubleshooting

### 🔴 Model file not found

Make sure `forest_fire_model.keras` is located in:

    forest_fire_project/app/

### 🔴 Docker port issues

Use a different port:

``` bash
docker run -p 8080:8000 forest_fire_predict
```

### 🔴 Missing dependencies

Reinstall:

``` bash
pip install -r requirements.txt
```

------------------------------------------------------------------------
