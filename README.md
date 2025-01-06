## Adult Income Prediction
This project predicts whether an individual's income exceeds $50K/year based on census data. The machine learning model is developed, serialized into a pickle file, and deployed using a Flask web application. The deployment process is streamlined with Docker and CI/CD pipelines.

### Project Structure
```
INCOME
│
├── .github/workflows/
│   └── dockers.yml          # CI/CD pipeline configuration for automated deployment
│
├── app/
│   ├── static/
│   │   └── style.css        # CSS for styling the Flask application
│   ├── templates/
│   │   └── index.html       # HTML template for the web application
│   ├── app.py               # Flask application to serve predictions
│   ├── model.pkl            # Serialized best machine learning model
│   └── model.py             # Script to train and save the best model as a pickle file
│
├── assets/
│   └── flask-app.png        # Project screenshot or logo (optional)
│
├── data/
│   └── adult.csv            # Adult Income dataset for training and testing
│
├── Notebook/
│   └── Code.ipynb           # Jupyter notebook for data exploration, preprocessing, and model evaluation
│
├── venv/                    # Virtual environment (optional for local development)
│
├── .gitignore               # Specifies files and directories to ignore in Git
├── Dockerfile               # Configuration file to build the Docker container
├── README.md                # Project documentation
├── requirements.txt         # Python dependencies
```


### Features
#### 1. Data Analysis and Preprocessing:
        * Data exploration, cleaning, and feature engineering are performed in `Code.ipynb` using the `adult.csv` dataset.

#### 2. Model Training:
        * The `model.py` script: 
        * Makes the pickle(model.pkl) of the model which is trained best in the notebook.

#### 3. Flask Web Application:
        * The web app is implemented in `app.py` and consists of:
        * A user-friendly interface (`index.html` and `style.css`) to input data.    
        * Backend logic to load the pickle file (`model.pkl`) and return predictions.  

#### 4. Deployment:
        * The project is containerized using Docker (`Dockerfile`). 
        * Automated deployment is managed using CI/CD pipelines configured in `dockers.yml`.  


### Getting Started
#### Prerequisites
* Python 3.8 or later
* Docker installed on your machine
* (Optional) Virtual environment tools like venv or conda           

#### Installation
1. Clone the repository:
```
git clone https://github.com/your-repo/Income_Prediction_Using_Machine_Learning.git
cd Income_Prediction_Using_Machine_Learning
```
2. Set up a virtual environment (optional but recommended):
```
conda create -p venv python==3.x -y
conda activate venv
```
3. Install dependencies:
```
pip install -r requirements.txt
```
4. Train and Serialize the Model:
Run model.py to train the model and generate the model.pkl file:
```
python app/model.py
```
5. Run the Flask Application:
```
python app/app.py
```
6. Access the App:
* Open your browser and navigate to `http://127.0.0.1:5000`.


### Deployment with Docker
1. Build the Docker Image:
```
docker build -t flask-income-app .
```
2. Run the Docker Container:
```
docker run -p 5000:5000 adult-income-prediction
```
3. Access the App:
* Open your browser and navigate to `http://127.0.0.1:5000`.


### CI/CD Pipeline
* The project uses GitHub Actions for CI/CD.
* The `dockers.yml` file automates:
   1. Building and testing the Docker image.
   2. Deploying the app to your Docker environment.


### Technologies Used
* **Programming Language**: Python
* **Libraries**: Pandas, Scikit-learn, Flask
* **Frontend**: HTML, CSS
* **Containerization**: Docker
* **CI/CD**: GitHub Actions

## Dataset
* **Source**: UCI Machine Learning Repository - Adult Dataset
* **Description**:
       * Predicts whether income exceeds $50K/year based on census data.
       * Contains features like age, education, occupation, and hours worked.


### Future Work
* Add advanced preprocessing techniques for better feature engineering.
* Deploy the model on a cloud platform like AWS, GCP, or Azure.


### Acknowledgments
* Thanks to the UCI Machine Learning Repository for providing the dataset.
* Inspired by various open-source projects and community contributions.