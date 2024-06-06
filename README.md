# Cookie Clicker Automation

This repository contains a Python script designed to automate the clicking of cookies in the Cookie Clicker game using Selenium WebDriver.

## Overview

The script `cookieclicker.py` is built using Python and Selenium, a powerful tool for controlling web browsers through programs and performing browser automation. This script specifically targets the popular Cookie Clicker game, automating the process of clicking the big cookie to accumulate points efficiently.

## Repository Contents

- `cookieclicker.py`: The primary script responsible for automating cookie clicks.
- `chromedriver.exe`: The ChromeDriver executable that allows Selenium to interface with the Chrome browser.
- `cookiclicker_output.webm`: A screen recording demonstrating the script's functionality.

## Requirements

Before running the script, ensure you have the following installed on your system:

- Python 3.x
- Selenium library for Python
- Google Chrome browser
- ChromeDriver (matching the version of your Chrome browser)

## Installation Instructions

### Step 1: Clone the Repository

First, clone the repository to your local machine using the following command:

```sh
git clone https://github.com/yourusername/Cookie_clicker.git
cd Cookie_clicker
```

### Step 2: Install Selenium

Install the Selenium package using pip:

```sh
pip install selenium
```

### Step 3: Download ChromeDriver

Download the ChromeDriver that matches your version of Chrome from the [official site](https://sites.google.com/a/chromium.org/chromedriver/downloads) and place the `chromedriver.exe` file in the same directory as `cookieclicker.py`.

## Detailed Explanation of `cookieclicker.py`

The `cookieclicker.py` script is designed to automate the Cookie Clicker game using Selenium WebDriver. Below is a detailed breakdown of what each part of the script does:

### Importing Required Libraries

The script starts by importing necessary libraries from Selenium and the `time` module for handling time-based operations:

```python
from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import time
```

### Setting Up the WebDriver

The script sets up the WebDriver using the ChromeDriver executable:

```python
service = Service(executable_path="chromedriver.exe")
driver = webdriver.Chrome(service=service)
```

### Navigating to Cookie Clicker Game

The WebDriver is instructed to navigate to the Cookie Clicker game URL:

```python
driver.get("https://orteil.dashnet.org/cookieclicker/")
```

### Handling Language Selection

The script waits for the language selection element to appear and then clicks on "English":

```python
WebDriverWait(driver, 5).until(
    EC.presence_of_element_located((By.XPATH, "//*[contains(text(), 'English')]"))
)

language = driver.find_element(By.XPATH, "//*[contains(text(), 'English')]")
language.click()
```

### Automating Cookie Clicking

After selecting the language, the script waits for the big cookie element to be present and then enters an infinite loop where it continuously clicks the cookie:

```python
WebDriverWait(driver, 5).until(
    EC.presence_of_element_located((By.ID, "bigCookie"))
)

cookie = driver.find_element(By.ID, "bigCookie")

while True:
    cookie.click()
    cookies_count = driver.find_element(By.ID, "cookies").text
    print(cookies_count)
```

- **Wait for Big Cookie**: The script waits until the big cookie element is located using its ID.
- **Clicking the Big Cookie**: In an infinite loop, the script continuously clicks the big cookie.
- **Display Cookie Count**: After each click, it retrieves and prints the current cookie count from the webpage.

## Usage

To run the script, use the following command:

```sh
python cookieclicker.py
```

The script will open the Cookie Clicker game in a Chrome browser window, select "English" as the language, and start clicking the big cookie automatically.

## Screen Recording

A screen recording (`cookiclicker_output.webm`) is included in the repository to demonstrate the script's functionality in action.

## Conclusion

Contributions are welcome! If you have suggestions or improvements, please let me know and researchers are requested to use this block of code in their respective projects.
I hope this helps, thank you.


