# Car_driver_safety_analysis

This repository contains Jupyter notebooks and deployment scripts for estimating driver safety using Pointer's dataset. The project demonstrates how to apply unsupervised learning techniques to assess driver safety at scale, leveraging both **Python (Pandas)** and **PySpark** implementations. The project also includes deployment instructions and CI/CD automation for running the solution on **Azure Databricks**.

> 🧪 This is an experimental project developed by Microsoft. Learn more in the official blog post:  
> [Unsupervised Driver Safety Estimation at Scale](https://www.microsoft.com/developerblog/2018/07/30/unsupervised-driver-safety-estimation-at-scale/)

---

## 📂 Project Structure

- `Driver safety estimation - pandas.ipynb`: Python notebook implementing the analysis with Pandas.
- `Driver safety estimation - pyspark.ipynb`: PySpark version for distributed processing.
- `databricks/deploy`: Scripts to configure and deploy the solution to Azure Databricks.
- `databricks/notebooks`: Sample notebook to run on Databricks.
- `.travis.yml`: Example Travis-CI configuration for CI/CD.

---

## 🔍 Notebooks Overview

- **Python Notebook**  
  [View on GitHub](https://github.com/Microsoft/driver_safety_analysis/blob/master/Driver%20safety%20estimation%20-%20pandas.ipynb)  
  Contains a step-by-step walkthrough using Pandas and visualization libraries.

- **PySpark Notebook**  
  [View on GitHub](https://github.com/Microsoft/driver_safety_analysis/blob/master/Driver%20safety%20estimation%20-%20pyspark.ipynb)  
  Mirrors the logic from the Python version using PySpark for scalability.

---

## 🛠️ Requirements

### Python Notebook
- Python > 3.5
- Packages:
  - `numpy>=1.14.0`
  - `scipy`
  - `pandas`
  - `seaborn`
  - `matplotlib`

### PySpark Notebook
- Python > 3.5
- Packages:
  - All Python requirements above
  - `pyspark`

---

## 🚀 Deployment on Azure Databricks

### Initial Setup
Navigate to `databricks/deploy/0_azure` to find an interactive script:
- Sets up your local environment
- Configures Azure resources
- Creates a Databricks cluster
- Installs the Databricks CLI

### Job Deployment
Scripts and templates are available in `databricks/deploy/1_configure`:
- `deploy_job.sh`: CLI script to deploy Databricks jobs using a JSON job definition.
- `job_definition.json`: Template specifying job name, notebook path, cluster config, libraries, and schedule.

These resources can be used manually or integrated into a CI/CD pipeline.

---

## ⚙️ CI/CD with Travis-CI

The `.travis.yml` file provides an example CI/CD setup:
- Installs the Databricks CLI
- Uses a secure `DATABRICKS_TOKEN` for authentication
- Runs `deploy_job.sh` to deploy jobs from the `master` branch

To configure:
1. Set `DATABRICKS_TOKEN` in Travis-CI project settings under *Environment Variables*.
2. Push to the `master` branch to trigger automatic deployment.
