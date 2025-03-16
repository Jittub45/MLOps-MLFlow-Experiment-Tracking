 🚀 MLOps-MLFlow-Experiment-Tracking

 📌 Overview
This project demonstrates how to implement experiment tracking using MLflow. It covers setting up MLflow locally, integrating it with a remote tracking server (DagsHub), and managing experiment logs, artifacts, and model versions.

 🔧 Tech Stack & Tools Used
- Languages: Python
- ML Tools: Scikit-learn, NumPy, Pandas
- Experiment Tracking: MLflow
- Remote Storage & Tracking: DagsHub
- Version Control: GitHub

```
 📂 Project Structure
MLOps-MLFlow-Experiment-Tracking/
│── mlartifacts/             # Stored MLflow artifacts (models, logs, etc.)
│── mlruns/                  # MLflow experiment tracking runs
│── src/                     # Source code for ML model training and evaluation
│   ├── file1.py             # MLflow experiment logging and model training
│   ├── test.py              # Converts local tracking to HTTP tracking
│── .gitignore               # Files and folders to ignore in Git
│── Confusion-matrix.png     # Example confusion matrix from experiment tracking
│── LICENSE                  # License file
│── README.md                # Documentation and project guide
│── mlflow-autolog.txt       # Notes on MLflow auto-logging
│── mlflow-basics.txt        # Basics of MLflow experiment tracking
│── project_flow.txt         # Step-by-step workflow for the project
```

 🛠️ Setup Instructions
1. Create a GitHub repository and clone it locally.
2. Install MLflow:
   ```bash
   pip install mlflow
   ```
3. Start the MLflow UI:
   ```bash
   mlflow ui
   ```
4. Create a Python script for a Random Forest model and integrate MLflow.
5. Create a `test.py` file and convert local tracking to an HTTP server.
6. Create a new experiment in MLflow.
7. Add artifacts, tags, and model-saving code in `file1.py`.

 🌍 Setting Up a Remote MLflow Server
1. Create a DagsHub account and connect it to your GitHub repository.
2. Create a new repository on DagsHub and grant access to the GitHub repository.
3. Install DagsHub package:
   ```bash
   pip install dagshub
   ```
4. Initialize DagsHub and set the tracking URI:
   ```python
   import mlflow
   mlflow.set_tracking_uri("<dagshub_repo_link>")
   ```

 ⚡ MLflow Auto-Logging
1. Enable autologging in MLflow by adding:
   ```python
   mlflow.autolog()
   ```
2. Run the script to automatically log parameters, metrics, and artifacts.

 🎯 Hyperparameter Tuning & Experiment Tracking
1. Enable MLflow parent-child run tracking to log all child runs under a parent experiment:
   ```python
   with mlflow.start_run() as parent_run:
       for param_set in hyperparameter_list:
           with mlflow.start_run(nested=True) as child_run:
               # Train model and log results
   ```
2. Compare all child runs in the MLflow UI.

 📦 MLflow Model Registry
1. Register models in MLflow Model Registry.
2. Manage different versions of the trained models.
3. Transition models between different stages (e.g., Staging → Production).

 📩 Contact
For queries, feel free to reach out:
- GitHub: [Jittub45](https://github.com/Jittub45)
- Twitter: jittub45
 🏁 Conclusion
This project showcases a complete experiment tracking pipeline with MLflow, including local and remote tracking, auto-logging, hyperparameter tuning, and model versioning. Future enhancements may include model deployment and real-time monitoring.
