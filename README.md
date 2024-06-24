# Notifier.py Class Documentation

## Overview
Provides different methods for contacting devices in different ways, such as by email or calling. This class uses Selenium Webscraping to preform all actions and thus requires Selenium to be installed. To install Selenium, run the command:

```bash
    pip install selenium
```

## Documentation

- `sendEmailWithDriver(driver: webdriver.Chrome, message: str, recipientEmailAddress: str) -> None`
    Sends an email with an already initialized driver. The method with create a new tab, send the email, then close the tab. Note that this method can take some time to preform, and it will block the current script until completion. The email will come from the address 'no-reply@mail.text-compare.com'
    Args:
    - `driver` - The Selenium Chrome webdriver to use.
    - `message` - The message of the body for the email.
    - `recipientEmailAddress` - The reciever of the email. Make sure it is a valid email address.
    Special thanks to [https://text-compare.com](https://text-compare.com) for allowing this service.
&nbsp;
- `sendEmail(message: str, recipientEmailAddress: str) -> None`
    Sends an email to the given recipient email address. Note that this method can take some time to preform, and it will block the current script until completion. This method opens a webpage and uses a service to send the email (the service was not meant to send emails). The email will come from the address 'no-reply@mail.text-compare.com' \n
    IMPORTANT: There cannot be another webdriver running in the program. Use `sendEmailWithDriver()` if a driver is already opened.\n
    Args:
    - message - The body of the email.
    - recipientEmailAddress - The reciever of the email.\n
    Special thanks to https://text-compare.com for allowing this service.
&nbsp;
- `call(number: str, hangUpAfterSeconds: float=60, countryCode: int | str=1) -> None`
    Calls the given number. Note that this method can take some time to preform, and it will block the current script until completion. The call will come from the number `+31 6 33 27 32 15` (The call is from the Netherlands).\n
    IMPORTANT: There cannot be another webdriver running in the program. The program will have to close the driver, call this method, then reinitialize the driver.\n
    Args:
    - number - The phone number that will be called. The number MUST be in the format `XXX-XXX-XXXX`.
    - hangUpAfterSeconds - The amount of time, in seconds, that the call will remain open before hanging up. Note that it usually takes a couple seconds to establish the call, so it is not recomended to place a value greater than `10`.
    - countryCode - The country code of for the call. The default is `1` (America). Do NOT include the '+' sign.\n
    Special thanks to https://globfone.com/call-phone/ for this service.

&nbsp;
&nbsp;
&nbsp;