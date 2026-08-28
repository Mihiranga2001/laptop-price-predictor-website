# 💻 Laptop Price Predictor Website

A Flask-based machine learning web application that predicts the estimated price of a laptop from its specifications.

Users can enter laptop hardware and configuration details through a simple web interface, and the application processes those inputs, sends them to a pre-trained machine learning model, and displays the predicted laptop price in **Sri Lankan Rupees (LKR)**.

## 📌 Project Overview

The **Laptop Price Predictor Website** provides a simple interface for estimating a laptop's price based on selected specifications.

The application:

1. Collects laptop specifications from an HTML form.
2. Converts the submitted values into the feature format expected by the trained model.
3. Loads the saved machine learning model from `model/predictor.pickle`.
4. Generates a price prediction.
5. Converts the predicted value to LKR.
6. Displays the estimated price on the web page.

## ✨ Features

- Machine learning-based laptop price prediction
- Simple and responsive web interface
- Flask backend
- Pre-trained model loaded using Python Pickle
- Automatic categorical feature encoding
- Support for multiple laptop brands
- Support for different laptop categories
- CPU and GPU selection
- Operating system selection
- Touchscreen support
- IPS display support
- RAM and laptop weight input
- Prediction result displayed in LKR

## 🧾 Prediction Inputs

The application uses the following information to generate a prediction:

| Feature | Description |
|---|---|
| RAM | Laptop RAM capacity in GB |
| Weight | Laptop weight in kilograms |
| Company | Laptop manufacturer |
| Type Name | Laptop category/type |
| Operating System | Installed operating system |
| CPU | Processor category |
| GPU | Graphics processor manufacturer |
| Touch Screen | Whether the laptop has a touchscreen |
| IPS | Whether the laptop has an IPS display |

### Supported Companies

- Acer
- Apple
- Asus
- Dell
- HP
- Lenovo
- MSI
- Toshiba
- Other

### Supported Laptop Types

- 2 in 1 Convertible
- Gaming
- Netbook
- Notebook
- Ultrabook
- Workstation

### Supported Operating Systems

- Windows
- macOS
- Linux
- Other

### Supported CPUs

- Intel Core i3
- Intel Core i5
- Intel Core i7
- AMD
- Other

### Supported GPUs

- Intel
- AMD
- NVIDIA

## 🛠️ Tech Stack

### Backend

- Python
- Flask
- NumPy
- Pickle
- Machine Learning

### Frontend

- HTML5
- CSS3
- Jinja2 Templates

### Machine Learning

The trained prediction model is stored as:

```text
model/predictor.pickle
```

The Flask application loads this model and calls its `predict()` method using the processed laptop specifications.

## 📂 Project Structure

```text
laptop-price-predictor-website/
│
├── app.py
│
├── model/
│   └── predictor.pickle
│
├── static/
│   └── style.css
│
└── templates/
    └── index.html
```

### File Description

| File / Directory | Purpose |
|---|---|
| `app.py` | Main Flask application and prediction logic |
| `model/predictor.pickle` | Serialized trained machine learning model |
| `templates/index.html` | Main user interface |
| `static/style.css` | Styling for the web interface |

## ⚙️ How the Application Works

The browser sends the laptop specifications to the Flask `/` route using an HTTP `POST` request.

The backend first adds the numerical features:

```text
RAM
Weight
Touchscreen
IPS
```

Categorical values are then converted into binary features using the predefined category lists for:

```text
Company
Laptop Type
Operating System
CPU
GPU
```

The resulting feature list is passed to the model:

```python
model.predict([feature_list])
```

The prediction is then converted to LKR by the application and displayed in the HTML template.

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Mihiranga2001/laptop-price-predictor-website.git
```

Move into the project directory:

```bash
cd laptop-price-predictor-website
```

### 2. Create a Virtual Environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### Linux / macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

The repository currently does not include a `requirements.txt` file.

Install the main dependencies with:

```bash
pip install Flask numpy scikit-learn
```

> **Note:** A Pickle model normally needs the same machine-learning package, and sometimes a compatible package version, that was used when the model was created. If the model fails to load because of a package/version mismatch, install the appropriate dependency version used during model training.

### 4. Run the Application

```bash
python app.py
```

The Flask development server should start locally.

Open:

```text
http://127.0.0.1:5000
```

in your browser.

## 🔄 Prediction Flow

```text
User
  │
  ▼
Laptop Specification Form
  │
  ▼
Flask Application
  │
  ▼
Feature Processing / Encoding
  │
  ▼
predictor.pickle
  │
  ▼
Machine Learning Prediction
  │
  ▼
LKR Price Conversion
  │
  ▼
Predicted Price Displayed to User
```

## 💡 Example Usage

A user can enter specifications such as:

```text
RAM          : 16 GB
Weight       : 1.8 Kg
Company      : Dell
Type         : Gaming
OS           : Windows
CPU          : Intel Core i7
GPU          : NVIDIA
Touch Screen : No
IPS Display  : Yes
```

After clicking **Predict Price**, the application processes the specifications and displays an estimated laptop price in LKR.

## 🔐 Production Notes

The current application starts Flask with:

```python
app.run(debug=True)
```

This is suitable for local development but should not be used directly in a production environment.

For production deployment, consider:

- Setting `debug=False`
- Using Gunicorn or another WSGI server
- Running the application inside Docker
- Using Nginx as a reverse proxy
- Adding HTTPS
- Adding input validation and error handling
- Pinning Python package versions
- Adding automated tests
- Adding CI/CD pipelines

## 🐳 Future DevOps Improvements

This application can be extended into a complete DevOps project by adding:

- `requirements.txt`
- `Dockerfile`
- `.dockerignore`
- Automated unit tests
- Jenkins CI/CD pipeline
- Docker image build and versioning
- Docker Hub or Amazon ECR
- AWS EC2 deployment
- Nginx reverse proxy
- SSL/TLS certificate
- GitHub webhook integration
- SonarQube code-quality analysis
- Trivy container vulnerability scanning
- Prometheus monitoring
- Grafana dashboards
- Centralized application logging

## 🗺️ Future Improvements

Possible application-level improvements include:

- Better input validation
- Improved error handling
- More laptop brands
- More CPU and GPU options
- Additional hardware specifications
- Model accuracy metrics
- Model training notebook
- Dataset documentation
- Prediction API endpoint
- Mobile-friendly UI improvements
- Model retraining pipeline
- Automated ML model deployment

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a new branch.

```bash
git checkout -b feature/your-feature-name
```

3. Make your changes.
4. Commit your changes.

```bash
git commit -m "Add new feature"
```

5. Push the branch.

```bash
git push origin feature/your-feature-name
```

6. Create a Pull Request.

## 👨‍💻 Author

**Mihiranga**

GitHub: [Mihiranga2001](https://github.com/Mihiranga2001)


⭐ If you find this project useful, consider giving the repository a star.
