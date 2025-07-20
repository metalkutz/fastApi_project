# FastAPI ML Project

A simple machine learning API built with FastAPI.

## Features

- RESTful API for ML model inference
- Easy integration and deployment
- Lightweight and fast

## Requirements

- Python 3.10+
- FastAPI
- Uvicorn
- scikit-learn

## Installation

```bash
pip install fastapi uvicorn scikit-learn
```

## Usage

1. Clone the repository.
2. Start the API server:

    ```bash
    uvicorn main:app --reload
    ```

3. Send requests to the API endpoint:

    ```bash
    curl -X POST "http://127.0.0.1:8000/predict" -H "Content-Type: application/json" -d '{"data": [your_input]}'
    ```

## Example Endpoint

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class InputData(BaseModel):
    data: list

@app.post("/predict")
def predict(input: InputData):
    # Replace with your ML model prediction
    result = sum(input.data)
    return {"prediction": result}
```

## License

MIT