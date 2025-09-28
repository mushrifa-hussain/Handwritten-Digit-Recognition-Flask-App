# Handwritten Digit Recognition Flask App

A web application that recognizes handwritten digits (0-9) using a trained neural network model. Users can draw digits on a canvas and get real-time predictions.

## 🚀 Features

- **Interactive Canvas**: Draw digits with your mouse or touch
- **Real-time Prediction**: Get instant digit recognition results
- **Clean UI**: Simple and intuitive user interface
- **Responsive Design**: Works on desktop and mobile devices
- **High Accuracy**: Trained on MNIST dataset for reliable predictions

## 🛠️ Technologies Used

- **Backend**: Flask (Python web framework)
- **Machine Learning**: TensorFlow/Keras
- **Frontend**: HTML5 Canvas, JavaScript, CSS3
- **Model**: Convolutional Neural Network (CNN)

## 📋 Prerequisites

- Python 3.7 or higher
- pip (Python package installer)

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/mushrifa-hussain/Handwritten-Digit-Recognition-Flask-App.git
   cd Handwritten-Digit-Recognition-Flask-App
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv myenv
   ```

3. **Activate the virtual environment**
   
   **On Windows:**
   ```bash
   myenv\Scripts\activate
   ```
   
   **On macOS/Linux:**
   ```bash
   source myenv/bin/activate
   ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Download the trained model**
   
   You'll need to train the model first or download a pre-trained model. The model file should be named `handwritten_digit.keras` and placed in the root directory.

## 🚀 Running the Application

1. **Start the Flask server**
   ```bash
   python app.py
   ```

2. **Open your browser**
   
   Navigate to `http://127.0.0.1:5000` or `http://localhost:5000`

3. **Start drawing!**
   
   - Use your mouse to draw a digit (0-9) on the black canvas
   - Click "Predict" to get the AI's prediction
   - Click "Clear" to start over

## 📁 Project Structure

```
Handwritten-Digit-Recognition-Flask-App/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── handwritten_digit.keras # Trained model (not included)
├── templates/
│   └── index.html        # Main HTML template
├── static/
│   └── style.css         # CSS styles
└── README.md            # This file
```

## 🎯 How It Works

1. **Drawing**: Users draw digits on a 280x280 pixel canvas
2. **Preprocessing**: The image is resized to 28x28 pixels (MNIST format) and converted to grayscale
3. **Prediction**: The preprocessed image is fed to the trained CNN model
4. **Result**: The model returns the predicted digit with confidence scores

## 🧠 Model Architecture

The model uses a Convolutional Neural Network trained on the MNIST dataset:
- Input: 28x28 grayscale images
- Architecture: CNN with multiple convolutional and dense layers
- Output: 10 classes (digits 0-9)

## 📊 Training the Model

To train your own model, you can use the following approach:

```python
import tensorflow as tf
from tensorflow import keras

# Load MNIST dataset
(x_train, y_train), (x_test, y_test) = keras.datasets.mnist.load_data()

# Preprocess data
x_train = x_train.reshape(60000, 28, 28, 1).astype('float32') / 255.0
x_test = x_test.reshape(10000, 28, 28, 1).astype('float32') / 255.0

# Build model
model = keras.Sequential([
    keras.layers.Conv2D(32, (3, 3), activation='relu', input_shape=(28, 28, 1)),
    keras.layers.MaxPooling2D((2, 2)),
    keras.layers.Conv2D(64, (3, 3), activation='relu'),
    keras.layers.MaxPooling2D((2, 2)),
    keras.layers.Conv2D(64, (3, 3), activation='relu'),
    keras.layers.Flatten(),
    keras.layers.Dense(64, activation='relu'),
    keras.layers.Dense(10, activation='softmax')
])

# Compile and train
model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
model.fit(x_train, y_train, epochs=5, validation_data=(x_test, y_test))

# Save model
model.save('handwritten_digit.keras')
```

## 🎨 Customization

- **Styling**: Modify `static/style.css` to change the appearance
- **Canvas Size**: Adjust the canvas dimensions in `templates/index.html`
- **Model**: Replace `handwritten_digit.keras` with your own trained model

## 🐛 Troubleshooting

### Common Issues:

1. **Model not found error**
   - Ensure `handwritten_digit.keras` is in the root directory
   - Check that the model file is not corrupted

2. **Port already in use**
   - Change the port in `app.py`: `app.run(host="0.0.0.0", port=5001)`

3. **Dependencies not found**
   - Make sure you're in the virtual environment
   - Run `pip install -r requirements.txt` again

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**Mushrifa Hussain**
- GitHub: [@mushrifa-hussain](https://github.com/mushrifa-hussain)

## 🙏 Acknowledgments

- MNIST dataset for training data
- TensorFlow/Keras team for the excellent ML framework
- Flask team for the web framework

---

⭐ **Star this repository if you found it helpful!**
