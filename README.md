<h1>PWNForm - CSRF PoC Generator</h1>
<img src=https://github.com/user-attachments/assets/9fa34937-be16-4743-9a2d-a906e5868b1a onerror=x width=800 />

---


<img src=https://github.com/user-attachments/assets/cd18729e-8440-4c96-8ac5-bb8822179b60 onerror=pwnform.gif width=800 />


<h1>Overview</h1>

PWNForm is an automated Bash script that generates a CSRF (Cross-Site Request Forgery) Proof-of-Concept (PoC) attack form. It allows users to generate CSRF PoC exploits that can be used to test web applications for CSRF vulnerabilities (Ex:- By Chaining with XSS in a POST Request).

With PWNForm, you can:

Easily create an interactive CSRF attack form.

Generate an HTML-based PoC that allows parameter modification.

Automatically serve the PoC via a local Python HTTP server on the user specified port (defaulting to 8000)

Open the PoC in a browser instantly.



---

<h1>Features</h1>

1.<h3>Interactive Input</h3> – The script prompts the user for a target URL, HTTP method, and request body.

2.<h3>Automatic HTML Generation</h3> – A properly formatted CSRF attack form is generated based on user input.

3.<h3>Local HTTP Server</h3> – A Python HTTP server is launched to serve the PoC file.

4.<h3>Browser Auto-Launch</h3> – Opens the PoC automatically in the browser for immediate testing.

5.<h3>Port Selection</h3> – Allows users to specify a custom port for the HTTP server.

6.<h3>Handles URL-Encoding</h3> – Decodes and properly formats URL-encoded request bodies.


---

<h1>Installation</h1>

Prerequisites

Ensure you have the following installed:

Bash (Linux/macOS/WSL recommended)

Python3 (for the built-in HTTP server)

xdg-open (For opening the preferred application for opening html files)


Clone the Repository

git clone https://github.com/Demgainschill/PWNForm.git
cd PWNForm
./pwnform -p 8070

---

<h1>Usage</h1>

Basic Usage

Run the script with:

./pwnform.sh  ( Defaults to Port:8000)

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

Start a local Python HTTP server on the user specified port (Default:8000).

Opens the PoC in your default browser using xdg-open hosted through python HttpServer Module.

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




<img src=https://github.com/user-attachments/assets/56def11a-062a-4a33-bc01-45ff4c4721db onerror=pwnfid.mp4 width=800 />

