## Dog API Request Pipeline

This project is a small Python pipeline that makes a GET request to the Dog CEO API, parses the JSON response, logs every major step, loads configuration from a YAML file, and loads environment variables from a .env file. It also saves the full JSON response to dog.json and reads it back for verification. This structure mirrors how data engineers build lightweight API ingestion pipelines.

-----------------------------
## Project Overview

The script performs:

1. Setting up logging with timestamps and levels.
2. Loading environment variables from .env.
3. Reading a configuration file (config.yaml) to get the API URL.
4. Making a GET request to the Dog API.
5. Logging the request status code.
6. Parsing the JSON response safely.
7. Logging the "message" value, which contains the dog image URL.
8. Saving the JSON response to dog.json.
9. Reading the saved dog.json to confirm it was written correctly.
10. Handling all major operations with try/except and proper logging.

This project practices real-world skills such as logging, config files, JSON handling, basic API calls, and error management.

-----------------------------
## Features:

- GET request using requests
- Structured logging with timestamps
- YAML configuration file for the API URL
- Environment variable handling using python-dotenv
- JSON parsing and validation
- Saving JSON to disk and reading it back
- Error handling and clear logging for every step

Project Structure:

Dog-API-Request/
│
├── dog_api_request.py
├── dog.json
├── .env
└── config/
      └── config.yaml

config.yaml:
api_url: "https://dog.ceo/api/breeds/image/random"

.env:
API_KEY="12345TESTKEY"

-----------------------------
## How It Works:

The script sets up logging using the Python logging module.

1. Environment variables (like API keys) are loaded using load_dotenv().
2. The Dog API URL is loaded from config.yaml.
3. A GET request is made to the Dog API with optional headers.
4. The script logs the response status code.
5. JSON is parsed and the "message" field (dog image URL) is extracted.
6. JSON is saved to dog.json using a file write operation.
7. The saved file is opened and printed to verify the output.
   
-----------------------------
## Example Output
Sample log output looks like:

INFO - API key loaded from environment variables.
INFO - Config file loaded successfully.
INFO - Starting API request...
INFO - Status code: 200
INFO - Parsing JSON response...
INFO - JSON parsed successfully.
INFO - Dog image: https://images.dog.ceo/breeds/terrier-norfolk/n02094114_2436.jpg
INFO - JSON saved successfully.
{'message': 'https://images.dog.ceo/breeds/sheepdog-shetland/n02105855_13071.jpg', 'status': 'success'}

-----------------------------
## Requirements
Install dependencies:
pip install requests pyyaml python-dotenv

## Running the Script:
python dog_api_request.py

You will see log messages in the terminal and a new file named dog.json containing the JSON response from the API.
