from appium import webdriver

desired_capabilities = {
    "platformName": "Android",
    "platformVersion": "9",
    "deviceName": "emulator-5554",
    "appPackage": "com.example.android",
    "appActivity": ".MainActivity",
    "automationName": "UiAutomator2"
}

driver = webdriver.Remote("http://localhost:4723/wd/hub", desired_capabilities)

# Example test scenario
    # My test steps go here
    element = driver.find_element_by_id("com.example.android:id/button")
    element.click()
    # Assuming there's a text field with id 'input_field', we'll send some text to it
    text_field = driver.find_element_by_id("com.example.android:id/input_field")
    text_field.send_keys("Hello, Appium!")

    # Verify if the text was entered correctly
    assert text_field.text == "Hello, Appium!"

    print("Test passed!")
except Exception as e:
    print("Test failed!", e)

driver.quit()
