## Host a Static Website Locally: Set Up a Local Server Apache and Host a Simple HTML page with your name  

### Introduction and Overview  
In this POC, we will learn how to host a static website locally using the Apache HTTP Server. This process involves setting up a local web server, configuring it correctly, and hosting a simple HTML page. By following these steps, you’ll get hands-on experience with configuring and running a local Apache server, which is a foundational skill for web hosting and server management.  

### Objective  
The goal of this project is to:  
1. Set up a local web server using Apache.  
2. Configure the server to host static files.  
3. Create and host a simple HTML page displaying your name.  

### Importance of Local Hosting  
Local hosting is an essential skill for developers, as it allows them to test and experiment with web applications in a controlled environment. It offers several advantages, such as:  
- **Hands-On Learning:** Gain practical experience with server setup and configuration.  
- **Testing Ground:** Safely test and debug websites before deploying them to a live server.  
- **Offline Development:** Work on web projects without requiring an active internet connection.  

---  

### Step-by-Step Overview  
#### Step 1:  
Search for "Apache Lounge" on Google and click the first link to access the official website.  
![t1p1](https://github.com/user-attachments/assets/d9a6104e-af4b-456f-bc4b-2811a8d50399)

#### Step 2:  
Click on the "Downloads" option located on the left-hand side of the Apache Lounge website.  
![t1p2](https://github.com/user-attachments/assets/7e082ea4-5ac7-4d1d-9bc2-1bbc917ad1a1)

#### Step 3:  
Open Command Prompt as Administrator (Windows + R, type cmd, right-click and select 'Run as Administrator') and use the command:  
```sh  
cd C:\path\to\apache\bin  
```  
to set the path to the Apache bin folder.  

#### Step 4:  
Run the installation command:  
```sh  
httpd.exe -k install  
```  

#### Step 5:  
Navigate to the Apache folder you downloaded, go to the `conf` folder, and right-click on the `httpd.conf` file; select 'Edit with Notepad'  
(Path: `Apache/conf/httpd.conf`)  
![t1p5](https://github.com/user-attachments/assets/1ba09a19-89e8-4ed1-a045-44e182f83543)

#### Step 6:  
Inside the `httpd.conf` file, replace the content with the provided configuration. Ensure you update the `SRVROOT` directive with your Apache installation path. This configuration defines the server’s root directory, listening port, modules, document root for serving web files, logging paths, and basic permissions, ensuring Apache serves content correctly from the specified `htdocs` directory.  
![t1p6](https://github.com/user-attachments/assets/e334151f-be3f-4e97-be01-2119af295a4b)

#### Step 7:  
Open Command Prompt and type the command:  
```sh  
httpd.exe -t  
```  
to test the configuration file. If the configuration is correct, you should see 'Syntax OK'.  

#### Step 8:   
Run the command:  
```sh  
httpd.exe -k start  
```  
to start the Apache server.  

#### Step 9:  
Go to the Apache folder, navigate to the `htdocs` folder, and find the `index.html` file. Right-click on it and select 'Edit with Notepad'.  

#### Step 10:  
Create a simple HTML model to display your name (you may optionally add CSS for styling).  
![t1p9](https://github.com/user-attachments/assets/48b26b1a-76cb-4642-834b-0a1c714ed67c)

#### Step 11:  
Open the browser and type `localhost/index.html` in the address bar. You should be able to see the website hosted successfully.  
![t1p10](https://github.com/user-attachments/assets/bb798b55-eb7d-4a06-94c0-fc7fdcac9cc4)

---  

### Expected Outcome  
By completing this POC, you will:  
1. Successfully configure and run an Apache server locally.  
2. Host a static HTML website that displays your name.  
3. Understand the basics of web server configuration and file hosting.  
