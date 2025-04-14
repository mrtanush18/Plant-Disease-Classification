# Potato Disease Classification Web App

## Intro
This project uses deep learning to classify diseases in potato leaves from images. The system includes a React-based frontend for uploading leaf images and a FastAPI backend powered by a TensorFlow model.

## Data Source
The dataset used is available on Kaggle. You can find the dataset and additional information [here.](https://www.kaggle.com/datasets/mervetorkan/churndataset](https://www.kaggle.com/arjuntejaswi/plant-village)

## Running the Repository
To run this repository locally:
+ Clone the repository to your local machine.
+ Create a virtual environment for the project.
```
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

## Running the API

### Using FastAPI

1. Get inside `api` folder

```bash
cd api
```

2. Run the FastAPI Server using uvicorn

```bash
uvicorn main:app --reload --host 0.0.0.0
```

3. Your API is now running at `0.0.0.0:8000`

### Using FastAPI & TF Serve

1. Get inside `api` folder

```bash
cd api
```

2. Copy the `models.config.example` as `models.config` and update the paths in file.
3. Run the TF Serve (Update config file path below)

```bash
docker run -t --rm -p 8501:8501 -v C:/Code/potato-disease-classification:/potato-disease-classification tensorflow/serving --rest_api_port=8501 --model_config_file=/potato-disease-classification/models.config
```

4. Run the FastAPI Server using uvicorn
   For this you can directly run it from your main.py or main-tf-serving.py using pycharm run option (as shown in the video tutorial)
   OR you can run it from command prompt as shown below,

```bash
uvicorn main-tf-serving:app --reload --host 0.0.0.0
```

5. Your API is now running at `0.0.0.0:8000`

## Running the Frontend

1. Get inside `api` folder

```bash
cd frontend
```

2. Copy the `.env.example` as `.env` and update `REACT_APP_API_URL` to API URL if needed.
3. Run the frontend

```bash
npm run start
```
