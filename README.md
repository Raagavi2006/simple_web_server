# EX01 Developing a Simple Webserver

# Date:05.12.2024
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

       from http.server import HTTPServer, BaseHTTPRequestHandler
       content = """
       <html>
    <head>
        <title>Laptop Configurations</title>
        <center>
            <h1 style="color: black">My Laptop Configurations</h1><hr>
        </center>
    </head>
    <body style="background-color: oldlace;">
        <style>
            table,th,td{
            text-align: center;
            border:3px solid black;
            border-collapse: collapse;
            height:70px;
            width: 1000px;
            vertical-align: center;
            margin-top: 3%;
        }
        h1{
            padding:2%;
            font-family:'Times New Roman', Times, serif;
        }
        th{
            font-style: bold;
            font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
            font-size:xx-large;
            font-weight: 7000;
        }
        td{
            font-style:normal;
            font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
            font-size: larger;
            font-weight: 550;
        }
        </style>
        <center>
            <table>
                <tr>
                    <th style="background-color: burlywood;">Configurations</th>
                    <th style="background-color: wheat;">Details</th>
                </tr>
                <tr>
                    <td style="background-color: tan;">Processor</td>
                    <td style="background-color: bisque;">13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</td>
                </tr>
                <tr>
                    <td style="background-color: tan;">RAM</td>
                    <td style="background-color: bisque;">16.0 GB</td>
                </tr>
                <tr>
                    <td style="background-color: tan;">Storage</td>
                    <td style="background-color: bisque;">350 GB</td>
                </tr>
                <tr>
                    <td style="background-color: tan;">Operating System</td>
                    <td style="background-color: bisque;">Windows 11</td>
                </tr>
                <tr>
                    <td style="background-color: tan;">System Type</td>
                    <td style="background-color: bisque;">64-bit operating system</td>
                </tr>
                <tr>
                    <td style="background-color: tan;">Device ID</td>
                    <td style="background-color: bisque;">15EEA3B2-7EF5-4DEC-903D-577382C3C005</td>
                </tr>
                <tr>
                    <td style="background-color: tan;">Product ID</td>
                    <td style="background-color: bisque;">00342-42708-86774-AAOEM</td>
                </tr>
            </table>
        </center>
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
    print("my websserver is running...")
    httpd.serve_forever()
    
# OUTPUT:

![WEB1](https://github.com/user-attachments/assets/d5d38ba8-f752-4937-b0fa-cee55108b76a)

![WEB1 OP](https://github.com/user-attachments/assets/107f016e-98e2-427b-9705-bd60c8c94fb9)

# RESULT:
The program for implementing simple webserver is executed successfully.
