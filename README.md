# Weather Dashboard

This is a Python-based weather dashboard project that fetches weather data from the OpenWeather API, processes it, and stores the data in an AWS S3 bucket. The project automatically creates the S3 bucket if it doesn't exist. The project is designed to demonstrate how to integrate different technologies such as OpenWeather API, AWS S3, and Python to create a useful weather monitoring tool.

## Features

- Fetches current weather data for multiple cities.
- Automatically creates an AWS S3 bucket if it doesn't exist.
- Stores weather data in AWS S3 as JSON files.
- Uses AWS SDK (Boto3) to interact with S3.
- Configurable via environment variables.

## Prerequisites

Before running this project, ensure you have the following:

- Python 3.8 or higher
- An active OpenWeather API key (get yours [here](https://openweathermap.org/))
- AWS account (the script will automatically create the S3 bucket for you)
- Python `requests` and `boto3` libraries
- **AWS CLI** installed and configured on your machine

## Installation

### 1. Clone this repository

Clone the repository to your local machine:

            
    git clone https://github.com/almathasoria/aws_weather_dashboard.git
    cd aws_weather_dashboard

2. Set up the Python Virtual Environment
   
Create a virtual environment for the project:
    
            
      python -m venv .venv

Activate the virtual environment:

On Windows:
    
              
              .\.venv\Scripts\activate

3. Install Dependencies
Install the required Python dependencies from requirements.txt:

    ```bash
      pip install -r requirements.txt
    
4. Set up Environment Variables
Create a .env file in the root directory and add the following content:

    ```bash
    OPENWEATHER_API_KEY=your_openweather_api_key
    AWS_BUCKET_NAME=your_unique_s3_bucket_name
    
* Replace your_openweather_api_key with your OpenWeather API key.
* Replace your_unique_s3_bucket_name with the name you want to assign to your S3 bucket (it will be created automatically if it doesn't exist).
5. Install AWS CLI
  Install AWS CLI if you haven’t already:

Windows: Download and install the AWS CLI from [here](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#install-on-windows).


6. Configure AWS CLI
Once the AWS CLI is installed, you need to configure it with your AWS credentials.

Run the following command to configure your AWS credentials:
    
        
        aws configure
      
You will be prompted to enter the following details:

AWS Access Key ID: Your AWS access key (get this from the AWS IAM console).
AWS Secret Access Key: Your AWS secret key (get this from the AWS IAM console).
Default region name: Choose your preferred AWS region, for example us-east-1.
Default output format: Choose json (or another format if preferred).

7. Run the Weather Dashboard
Now, you're ready to run the weather dashboard:

    ```bash
    python src/weather_dashboard.py
    
The script will:
Fetch weather data for the predefined cities (Philadelphia, Seattle, and New York).
Display the weather details (temperature, humidity, conditions, etc.).
Automatically create an S3 bucket (if it doesn't already exist) and store the weather data in the bucket as JSON files.
## Troubleshooting
401 Unauthorized Error: If you encounter a 401 Unauthorized error while fetching weather data, ensure that your OpenWeather API key is correctly placed in the .env file. You can generate a new key here.

AWS CLI and S3 Permissions: If the script fails to upload data to S3, ensure your AWS CLI is configured with the correct permissions to write to S3. The script will create the bucket automatically, but it still needs permission to upload data to it. You can check the permissions of your AWS IAM user and make sure it has the s3:PutObject permission.

## Contributing
Contributions to this project are welcome! To contribute:

1. Fork this repository.
2. Create a new branch (git checkout -b feature-branch).
3. Make your changes and commit them (git commit -am 'Add new feature').
4. Push to your branch (git push origin feature-branch).
5. Create a pull request.

## Acknowledgements
OpenWeatherMap API for weather data.
AWS for providing cloud storage (S3).
Python and its libraries for making it all work!
30 Days DevOps Challenge by the Cozy Cloud Crew


