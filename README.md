# Vietnamese License Plate Reader

## Introduction
A License Plate Reader that consists of a YOLOv10 model for detecting the license plate and a TrOCR model for reading the license plate number. The models were trained using a synthetic dataset from available sources and plate images crawled from [Platesmania](https://platesmania.com/vn/).

## Preparation
After downloading the checkpoints:
```bash
git clone https://github.com/namnguyen2103/Vietnamese-License-Plate-Reader.git
cd Vietnamese-License-Plate-Reader
python app.py
```
The Flask application will run on **`http://0.0.0.0:5000`** (or **`http://localhost:5000`**).  
To make a prediction, you can use a tool like Postman or cURL to send a POST request to the `/predict` endpoint with an image file.

### Example cURL Command
```bash
curl -X POST -F "file=123.jpg" http://localhost:5000/predict
```

## Evaluation
TrOCR model: 82.59% accuracy (exact match accuracy)

Example output:
<img width="1266" height="1113" alt="image" src="https://github.com/user-attachments/assets/ab40cb2e-7abe-4aab-a47b-138c9e92bf36" />


## Future direction
* Implement a proper user interface for better accessibility.
* Adding additional features based on the available dataset (e.g., vehicle classification, regional identification, etc.)
