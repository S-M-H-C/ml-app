# ML-App: Machine Learning Application with Docker

## Overview
This project demonstrates a simple machine learning application using a decision tree classifier trained on the Iris dataset. The application is containerized using Docker and provides a prediction endpoint via a Flask web server.

## Prerequisites
- Python 3.9
- Docker

## Project Structure
```
ml-app/
├── Dockerfile
├── requirements.txt
├── train_model.py
├── app.py
└── model.pkl
```

## Setup Instructions

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/ml-app.git
cd ml-app
```

### Step 2: Build the Docker Image
```bash
sudo docker build -t ml-app .
```

### Step 3: Run the Docker Container
```bash
sudo docker run -p 4000:80 ml-app
```

### Step 4: Access the Application
Open your browser and navigate to `http://localhost:4000` to see the running application.

### Step 5: Test the ML Endpoint
You can test the `/predict` endpoint using `curl`:
```bash
curl -X POST http://localhost:4000/predict -H "Content-Type: application/json" -d '{"input": [5.1, 3.5, 1.4, 0.2]}'
```

## Files Description
- **Dockerfile**: Contains the instructions to build the Docker image.
- **requirements.txt**: Lists the Python dependencies required for the application.
- **train_model.py**: Script to train the decision tree classifier and save the model.
- **app.py**: Flask application to serve the prediction endpoint.
- **model.pkl**: Serialized trained model (generated after running `train_model.py`).

## How to Train the Model
If you need to retrain the model, run the following command:
```bash
python train_model.py
```
This will generate a new `model.pkl` file.

## Contributing
Feel free to fork this repository and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

## License
This project is licensed under the MIT License.

---
