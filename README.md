# 🌦️ OpenWeather Current Data Pull-Up

**Date:** 10st December 2025  
**Author:** Benjamin Ishimwe  

## 📝 Description
This project fetches data from external APIs and stores it in a database for persistent storage and easy retrieval. It automates the process of collecting data from various API endpoints and organizing it in a structured database format.

## 🎯 PROJECT OBJECTIVES
- **Set up API Access:** Register on the OpenWeather platform and generate an API key for accessing weather data.
- **Fetch Current Weather Data:** Use Python to send requests to the OpenWeather API and collect real-time weather information.
- **Data Storage:** Validates and processes API responses, and stores data efficiently in a database.
- **Error Handling and Debugging:** Handles errors and retries failed requests.
- **Data Automation and Cron Job:** Supports scheduled/automated data fetching and Logs all operations for monitoring and debugging
- **Report Building using Powerbi:** Build a report using PowerBI and connect to Mysql server for automation
- **Documentation:** Record and explain the entire process for reproducibility and learning purposes.
 
This project is a beginning of building a data pipeline. It consists of pulling weather data conditions of various cities from Open weather platform. 

## 🌍 Data Source
- **OpenWeather:** [https://openweathermap.org/guide](https://openweathermap.org/guide)

---

## 🧭 Methodology
a) Explore OpenWeather’s free plans and registered for an API key.  
b) Use the **`requests`** module in Python to fetch current weather data for 21 major African cities.  
c) Connect API source to database and store every fetch batch to the database.
d) Initiate a scheduling job for continous fetching.
d) Build a PowerBI Report and connect it to the database for Automation.

---

## 📊 Results
The analysis revealed that:
- **Kinshasa**, **Abuja**, and **Dakar** recorded the **highest temperatures** among the selected cities.  
- Other cities showed moderate or relatively lower temperature levels at the time of data retrieval.

---

## 🧩 Technologies Used
- **Programming Languages:** Python 3, SQL  
- **Database:** MySQL Server
- **Database Driver:** PyMySQL  
- **API Communication:**  requests library
- **Environment Management:** python-dotenv
- **Scheduling Work:** Crontab
- **Server OS:** Ubuntu Server (Linux)
 
---

## PREREQUISITE
Before running this project, ensure you have the following installed:
 - Python 3.8 or higher
 - MYSQL 8 or higher
 - PIP (Python package manager)
 - Ubuntu Server or Linux-based OS

## INSTALLATION
### SYSTEM REQUIREMENTS SETUP (UBUNTU SERVER)
1. UPDATE SYSTEM PACKAGE
     bash
   
     sudo apt update
    
     sudo apt upgrade -y 
3. INSTALL PYTHON 3
     bash
   
     sudo apt install python3
    
     sudo apt install python 3.12.3
   
5. INSTALL PYTHON PACKAGES
      bash
   
      sudo apt install python3-pip
   
      sudo apt install python3-pymysql
   
      sudo apt install python3-requests
   
      sudo apt install python3-datetime 
   
7. CLONE THE REPOSITORY
     bash
     git clone https://github.com/IBen655/Open_weather_project.git
   
     cd Open_weather_project

9. CREATE VIRTUAL ENVIRONMENT
   You may want to use python virtual environment. It is not mandatory to use it for you can use server system enviroment.
   bash
   
   python -m venv venv

   <!--Activate virtual environment-->
   
   <!--On Windows:-->
   
   venv\Scripts\activate 
   
   <!--On Mac/Linux:-->
   
   source venv/bin/activate
   

11. SETUP MYSQL DATABASE
     bash
    
     <! --Install MySQL Server (if not already installed)-->
    
     sudo apt update
    
     sudo apt install mysql-server

     <! --Start MySQL service-->
    
     sudo systemctl start mysql
    
     sudo systemctl enable mysql

     <! --Check MySQL status-->
    
     sudo systemctl status mysql

     <! --Access MySQL as root-->
    
     sudo mysql -u root -p

     <! --Inside MySQL shell, create database and user-->
     CREATE DATABASE your_database_name;
    
     CREATE USER 'your_username'@'localhost' IDENTIFIED BY 'your_password';
    
     GRANT ALL PRIVILEGES ON your_database_name.* TO 'your_username'@'localhost';
    
     FLUSH PRIVILEGES;
    
     EXIT;

13. CONFIGURATION
     Create a .env file in the project root with the following variables:
            env
    
            # API Configuration
    
            API_KEY=your_api_key_here
    
            API_BASE_URL=https://api.example.com
    

            # Database Configuration
            DB_HOST=localhost
            DB_PORT=3306
            DB_NAME=your_database_name
            DB_USER=your_username
            DB_PASSWORD=your_password
   
   8. DEPENDENCIES(REQUIREMENT.TXT)
        PyMySQL==1.1.0
      
        requests==2.31.0
      
        python-dotenv==1.0.0
      
   ** Note **: On Ubuntu Server, packages are installed system-wide using:
             bash
      
             sudo apt install python3-requests
      
             sudo pip3 install pymysql python-dotenv

## <img src="https://www.flaticon.com/free-icon/database_4562989" width="30" height="30"> DATABASE SCHEMA
     This project creates and uses one project namely:

   ** WEATHER_DATA **
            -CITY_NAME VARCHAR(20) NOT NULL
            -COUNTRY VARCHAR(20)
            -TIME TIMESTAMP
            -TEMPERATURE FLOAT
            -TEMP_MIN FLOAT
            -TEMP_MAX FLOAT
            -HUMIDITY INT
            -PRESSURE INT
            -SEA_LEVEL INT
            -GROUND_LEVEL INT
            -WEATHER VARCHAR(20)
            -DESCRIPTION VARCHAR(20)
            -WIND_SPEED FLOAT
            -WIND_DIRECTION INT
            -CLOUDINESS INT
## USAGE
   Run this script for the first time
       bash
       
       python3 weather_data.py
       
   The script will:
         1. Connect to the OpenWeatherMap API
         2. Fetch 5-day forecast data for each configured city
         3. Insert the data into your MySQL database
         4. Log progress and any errors encountered
         
 ## <img src="Screenshot 2025-12-10 115503.png" width="30" height="30"> CITIES COVERED
The script fetches weather data for the following African cities:
            -Kigali (Rwanda)
            -Kampala (Uganda)
            -Nairobi (Kenya)
            -Libreville (Gabon)
            -Kinshasa (DR Congo)
            -Cairo (Egypt)
            -Tripoli (Libya)
            -Abuja (Nigeria)
            -Lagos (Nigeria)
            -Accra (Ghana)
            -Dakar (Senegal)
            -Durban (South Africa)
            -Johannesburg (South Africa)
            -Dar es Salaam (Tanzania)
            -Bamako (Mali)
            -Addis Ababa (Ethiopia)
            -Algiers (Algeria)
            -Lusaka (Zambia)
            -Tunis (Tunisia)
            -Bangui (Central African Republic)
            -Lilongwe (Malawi)
You can fetch for the one you like. This is just a sample.

## <img src="Screenshot 2025-12-10 120824.png"  width="30" height="30"> DATA COLLECTED
For each forecast entry, the following data is stored:

        *<img src="Screenshot 2025-12-10 115756.png" width="30" height="30"> City name and country
        *<img src="https://www.flaticon.com/free-icon/time_5521277"  width="30" height="30"> Timestamp
        *<img src="https://www.flaticon.com/free-icon/temperature_9549128?term=temperature&page=1&position=26&origin=search&related_id=9549128" width="30" height="30"> Temperature (current, min, max)
        *<img src="https://www.flaticon.com/free-icon/humidity_8923419?term=humidity+sensor&page=1&position=2&origin=search&related_id=8923419"  width="30" height="30"> Humidity
        *<img src="https://www.flaticon.com/free-icon/pressure-gauge_4117387?term=atmospheric+pressure&page=1&position=5&origin=search&related_id=4117387"  width="30" height="30"> Atmospheric pressure
        *<img src="http://flaticon.com/free-icon/sea-level_3095218?term=sea+level&page=1&position=38&origin=search&related_id=3095218"  width="30" height="30"> Sea level and ground level pressure
        *<img src="https://www.flaticon.com/free-icon/atmospheric-conditions_18005339?term=weather+condition&page=1&position=6&origin=search&related_id=18005339"  width="30" height="30"> Weather condition and description
        *<img src="https://www.flaticon.com/free-icon/windock_5378202?term=wind+speed&page=1&position=22&origin=search&related_id=5378202"  width="30" height="30"> Wind speed and direction
        *<img src="https://www.flaticon.com/free-icon/clouds_414825?term=atmospheric+cloud&page=1&position=9&origin=search&related_id=414825"  width="30" height="30"> Cloud coverage percentage

## LOGGING
The script uses Python's logging module to track operations. Logs include:

         -Successful data fetches
         -Number of records inserted
         -Duplicate records skipped
         -Any errors encountered

## ERROR HANDLING

      *API request failures are logged with error messages
      *Database connection errors are caught and logged
      *Duplicate entries are automatically skipped using INSERT IGNORE
## SCHEDULED SCRIPT RUNNING
     + Initiate a cron job using crontab
     + schedule a cron job every 3 hours
     
## SECURITY NOTE

⚠️ Warning: This script contains a hardcoded database password and API key. For production use:

             -Store credentials in environment variables
             -Use a configuration file that's excluded from version control
             -Never commit sensitive credentials to your repository
## 🪪 License
This project is for educational purposes and may be reused with proper attribution.
