## Weather Dashboard Environment Setup

This repository walks through the process of setting up your environment to set up a weather dashboard that pulls weather data from cities using the OpenWeather API and uploads it to an s3 Bucket.


## 1 Installation of Tools

### 1.1 Install Python

- Install python from this link: [Python Installation](https://www.python.org/downloads/)

- Confirm python installation by running:
```sh
python3 --version
```

- confirm pip has also been installed with this command:
```sh
pip --version
```

### 1.2 Create Your AWS Account and download the AWS CLI

- Create your AWS Account by visiting the [AWS Free Tier Signup Page](https://aws.amazon.com/free/?p=ft&z=subnav&loc=1&all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all&awsf.Free%20Tier%20Categories=*all) and click create account

- Create an IAM user by going to the IAM Section and click create user

- Generate credentials for the user, and copy the Secret Key and Access Key

- Download the AWS CLI from this link : [Amazon CLI Install Page](https://aws.amazon.com/cli/)

- Run the command to configure your aws cli:
```sh
aws configure
```

- Input your access and secret key
- Enter your default region; preferably us-east-1
- Set your default output format to json


## 2 Workflow 

### 2.1 Get OpenWeather API Key

- Get the OpenWeather API Key by signing up to this page: [OpenWeatherAPI](https://openweathermap.org/api)
- Once logged in, navigate to API Keys and generate a new key. Copy the generated key.

### 2.2 Set up Project Directory

- Create the Structure for the Project
```sh
mkdir weather-dashboard
cd weather-dashboard
mkdir src tests data
touch src/__init__.py src/weather_dashboard.py
touch requirements.txt README.md .env
echo ".env" >> .gitignore
echo "__pycache__/" >> .gitignore
echo "*.zip" >> .gitignore
echo "boto3==1.26.137" >> requirements.txt 
echo "python-dotenv==1.0.0" >> requirements.txt 
echo "requests==2.28.2" >> requirements.txt 
```

### 2.3 Create a Virtual Environment

- Create a virtual environment to ensure dependencies installed for this project doesn't affect other projects based on versioning
```sh
python3 -m venv venv
source venv/bin/activate
```

### 2.4 Install requirements
- Install requirements with the command:
```sh
pip install -r requirements.txt
```

#### 2.5 Environment Variables

Add the following environment variables to your .env file and also add venv to your .gitignore

```sh
OPENWEATHER_API_KEY="[API KEY from OpenWeather]"
AWS_BUCKET_NAME="[UNIQUE BUCKET NAME]"
echo "venv/" >> .gitignore
```

## 3 RUN CODE

- Run the code with the command
```sh
python3 src/weather_dashboard.py
```

- You will notice the bucket has been created along with weather data for the cities in the code






