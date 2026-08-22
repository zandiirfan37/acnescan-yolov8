# AcneScan

**AI-powered web application for acne severity classification using YOLOv8 and the Investigator's Global Assessment (IGA) scale.**

AcneScan is an end-to-end computer vision application that allows users to upload or capture a facial image and automatically classify acne severity from **IGA 0 to IGA 4** through an interactive web interface.

## Overview

AcneScan was developed to explore how deep learning and computer vision can be integrated into an accessible web-based application for acne severity assessment.

The system combines **YOLOv8-based image classification**, a **Flask backend**, and a responsive web interface to process facial images and return acne severity predictions along with relevant information for users.

The project used **2,457 labeled facial images** across IGA 0–4 categories, complemented by non-face samples to improve input validation.

## Key Features

* Acne severity classification from **IGA 0 to IGA 4**
* YOLOv8-based deep learning model
* Image upload and camera input
* Automatic facial image processing and prediction
* Non-face input handling
* Interactive prediction results
* Responsive interface for desktop and mobile devices
* Flask-based inference backend
* Web deployment

## Model Development

Multiple YOLOv8 variants and input resolutions were evaluated to identify an appropriate balance between predictive performance and inference efficiency.

The experiments included:

* YOLOv8 Nano
* YOLOv8 Small
* YOLOv8 Medium
* YOLOv8 Large
* YOLOv8 Extra Large
* Multiple input resolutions including 384 × 384 and 512 × 512

The final system selected the **YOLOv8 Nano 512** configuration based on its balance of accuracy, confidence, inference time, and computational efficiency.

## Model Performance

The selected model achieved:

* **Accuracy: 82%**
* **Macro F1-score: 0.83**
* **Weighted F1-score: 0.82**
* Evaluation set: **657 samples**

## Tech Stack

**Artificial Intelligence & Computer Vision**

* Python
* YOLOv8
* Ultralytics

**Backend**

* Flask

**Frontend**

* HTML
* CSS
* JavaScript
* Bootstrap

**Development & Deployment**

* Git
* GitHub
* Docker for local environment testing
* PythonAnywhere for web deployment

The application was previously deployed through PythonAnywhere with the trained YOLOv8 model integrated directly into the Flask application.

## Application Workflow

1. User accesses the AcneScan web application.
2. User uploads a facial image or captures an image using the camera.
3. The Flask backend validates the submitted image.
4. The trained YOLOv8 model processes the image.
5. The system predicts the corresponding acne severity level.
6. The prediction result is returned through the web interface.
7. Users receive the predicted **IGA severity level** and related information.

The application supports severity levels:

* **IGA 0** — Clear
* **IGA 1** — Almost Clear
* **IGA 2** — Mild
* **IGA 3** — Moderate
* **IGA 4** — Severe

## Project Structure

```text
acnescan/
├── app/
│   ├── model/
│   │   └── best.pt
│   ├── static/
│   ├── templates/
│   ├── app.py
│   └── requirements.txt
│
├── Dockerfile
├── requirements.txt
├── .gitignore
└── README.md
```

## Web Application

The application was designed to work across desktop and mobile devices and includes:

* Landing page
* IGA severity information
* Image upload interface
* Camera input
* Prediction page
* Prediction result display
* Responsive mobile interface

Functional testing covered navigation, image submission, input validation, camera functionality, prediction processing, and result rendering.

## Deployment

AcneScan was successfully deployed as a Flask web application on **PythonAnywhere**, integrating the trained YOLOv8 model directly into the production application.

## Project Context

AcneScan was developed as a **team Machine Learning project at Universitas Airlangga** as part of the Data Science Technology undergraduate program.

The project focused on building an end-to-end AI application, covering model experimentation, evaluation, web application development, and deployment.

## Limitations

The model may still produce incorrect predictions when processing non-face objects with visual characteristics similar to human facial features. Further development could include a more diverse dataset, stronger augmentation strategies, and improved robustness to real-world image variations.

## Disclaimer

This project was developed for **educational and research purposes only**. AcneScan is not intended to provide medical diagnosis or replace consultation with qualified healthcare professionals.
