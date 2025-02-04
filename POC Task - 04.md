## Comprehensive Git Repository Backup and Automation Guide
### Introduction  
Backing up your Git repositories is a crucial part of version control management. It ensures that your work remains safe and accessible even in the event of unforeseen data loss, such as accidental deletions, hardware failures, or repository corruption. Automating this process saves time, reduces manual intervention, and guarantees regular updates.  

### Overview  
This task involves creating an automated backup system for your Git repository on a Windows machine using a batch script and Task Scheduler. The script pulls the latest changes from the repository daily and stores them in a backup directory. Additionally, it compresses the repository into a timestamped archive for easy organization. The process ensures that your codebase and its version history are safely stored in a local directory.  

### Key Components  
1. **Batch Script**: A `.bat` file is used to execute commands such as cloning the repository, pulling updates, and compressing the backup.  
2. **Task Scheduler**: A built-in Windows tool is used to automate the script, ensuring it runs daily without manual intervention.  

### Objectives  
1. **Automate Backups**: Develop a script to back up the entire Git repository daily.  
2. **Minimize Data Loss**: Safeguard the repository from accidental deletions or hardware failures.  
3. **Ease of Management**: Create timestamped backups for quick identification and restoration.  
4. **Hands-Free Automation**: Leverage Task Scheduler to eliminate the need for manual execution.  

### Importance  
1. **Disaster Recovery**: In case of repository failures or accidental deletions, you can quickly restore your work from the local backup.  
2. **Version History Preservation**: All changes and version history are secured, ensuring no progress is lost.  
3. **Efficient Workflow**: Automating the process allows you to focus on development tasks instead of managing backups manually.  
4. **Organization**: Timestamped backups provide a clear, structured way to keep track of changes over time.  

### Step-by-Step Overview  
#### Step 1: Create Backup Folder  
Create a folder named `GitHub Backup Folder` to store your backup files.  

![Screenshot 2025-02-02 135527](https://github.com/user-attachments/assets/b8fc8e24-2fc9-45e2-bfa3-8e7115a7ca72)
#### Step 2: Create a Batch Script  
1. Open Notepad and type the following script.  
2. Replace `REPO_URL` with your Git repository URL.  
3. Replace `BACK_DIR` with the file path of the backup folder.  
4. Save it as `backup.bat` on your desktop.  

```batch
@echo off
set REPO_URL=https://github.com/your-repository.git
set BACK_DIR=C:\Path\To\GitHub Backup Folder
set DATE=%date:~10,4%%date:~4,2%%date:~7,2%

cd /d %BACK_DIR%
git clone %REPO_URL% repo_backup_temp
cd repo_backup_temp
git pull origin main
cd ..
ren repo_backup_temp repo_backup_%DATE%
zip -r repo_backup_%DATE%.zip repo_backup_%DATE%
rmdir /s /q repo_backup_%DATE%
echo Backup completed on %DATE%
exit
```  

![Screenshot 2025-02-01 223851](https://github.com/user-attachments/assets/cdeac238-cdea-4127-b8c5-c895e3cb4edf)
#### Step 3: Open Task Scheduler  
1. Press `Win + R` on your keyboard.  
2. Type `taskschd.msc` and press `Enter`.  

![Screenshot 2025-02-01 223923](https://github.com/user-attachments/assets/f7594f4a-6fed-462d-ae7d-7461f8c630a6)
#### Step 4: Create a Basic Task  
1. Click on **Create Basic Task** in the right panel.  
2. Enter a name like **GitRepoBackup** and a description.  
3. Click **Next**.  

![Screenshot 2025-02-01 224114](https://github.com/user-attachments/assets/0f468c80-254e-4121-a19e-86e652f907b3)
#### Step 5: Schedule the Task  
4. Choose **Daily** and click **Next**.  
5. Set the start date and time.  
6. Click **Next**.  

![Screenshot 2025-02-01 224128](https://github.com/user-attachments/assets/697c2f1f-f4f8-4712-b324-95fa22e79955)
#### Step 6: Set the Action  
7. Choose **Start a Program** and click **Next**.  
8. Browse and select your `backup.bat` file.  
9. Click **Next** and then **Finish**.  

![Screenshot 2025-02-01 224246](https://github.com/user-attachments/assets/a295419e-fe88-4dde-a829-fe2334003c2e)
#### Step 7: Run the Task  
10. In **Task Scheduler Library**, find your task.  
11. Right-click and select **Run**.  

![image](https://github.com/user-attachments/assets/72f3b9f3-0a5b-4bd5-8954-8d0cc6874abe)
#### Step 8: Verify Backup  
Check your `GitHub Backup Folder` to ensure the files are stored correctly.  

![Screenshot 2025-02-01 225258](https://github.com/user-attachments/assets/d5378c9e-a378-4c10-bc92-28efc2743237)
![Screenshot 2025-02-01 224636](https://github.com/user-attachments/assets/b53ccdb5-67e4-4940-bf19-1991ca5fda47)
### Outcomes  
By completing this Proof of Concept (PoC) of automating Git repository backups, you will:  
- **Successfully implement a backup system for Git repositories**: Automate the process of creating daily backups for your Git repositories, ensuring that all updates and changes are securely stored in a local folder.  
- **Master the use of batch scripting for task automation**: Learn to create and execute a `.bat` script that clones, pulls updates, and compresses a Git repository into timestamped backup archives.  
- **Understand Task Scheduler's automation capabilities**: Gain practical experience with Task Scheduler, learning how to set triggers, define actions, and configure conditions to automate repetitive tasks seamlessly on a Windows system.  
