# Candidate Filter

## Overview
This project provides a Python-based solution for filtering and retrieving candidate resumes from the HH.ru API. It enables users to authenticate via OAuth, search resumes using specific filters, and process the retrieved data into a structured format using pandas.

## Features
- OAuth authentication with HH.ru API
- Resume search with customizable query parameters
- Extraction and parsing of resume data
- Data transformation and storage in pandas DataFrame

## Prerequisites
To use this project, ensure you have the following:
- Python 3.x installed
- An HH.ru API client ID and client secret
- The required Python packages installed (see below)

## Installation
1. Clone this repository:
   ```sh
   git clone https://github.com/your-username/candidate-filter.git
   cd candidate-filter
   ```

2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
   If `requirements.txt` is not available, manually install dependencies:
   ```sh
   pip install requests pandas openai
   ```

## Usage
1. Update the `client_id`, `client_secret`, and `redirect_uri` in the script:
   ```python
   client_id = 'your-client-id'
   client_secret = 'your-client-secret'
   redirect_uri = 'your-redirect-uri'
   ```

2. Run the script to generate the authorization URL:
   ```sh
   python your_script.py
   ```
   Copy and visit the authorization URL to obtain the authorization code.

3. Replace `'your_authorization_code'` with the actual code received:
   ```python
   authorization_code = 'your_authorization_code'
   ```

4. Execute the script to obtain an access token and fetch resume data.

5. Retrieved resumes will be structured and stored in a pandas DataFrame for further processing.

## Configuration
Modify `query_params` to customize the search criteria:
```python
query_params = {
    'text': 'Data Scientist',
    'area': 1,  # Region ID (1 = Moscow)
    'experience': 'between3And6',  # 3-6 years experience
    'relocation': 'living_but_relocation',
    'industry': 7,  # IT, Telecoms
    'per_page': 1,
    'page': 0
}
```

## Output
The script fetches resume data and transforms it into a structured DataFrame. Key fields include:
- Resume ID
- Candidate Name
- Job Title
- Experience Details
- Education Information
- Contact and Salary Details
- Downloadable Resume Links
