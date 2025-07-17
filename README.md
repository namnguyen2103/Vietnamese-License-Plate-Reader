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
### YOLOv10
- **Precision**: 0.970  
- **Recall**: 0.985  
- **mAP@0.5**: 0.994  

### TrOCR

- **Exact Match Accuracy**: 82.59%  
  (Percentage of predictions that exactly match the ground truth string)

- **Example TrOCR Output:**
<img width="1238" height="1309" alt="image" src="https://github.com/user-attachments/assets/c631e6ed-3dd3-4a71-b868-803774aa52b9" />



## Future direction
* Implement a proper user interface for better accessibility.
* Adding additional features based on the available dataset (e.g., vehicle classification, regional identification, etc.)
