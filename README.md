# EX01 Developing a Simple Webserver

# Date:24-03-2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <body>
        <h1 align="center">Laptop Specification (NAME:NAVINKUMAR.S REG NO:24901075)</h1>
        <ol>
            <li>Device Name     NAVIN</li>
               <li>Processor       13th  Gen Intel(R) Core(TM) i5-1335U 1.30 GHz</li> 
               <li>Installed RAM	16.0 GB (15.7 GB usable)</li>
               <li>Device ID	    15EEA3B2-7EF5-4DEC-903D-577382C3C005</li>
               <li>Product ID	    00342-42708-27268-AAOEM</li>
               <li>System type	    64-bit operating system, x64-based processor</li>
               <li>Pen and touch	No pen or touch input is available for this display</li>
        </ol>     
    </body>
</html>

"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
# OUTPUT:
![Screenshot 2025-03-25 151541](https://github.com/user-attachments/assets/400b7012-0b00-4f77-90e8-08f1bfbdadc7)

![Screenshot 2025-03-25 151519](https://github.com/user-attachments/assets/779b34fb-3989-470a-9da2-a9a4725ee206)

# RESULT:
The program for implementing simple webserver is executed successfully.
