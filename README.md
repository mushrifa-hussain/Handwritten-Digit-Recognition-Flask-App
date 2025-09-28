# 🖊️ Handwritten Digit Recognition App

A Machine Learning powered Flask web application that recognizes handwritten digits (0-9) using a trained neural network model.

## 📌 Features

- **Real-time digit recognition** from hand-drawn input
- **Interactive canvas** for drawing digits with mouse
- **High accuracy** neural network model trained on MNIST dataset
- **Clean, responsive web interface** built with Flask and HTML5 Canvas
- **Instant predictions** with probability scores
- **Easy to use** - just draw and click predict!

## 🚀 How to Run Locally

### Prerequisites
- Python 3.7+
- pip (Python package installer)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/mushrifa-hussain/handwritten-digit-recognition.git
   cd handwritten-digit-recognition
   ```

2. **Create virtual environment** (recommended)
   ```bash
   python -m venv myenv
   # On Windows:
   myenv\Scripts\activate
   # On macOS/Linux:
   source myenv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**
   ```bash
   python app.py
   ```

5. **Open your browser** and go to `http://127.0.0.1:5000`

## 🎨 How to Use

1. **Draw a digit** (0-9) on the black canvas using your mouse
2. **Click "Predict"** to get the AI's prediction
3. **Click "Clear"** to erase the canvas and try again
4. **Draw clearly** for best results - the model works best with centered, well-formed digits

## 📂 Project Structure

```
handwritten-digit-recognition/
├── app.py                    # Flask web application
├── handwritten_digit.keras   # Trained neural network model
├── templates/
│   └── index.html           # Main web interface
├── static/
│   └── style.css            # CSS styling
├── requirements.txt         # Python dependencies
├── .gitignore              # Git ignore file
└── README.md               # This file
```

## 🧠 Model Information

- **Algorithm**: Convolutional Neural Network (CNN)
- **Framework**: TensorFlow/Keras
- **Training Dataset**: MNIST (70,000 handwritten digit images)
- **Input Size**: 28x28 pixels (grayscale)
- **Accuracy**: ~99% on MNIST test set
- **Model Architecture**: 
  - Convolutional layers for feature extraction
  - Dense layers for classification
  - Softmax output for 10 digit classes (0-9)

## 🛠️ Technical Details

### Backend (Flask)
- **Framework**: Flask web framework
- **Image Processing**: PIL (Python Imaging Library)
- **Base64 encoding/decoding** for canvas data transfer
- **JSON API** for prediction requests

### Frontend
- **HTML5 Canvas** for drawing interface
- **JavaScript** for mouse event handling
- **CSS3** for responsive styling
- **AJAX** for seamless prediction requests

### Dependencies
- `flask` - Web framework
- `tensorflow` - Machine learning framework
- `numpy` - Numerical computing
- `PIL` - Image processing
- `keras` - High-level neural network API

## 🌐 Deployment

This app can be easily deployed on various platforms:

- **Heroku**: Add Procfile and requirements.txt
- **AWS**: Use Elastic Beanstalk or EC2
- **Google Cloud**: App Engine or Compute Engine
- **Streamlit Cloud**: Convert to Streamlit app
- **Docker**: Containerize for easy deployment

## 📊 Performance

- **Prediction Time**: ~50-100ms per digit
- **Model Size**: ~2-5MB (depending on architecture)
- **Memory Usage**: ~100-200MB (including TensorFlow)
- **Browser Compatibility**: Modern browsers with Canvas support

## 🔧 Customization

### Training Your Own Model
1. Use the MNIST dataset or your own digit images
2. Train a CNN model with TensorFlow/Keras
3. Save the model as `.keras` file
4. Replace `handwritten_digit.keras` in the project

### Modifying the Interface
- Edit `templates/index.html` for layout changes
- Modify `static/style.css` for styling
- Update `app.py` for backend logic changes

## ⚠️ Limitations

- Works best with **single digits** (0-9)
- Requires **clear, well-formed** handwriting
- **Centered digits** perform better
- Model trained on **MNIST-style** digits (28x28, grayscale)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- **MNIST Dataset** - Yann LeCun, Corinna Cortes, Christopher Burges
- **TensorFlow Team** - For the amazing ML framework
- **Flask Community** - For the lightweight web framework
- **Open Source Community** - For continuous inspiration

## 📞 Contact

**Mushrifa Hussain**
- GitHub: [@mushrifa-hussain](https://github.com/mushrifa-hussain)
- Project Link: [Handwritten Digit Recognition](https://github.com/mushrifa-hussain/handwritten-digit-recognition)

---

⭐ **Star this repository** if you found it helpful!

🐛 **Found a bug?** Open an issue and let me know!

💡 **Have suggestions?** I'd love to hear your ideas!
