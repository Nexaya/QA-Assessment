```markdown
# Python Automation Instructions

## Task:
- Write an automated test script using **Python** to test the login functionality of a web-based application.
- Ensure that both valid and invalid login scenarios are covered.

## Requirements:
- Use **Selenium** or any other Python automation framework.
- Ensure to include assertions for success and failure scenarios.

## Deliverables:
- Submit your Python code along with instructions to run the test.
- Include a `requirements.txt` file for any external dependencies.

---

## Sample:
```python
from selenium import webdriver

driver = webdriver.Chrome(executable_path="/path/to/chromedriver")
driver.get("http://example.com/login")

# Perform login test
username = driver.find_element_by_name("username")
password = driver.find_element_by_name("password")

username.send_keys("valid_username")
password.send_keys("valid_password")
driver.find_element_by_name("login").click()

# Assert login success
assert "Dashboard" in driver.title

driver.quit()
