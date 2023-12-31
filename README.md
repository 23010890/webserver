# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

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
Creating a Simple Web Server to serve a page: 
If we have an HTML file, mywebpage.html, that we want to serve: 
<!DOCTYPE html> 
<html> 
<head> 
<title>Using Python's SimpleHTTPServer Module</title> 
<style> 
#rectangle { 
height: 50px; 
width: 100px; 
background-color: #00f28f; 
} 
</style> 
</head> 
<body> 
<h2>Rectangle served by SimpleHTTPServer</h2> 
<div id="rectangle"></div> 
</body> 
</html>


We can use our custom handler to serve it on any path we want. In this example       
we'll just serve it on the root path, /: 
import http.server 
import socketserver 
class MyHttpRequestHandler(http.server.SimpleHTTPRequestHandler): 
def do_GET(self): 
if self.path == '/': 
self.path = 'mywebpage.html' 
return http.server.SimpleHTTPRequestHandler.do_GET(self) 

handler_object = MyHttpRequestHandler 
PORT = 8000 
my_server = socketserver.TCPServer(("", PORT), handler_object) 
 
my_server.serve_forever()
```
## OUTPUT:
# CLIENT OUTPUT:
![output](./CLIENT%20OUTPUT.png)
# SERVER OUTPUT:
![output](./SERVER%20OUTPUT.png)
## RESULT:
The program is executed succesfully
