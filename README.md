Automated Testing with Python, Django, and Robot Framework
Introduction
This repository contains a solution for automating testing using Python, Django, and Robot Framework. The system is designed to accept detailed API calls, execute testing steps provided within as Robot Framework tests, and return the test output.

Features
API Development: Built with Django to create an API endpoint that accepts JSON payloads containing test details.
Test Execution: Utilizes Robot Framework to dynamically generate and execute test cases based on the received API calls.
Browser Automation: Uses SeleniumLibrary to perform browser automation for web application testing.
Dynamic Test Generation: Converts JSON-encoded test commands into Robot Framework test suites dynamically.
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/automated-testing.git
Install dependencies:

bash
Copy code
pip install -r requirements.txt
Configure Selenium WebDriver:

Download chromedriver (for Chrome) or geckodriver (for Firefox) and place it in a directory accessible from your system's PATH.
Start the Django server:

bash
Copy code
python manage.py runserver
Usage
Make a POST request to the API endpoint (http://127.0.0.1:8000/testai/tests/v1/execute) with a JSON payload structured as follows:

json
Copy code
{
  "tests":[
    {
      "title":"Test Title",
      "steps":[
        "Open Browser    url='https://example.com'    browser='chrome'",
        "Go To    ${url}"
      ]
    }
  ]
}
Replace "Test Title" with the title of your test and "https://example.com" with the URL you want to navigate to.

The system will execute the provided test steps using Robot Framework and return the test results.

Contributing
Contributions are welcome! If you find any bugs or have suggestions for improvements, please open an issue or submit a pull request.
