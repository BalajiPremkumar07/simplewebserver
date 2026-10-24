# EX01 Developing a Simple Webserver
## Date:29-9-2026

## AIM:
To develop a simple webserver to serve html pages and display the Windows Specifications of your Laptop.

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
content = """
      
<html>
    <head>
        <title>webpage </title>
    </head>
        <body bgcolor="lime">
            <h1 align="center">BALAJI-26007368</h1>
            <h2 align="center">MY SYSTEM CONFIGURATION</h2>
            <table border="2">
                <tr>
                    <th>S.No</th>
                    <th>Device Type</th>
                    <th>Device info</th>
                </tr>
                <tr>
                    <td>1.</td>
                    <td>Device Name </td>
                    <td>TL15-53M-G2</td>
                </tr>
                <tr>
                    <td>2.</td>
                    <td>Processor</td>
                    <td>Intel(R) Core(TM) 5 210H (2.20 GHz)</td>
                </tr>
                <tr>
                    <td>3.</td>
                    <td>Installed RAM</td>
                    <td>16.0 GB </td>
                </tr>
                <tr>
                    <td>4.</td>
                    <td>Graphics Card</td>
                    <td>Intel(R) Graphics (128 MB)</td>
                </tr>
                <tr>
                    <td>5.</td>
                    <td>Storage</td>
                    <td>138 GB of 477 GB used</td>
                </tr>
                <tr>
                    <td>6.</td>
                    <td>device ID</td>
                    <td>4D11B0C1-8709-469D-8B27-0BA79F27BBA3</td>
                </tr>
                <tr>
                    <td>7.</td>
                    <td>Product ID</td>
                    <td>00342-42943-41969-AAOEM</td>
                </tr>
                <tr>
                    <td>8.</td>
                    <td>System Type</td>
                    <td>64-bit operating system, x64-based processor</td>
                </tr>
                <tr>
                    <td>9.</td>
                    <td>Pen and Touch Support</td>
                    <td>No pen or touch input is available for this display</td>
                </tr>


            </table>
        
        
        
        
        </body>

</html>  
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Client request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my own webserver is running successfully...")
httpd.serve_forever()
```



## OUTPUT:
webpage
![alt text](image.png)

serverpage
![alt text](image-1.png)
## RESULT:
The program for implementing simple webserver is executed successfully.
