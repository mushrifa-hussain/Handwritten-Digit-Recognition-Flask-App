# Handwritten Digit Recognition Flask App

A web application that uses machine learning to recognize handwritten digits (0-9) drawn by users. The app uses a trained Keras model to predict digits drawn on a canvas.

## Features

- **Interactive Canvas**: Draw digits using your mouse on a web canvas
- **Real-time Prediction**: Get instant predictions for your handwritten digits
- **Clean UI**: Simple and intuitive user interface
- **Responsive Design**: Works on different screen sizes

## Technologies Used

- **Backend**: Flask (Python web framework)
- **Machine Learning**: TensorFlow/Keras
- **Frontend**: HTML5 Canvas, JavaScript, CSS
- **Image Processing**: PIL (Python Imaging Library)
- **Model**: Pre-trained Keras model for digit recognition

## Installation

### Prerequisites

- Python 3.7 or higher
- pip (Python package installer)

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/mushrifa-hussain/Handwritten-Digit-Recognition-Flask-App.git
   cd Handwritten-Digit-Recognition-Flask-App
   ```

2. **Create a virtual environment** (recommended)
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

5. **Open your browser** and navigate to `http://127.0.0.1:5000`

## Usage

1. **Draw a digit**: Use your mouse to draw a digit (0-9) on the black canvas
2. **Clear canvas**: Click the "Clear" button to erase your drawing
3. **Get prediction**: Click the "Predict" button to see the AI's prediction
4. **Try again**: Clear the canvas and draw a different digit

## Project Structure

```
Handwritten-Digit-Recognition-Flask-App/
├── app.py                 # Main Flask application
├── handwritten_digit.keras # Trained Keras model
├── requirements.txt       # Python dependencies
├── static/
│   └── style.css         # CSS styles
├── templates/
│   └── index.html        # HTML template
└── README.md             # This file
```

## API Endpoints

- `GET /` - Serves the main application page
- `POST /predict` - Accepts image data and returns digit prediction

### Predict Endpoint

**Request:**
```json
{
  "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAA..."
}
```

**Response:**
```json
{
  "prediction": 5
}
```

## Model Information

The application uses a pre-trained Keras model (`handwritten_digit.keras`) that was trained on the MNIST dataset. The model expects 28x28 grayscale images and outputs predictions for digits 0-9.

## Development

### Running in Development Mode

The app runs with debug mode disabled by default. To enable debug mode, modify `app.py`:

```python
app.run(host="0.0.0.0", port=5000, debug=True, use_reloader=False)
```

### Adding New Features

1. **Model Improvements**: Replace `handwritten_digit.keras` with a better trained model
2. **UI Enhancements**: Modify `templates/index.html` and `static/style.css`
3. **API Extensions**: Add new routes in `app.py`

## Troubleshooting

### Common Issues

1. **Port already in use**: Change the port in `app.py` if 5000 is occupied
2. **Model not found**: Ensure `handwritten_digit.keras` is in the project root
3. **Dependencies issues**: Make sure all packages in `requirements.txt` are installed

### Performance Tips

- The model loads on startup, so the first prediction might be slower
- For better accuracy, draw digits clearly and centered on the canvas
- The canvas size is optimized for 28x28 pixel input to the model

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- MNIST dataset for training data
- TensorFlow/Keras for machine learning framework
- Flask for web framework
- HTML5 Canvas API for drawing functionality

## Contact

For questions or suggestions, please open an issue on GitHub or contact the maintainer.

---

**Note**: This is a development server. For production deployment, use a production WSGI server like Gunicorn or uWSGI.
