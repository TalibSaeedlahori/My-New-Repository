# My-New-Repository
My new repository will help many others
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

def login_to_aiou_cms(username, password):
    # Replace with the path to your WebDriver executable
    driver = webdriver.Chrome('/path/to/chromedriver')

    # Replace with the URL of the AIOU CMS login page
    driver.get('https://example.com/login')

    # Replace with appropriate selectors for the username and password fields on the login page
    username_field = driver.find_element(By.CSS_SELECTOR, 'input[name="username"]')
    password_field = driver.find_element(By.CSS_SELECTOR, 'input[name="password"]')

    # Enter the username and password
    username_field.send_keys(username)
    password_field.send_keys(password)

    # Submit the login form
    password_field.send_keys(Keys.RETURN)

    # Wait for the page to load after login (replace with appropriate condition if necessary)
    WebDriverWait(driver, 10).until(EC.url_contains('dashboard'))

    # Add any additional actions you want to perform after successful login
    # For example, you can extract information or navigate to specific pages

    # Close the browser
    driver.quit()

# Replace with your AIOU CMS username and password
username = 'your-username'
password = 'your-password'

login_to_aiou_cms(username, password)
