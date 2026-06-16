# Machine Learning Driven Analysis of Digital Payment Acceptance Trends Among Retail Merchants

This project is a Django web application for analyzing digital payment acceptance trends and predicting customer satisfaction outcomes using machine learning. It includes user registration/login, admin user management, dataset viewing, model training, and prediction pages.

## Features

- User registration, login, and password reset
- Admin login and registered user management
- Dataset preview for digital payment records
- Gradient Boosting Regressor training workflow
- Customer satisfaction score prediction from transaction-related inputs
- Included trained model and scaler files for prediction

## Tech Stack

- Python
- Django
- SQLite
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

## Project Structure

```text
digital_payment/
+-- admins/                 # Admin app views and configuration
+-- assests/templates/      # HTML templates
+-- digital_payment/        # Main Django project settings and URLs
+-- media/                  # Dataset files
+-- users/                  # User app models, views, and migrations
+-- db.sqlite3              # SQLite database
+-- manage.py               # Django management script
+-- rg.pkl                  # Trained regression model
+-- scaler.pkl              # Saved feature scaler
```

## Setup Instructions

1. Clone the repository:

```bash
git clone https://github.com/jahnaviguturi/MACHINE-LEARNING-DRIVEN-ANALYSIS-OF-DIGITAL-PAYMENT-ACCEPTANCE-TRENDS-AMONG-RETAIL-MERCHANTS.git
cd MACHINE-LEARNING-DRIVEN-ANALYSIS-OF-DIGITAL-PAYMENT-ACCEPTANCE-TRENDS-AMONG-RETAIL-MERCHANTS
```

2. Create and activate a virtual environment:

```bash
python -m venv venv
venv\Scripts\activate
```

3. Install required packages:

```bash
pip install django pandas numpy scikit-learn matplotlib seaborn
```

4. Apply migrations:

```bash
python manage.py migrate
```

5. Run the development server:

```bash
python manage.py runserver
```

6. Open the app in a browser:

```text
http://127.0.0.1:8000/
```

## Main Routes

- `/` - Home page
- `/Adminlogin` - Admin login
- `/UserLogin` - User login
- `/UserRegisterForm` - User registration
- `/dataset_view/` - Dataset preview
- `/training/` - Train and evaluate the model
- `/prediction/` - Predict customer satisfaction score

## Machine Learning Workflow

The training workflow reads `media/DigitalPay_balanced_dataset (1).csv`, selects transaction and loyalty-related features, scales them with `StandardScaler`, trains a `GradientBoostingRegressor`, and saves the model artifacts as `rg.pkl` and `scaler.pkl`.

## Notes

- This project uses SQLite for local development.
- The included `db.sqlite3`, dataset, model, and scaler files are part of the current project state.
- For production deployment, move sensitive Django settings such as `SECRET_KEY` and `DEBUG` into environment variables.

## Deployment From GitHub

This Django project cannot be hosted directly with GitHub Pages because GitHub Pages only serves static HTML, CSS, and JavaScript. To run the Django backend, deploy the GitHub repository to a Python hosting service such as Render.

### Render Deployment

1. Push the latest code to GitHub.
2. Go to [Render](https://render.com/) and sign in.
3. Select **New +** and choose **Blueprint**.
4. Connect this GitHub repository.
5. Render will detect `render.yaml` and create the web service.
6. Wait for the build to complete.
7. Open the generated Render URL.

The project includes:

- `requirements.txt` for Python dependencies
- `Procfile` for the web process
- `runtime.txt` for the Python version
- `render.yaml` for Render deployment settings

For a production system, use a persistent database such as PostgreSQL instead of SQLite.
