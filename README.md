# Developing a Simple Webserver
## AIM:
To Develop a webserver to display about top five web application development frameworks.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<!DOCTYPE html>
<html>
<head>
<titlt>MY WEBSERVER</title>
</head>
<body>
<h1>WELCOME TO MY SIMPLE WEBSERVER</h1>
</body>
</html>
"""

class HelloHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request recieved")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())


server_address = ('', 8080)
httpd = HTTPServer(server_address, HelloHandler)
print("my webserver is running.....")
httpd.serve_forever()
```

## OUTPUT:

### SERVERSIDE OUTPUT
![Screenshot 2023-04-15 224618](https://user-images.githubusercontent.com/112475766/232242225-cf215eb4-179a-4352-961e-f5aafa09f21c.png)

### CLIENTSIDE OUTPUT
![Screenshot 2023-04-15 224715](https://user-images.githubusercontent.com/112475766/232242232-e3da727d-3952-4950-aab7-25d4a2e280d3.png)

## RESULT:

Thus the webserver is developed to display about top five programming languages.
