# 🌦️ OpenWeather Current Data Pull-Up

**Date:** 31st October 2025  
**Author:** Benjamin Ishimwe  

## 📝 Description
This project demonstrates how to use the OpenWeather API to fetch real-time weather data for selected cities.  
The retrieved data is processed in Python, converted into a Pandas DataFrame, and visualized in a mock dashboard.
## 🎯 PROJECT OBJECTIVES
- **Set up API Access:** Register on the OpenWeather platform and generate an API key for accessing weather data.
- **Fetch Current Weather Data:** Use Python to send requests to the OpenWeather API and collect real-time weather information.
- **Data Handling with Pandas:** Convert API responses into structured Pandas DataFrames for analysis.
- **Mock Dashboard Creation:** Use Claude AI or ChatGPT to design a prototype dashboard that visualizes weather insights.
- **Documentation:** Record and explain the entire process for reproducibility and learning purposes.
 
This project is a beginning of building a data pipeline. It consists of pulling weather data conditions of various cities from Open weather platform. Convert them to data frame using python/pandas.

## 🌍 Data Source
- **OpenWeather:** [https://openweathermap.org/guide](https://openweathermap.org/guide)

---

## 🧭 Methodology
a) Explored OpenWeather’s free plans and registered for an API key.  
b) Used the **`requests`** module in Python to fetch current weather data for ten major African cities.  
c) Structured the retrieved data into a **Pandas DataFrame** for easy manipulation and analysis.  
d) Created **bar charts** with **Matplotlib** to visually compare the cities’ temperature levels.

---

## 📊 Results
The analysis revealed that:
- **Kinshasa**, **Abuja**, and **Dakar** recorded the **highest temperatures** among the selected cities.  
- Other cities showed moderate or relatively lower temperature levels at the time of data retrieval.

---

## 🧩 Technologies Used
- **Python 3**  
- **Requests** (for API calls)  
- **Pandas** (for data processing)  
- **Matplotlib** (for visualization)

## PREREQUISITE
Before running this project, ensure you have the following installed:
 - Python 3.8 or higher
 - MYSQL 12 or higher
 - PIP (Python package manager)
 - Ubuntu Server or Linux-based OS

## INSTALLATION
### SYSTEM REQUIREMENTS SETUP (UBUNTU SERVER)
1. UPDATE SYSTEM PACKAGE
     bash
     sudo apt update
     sudo apt upgrade -y
2. INSTALL PYTHON 3
     bash
     sudo apt install python3
     sudo apt install python 3.12.3
3. INSTALL PYTHON PACKAGES
      bash
      sudo apt install python3-pip
      sudo apt install python3-pymysql
      sudo apt install python3-requests
      sudo apt install python3-datetime
   
4. CLONE THE REPOSITORY
     bash
     git clone https://github.com/IBen655/Open_weather_project.git
     cd Open_weather_project

<!-- CREATE VIRTUAL ENVIRONMENT
   bash
   python -m venv venv

   <!-- Activate virtual environment -->
   <!-- On Windows: -->
   venv\Scripts\activate
   <!-- On Mac/Linux: -->
   source venv/bin/activate
-->

5. SETUP MYSQL DATABASE
     bash
     <! -- Install MySQL Server (if not already installed) -->
     sudo apt update
     sudo apt install mysql-server

     <! -- Start MySQL service -->
     sudo systemctl start mysql
     sudo systemctl enable mysql

     <! -- Check MySQL status -->
     sudo systemctl status mysql

     <! -- Access MySQL as root -->
     sudo mysql -u root -p

     <! -- Inside MySQL shell, create database and user -->
     CREATE DATABASE your_database_name;
     CREATE USER 'your_username'@'localhost' IDENTIFIED BY 'your_password';
     GRANT ALL PRIVILEGES ON your_database_name.* TO 'your_username'@'localhost';
     FLUSH PRIVILEGES;
     EXIT;

6. 

## 🪪 License
This project is for educational purposes and may be reused with proper attribution.
