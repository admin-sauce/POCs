
## Automate Static Website Deployment Locally  

### Introduction and Overview  
This document outlines the step-by-step procedure for automating the deployment of a static website from a Git repository to a local server using a deployment script (`deploy.bat`). This automation ensures that any changes made to the HTML files in the repository are immediately replicated in the deployment directory, facilitating seamless updates and reducing manual intervention.  

### Objectives  
- Automate the deployment of changes made to a static website in a Git repository.  
- Use a PowerShell script (`deploy.bat`) to pull changes from the repository and update the deployment folder.  
- Demonstrate how to set up a post-receive Git hook to trigger the deployment process.  
- Ensure changes to the repository reflect automatically in the deployment directory.  

### Importance  
- **Efficiency:** Automates the process of deploying website updates, reducing time and effort.  
- **Consistency:** Ensures the deployment folder always reflects the latest repository changes.  
- **Reduced Errors:** Minimizes the chances of human error by automating the entire deployment flow.  
- **Version Control:** By using Git, it provides versioning and history of changes made to the website files.  

---

## Steps  

### **Step 1: Adding the HTML Website to the Repository**  
1. Navigate to the folder where your static website files are stored.  
2. Open Git Bash or your terminal.  
3. Initialize the repository (if not already done) by running:  
   ```bash
   git init
   ```  
4. Add your HTML files (or any other website files) to the repository:  
   ```bash
   git add .
   ```  
5. Commit the files to the repository:  
   ```bash
   git commit -m "Initial commit with website files"
   ```  
6. Link the repository to your remote GitHub repository (replace the URL with your actual repository URL):  
   ```bash
   git remote add origin https://github.com/yourusername/yourrepository.git
   ```  
7. Push the changes to the remote repository:  
   ```bash
   git push -u origin main
   ```

![Screenshot 2025-02-04 191850](https://github.com/user-attachments/assets/e8a80d76-175a-4226-b262-b657c798b078)
### **Step 2: Creating the `deploy.bat` File**  
8. In your project folder, create a new text file and rename it to `deploy.bat`.  
9. Open the file in a text editor (e.g., Notepad++).  
10. Paste the following script in the file:  
   ```batch
@echo off
set DEPLOY_DIR="D:\Development\SampleWebsite"
set SOURCE_DIR="D:\Development\automated deployment"
   
REM Pull the latest changes from the repository
echo Pulling the latest changes from the repository...
git pull origin main
   
REM Copy files to the deployment directory, excluding deploy.bat
echo Copying files to the deployment directory...
xcopy %SOURCE_DIR%\*.* %DEPLOY_DIR%\ /E /Y /I /H
   
echo Deployment complete!
pause
```

![Screenshot 2025-02-04 192146](https://github.com/user-attachments/assets/0fdafe89-4fba-4b4a-a670-bd944162f7b3)
11. Save the file.  

### **Step 3: Revealing the `.git` Folder**  
By default, Git hides the `.git` folder. If you need to make it visible for some reason, follow these steps:  
1. Open File Explorer.  
2. Navigate to your project directory.  
3. In the File Explorer menu, click on **View → Show → Hidden items**.  
4. The `.git` folder should now be visible. If it is still hidden, check your folder options and ensure **"Hide protected operating system files"** is unchecked.  

![Screenshot 2025-02-04 192218](https://github.com/user-attachments/assets/7a38971a-8f5f-48ee-9c41-4934380f4a86)
### **Step 4: Creating the `post-receive.sample` File**  
5. Navigate to your `.git\hooks` folder.  
6. Create a new file named `post-receive` (with the `.sample` extension).  
7. Open the file and paste the following script:  
   ```bash
   #!/bin/bash
   # Navigate to the project directory
   cd /path/to/your/project/directory
   
   # Execute the deployment script
   cmd /c deploy.bat
   ```

![Screenshot 2025-02-04 192429](https://github.com/user-attachments/assets/5439625b-d899-4e98-8ded-c72efbc661a2)
8. Replace `/path/to/your/project/directory` with the actual path to your repository directory.  
9. Make the `post-receive` hook executable by running:  
   ```powershell
   cd D:\Development\SampleWebsite\.git\hooks
   Unblock-File -Path .\post-receive.sample
   ```

![Screenshot 2025-02-04 192712](https://github.com/user-attachments/assets/eebd5824-7bfe-42b8-a3ba-bbbc09425442)
### **Step 5: Setting Up the Source and Deployment Directories**  
10. Keep your `deploy.bat` file in the source repository directory.  
11. Create a new directory (e.g., `D:\Development\SampleWebsite`) where the autonomous deployment will occur. This will be the directory where the latest changes will be copied after they are pulled from the repository.  
12. Ensure both the source and deployment directories are correctly defined in the `deploy.bat` file.  

### **Step 6: Testing the Deployment Process**  
1. Make a change to your HTML file (e.g., `index.html`) in the repository.  
2. Stage and commit the change:  
   ```bash
   git add index.html
   git commit -m "Updated index.html"
   ```  
3. Push the changes to the remote repository:  
   ```bash
   git push origin main
   ```  
4. Open PowerShell as an administrator.  
5. Navigate to the directory where the `deploy.bat` file is located:  
   ```powershell
   cd D:\Development\automated deployment
   ```  
6. Run the `deploy.bat` script:  
   ```powershell
   .\deploy.bat
   ```  
7. Check if the files were copied successfully to the deployment directory (`D:\Development\SampleWebsite`).  
8. Verify that the changes made in the HTML file are reflected in the deployment directory.  

---

This concludes the automated deployment setup for a static website. 🚀
