# EX01 Developing a Simple Webserver
## Date:7.10.25

## AIM:
To develop a simple webserver to serve html pages and display the Device Specifications of your Laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

# HTML content about TCP/IP protocol
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laptop Configuration Details</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            margin: 0;
            padding: 20px;
        }
        h1 {
            color: #333;
        }
        .container {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            margin: 0 auto;
        }
        .info-item {
            margin: 10px 0;
        }
        .label {
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Laptop Configuration Details</h1>
        <div class="info-item"><span class="label">Operating System:</span> {{ system_info['OS'] }} ({{ system_info['OS Version'] }})</div>
        <div class="info-item"><span class="label">Machine Type:</span> {{ system_info['Machine'] }}</div>
        <div class="info-item"><span class="label">Processor:</span> {{ system_info['Processor'] }}</div>
        <div class="info-item"><span class="label">RAM:</span> {{ system_info['RAM (GB)'] }} GB</div>
        <div class="info-item"><span class="label">CPU Cores:</span> {{ system_info['CPU Cores'] }}</div>
        <div class="info-item"><span class="label">Logical CPUs:</span> {{ system_info['Logical CPUs'] }}</div>
    </div>
</body>
</html>

"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

# Run the web server
server_address = ('', 8000)
httpd = HTTPServer(server_address, myhandler)
print("My TCP/IP presentation webserver is running on port 8000...")
httpd.serve_forever()
```


## OUTPUT:
![output1](https://github.com/user-attachments/assets/ffe8f402-46b1-47df-b067-9063d426f7b0)
![output2](https://github.com/user-attachments/assets/9ccb075f-4750-4a88-b5c6-47409df42c4a)


## RESULT:
The program for implementing simple webserver is executed successfully.
