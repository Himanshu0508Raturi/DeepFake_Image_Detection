# DeepFake Image Detection 🔍🤖

A deep learning-based web application for detecting deepfake images using a ResNet50 model. This project provides a FastAPI backend that can classify images as either real or deepfake with confidence scores.

## ✨ Features

- **Deep Learning Model**: ResNet50-based architecture for accurate deepfake detection
- **REST API**: FastAPI-powered endpoints for easy integration
- **Real-time Predictions**: Upload images and get instant classification results
- **Confidence Scoring**: Returns prediction confidence for each classification
- **Web Interface**: Simple HTML interface for testing the API

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- pip package manager

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Himanshu0508Raturi/DeepFake_Image_Detection.git
cd DeepFake_Image_Detection
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the application:
```bash
uvicorn app:app --host 0.0.0.0 --port 8000
```

The API will be available at `http://localhost:8000`

## 📖 API Usage

### Endpoints

#### GET `/`
Returns a welcome message indicating the model is ready. 

**Response:**
```json
{
  "message": "Model is ready for predictions"
}
```

#### POST `/predict`
Upload an image to detect if it's real or deepfake.

**Request:**
- Method: POST
- Content-Type:  multipart/form-data
- Body: Image file

**Response:**
```json
{
  "label":  "Real" | "Deepfake",
  "confidence": 0.9542
}
```

### Example Usage

Using cURL:
```bash
curl -X POST "http://localhost:8000/predict" \
  -H "accept: application/json" \
  -H "Content-Type: multipart/form-data" \
  -F "file=@your_image.jpg"
```

Using Python:
```python
import requests

url = "http://localhost:8000/predict"
files = {"file": open("your_image.jpg", "rb")}
response = requests.post(url, files=files)
print(response.json())
```

## 🧠 Model Details

- **Architecture**: ResNet50 (pre-trained on ImageNet)
- **Input Size**: 180x180 pixels
- **Output**: Binary classification (Real vs Deepfake)
- **Framework**: TensorFlow/Keras

## 📁 Project Structure

```
DeepFake_Image_Detection/
├── app.py                           # FastAPI application
├── deepfake_detector_model.ipynb    # Model training notebook
├── resnet50_model_explicit.keras    # Trained model file
├── requirements.txt                 # Python dependencies
├── index.html                       # Web interface
└── README.md                        # Project documentation
```

## 🛠️ Technologies Used

- **FastAPI**: Modern web framework for building APIs
- **TensorFlow/Keras**: Deep learning framework
- **ResNet50**:  Convolutional neural network architecture
- **Pillow**: Image processing library
- **NumPy**: Numerical computing library
- **Uvicorn**: ASGI server for FastAPI

## 🌐 Live Demo

The application is hosted on GitHub Pages.  Visit the [project website](https://himanshu0508raturi.github.io/DeepFake_Image_Detection/) to try it out.

## 📊 Model Training

The model training process is documented in the `deepfake_detector_model.ipynb` Jupyter notebook. It includes:
- Data preprocessing and augmentation
- Model architecture setup
- Training and validation
- Performance evaluation

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📝 License

This project is open source and available under the MIT License. 

## 👨‍💻 Author

**Himanshu Raturi**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/himanshu-raturi/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=for-the-badge&logo=github)](https://github.com/Himanshu0508Raturi)

## ⚠️ Disclaimer

This tool is designed for educational and research purposes.  While it aims to detect deepfake images with high accuracy, no detection system is perfect. Always verify critical information through multiple sources. 

## 📧 Contact

For questions or feedback, please open an issue on GitHub. 

---

⭐ If you find this project useful, please consider giving it a star! 
