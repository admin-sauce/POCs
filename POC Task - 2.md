## Automate File Copying with a Script  

### Introduction  
Automating repetitive tasks like file copying can save time, reduce errors, and improve efficiency in various scenarios, such as managing backups, organizing files, or syncing data between directories. This POC script will demonstrate how to copy files automatically from one folder to another, using a simple yet effective approach.  
### Overview  
The script automates the process of copying files from a source folder to a destination folder. It ensures that all files in the source directory are transferred efficiently while maintaining their integrity. This automation can be customized based on specific needs, such as copying files based on file type, modification date, or size. The script can be written using programming languages like Python, Shell scripting, or PowerShell, depending on the operating environment.  
### Objectives  
The key objectives of this automation task are:  
- **Simplify File Management:** Reduce manual effort in moving or copying files between folders.  
- **Improve Efficiency:** Automate the process to save time and improve productivity.  
- **Ensure Data Integrity:** Accurately copy files without any corruption or loss.  
- **Customizable Workflow:** Enable flexibility to meet specific requirements (e.g., filtering files by type or date).  
- **Scalable Solution:** Allow the script to handle a large number of files efficiently.  
### Importance  
1. **Time-Saving:** Automating the process eliminates the need for manual intervention, saving hours of work.  
2. **Error Reduction:** Reduces human errors, such as forgetting to copy specific files or overwriting important ones.  
3. **Improved Organization:** Helps maintain a consistent structure for file storage and backups.  
4. **Useful in Various Scenarios:** Valuable for IT professionals, businesses, and individuals dealing with frequent file transfers or backups.  
5. **Scalability and Reusability:** Once created, the script can be reused and scaled up to handle more complex tasks.  
### Step-by-Step Overview  

#### Step 1  
Create two folders named `source` and `destination`. 

![t2p1](https://github.com/user-attachments/assets/f674a44a-e9d7-4bba-9960-73e2b7ddbf7c)

#### Step 2  
Store some files inside the `source` folder to automate the copying process.  

![t2p12](https://github.com/user-attachments/assets/ff7a0b56-6037-4bd2-a5d3-b2f4d1c14ec0)

#### Step 3  
Open Notepad and type the following code. Ensure that in `set SOURCE`, you provide your `source` folder address, and in `set DESTINATION`, you provide your `Destination` folder address.  

![t2p2](https://github.com/user-attachments/assets/b7dd7576-608c-4256-85b7-27901e350aee)

#### Step 4  
Save the file on your desktop with a `.bat` extension (e.g., `backup-files.bat`).  

![t2p3](https://github.com/user-attachments/assets/905e8555-6773-426f-8ff8-8ce422479459)

#### Step 5  
Press `Win + R` on your keyboard.  
- A small "Run" dialog box will pop up.  
- Type `taskschd.msc` (without quotes) in the Run box.  
- Press `Enter` or click `OK`. This will open the Task Scheduler window.

![t2p5](https://github.com/user-attachments/assets/ae9e1241-184b-4d5c-9437-a402ee65c22e)

#### Step 6  
In the Task Scheduler window, look to the right-hand side for a button called **"Create Basic Task"**.  
- Click it.  
- A wizard will open to guide you through the setup.

![t2p6](https://github.com/user-attachments/assets/8cf43064-dec8-402b-869a-15fcfca18e99)

#### Step 7  
6. **Enter a Name for the Task:**  
   - Example: `Automate File Copying` (This can be anything that helps you remember what the task does.)  
   - Optionally, add a description like "Copies files from folder A to folder B".  
7. Click `Next` to continue.
   
![t2p7](https://github.com/user-attachments/assets/82514453-1058-4675-8df5-f5d0c8ac9dd3)

#### Step 8  
Choose a Schedule:  
- **Daily** (runs every day).  
- **Weekly** (runs once a week).  
- **One time** (runs only once at a specific time).  
Choose what works for you (e.g., `Daily`) and click `Next`.
![t2p8](https://github.com/user-attachments/assets/205deda5-0ba2-4f74-85cc-81f42dd95497)

#### Step 9  
Set the Time and Frequency:  
- If you chose `Daily`, specify:  
  - The **start date** (it defaults to today).  
  - The **time** (e.g., `10:00 AM`).  
- Click `Next` to move on.

![t2p9](https://github.com/user-attachments/assets/b11902ed-b286-43a9-9eb4-061dea790d8a)

#### Step 10  
Set the Action:  
- Select **"Start a Program"**.  
- Click `Next`.

![t2p10](https://github.com/user-attachments/assets/9f1da189-4caf-4db1-aa8b-e87df22108f7)

#### Step 11  
Point to the Program or Script:  
- In the **Program/script** field, click `Browse` and navigate to the location of your `.bat` file.  
- Example: If your script is named `backup-files.bat` and saved on the desktop, navigate to that file and select it.  
- Click `Next`.

![t2p11](https://github.com/user-attachments/assets/ea814998-5491-4253-9d6d-6a037b32e3f2)

#### Step 12  
Review and Finish:  
- Click `Finish` to save and schedule the task.  
#### Step 13  
- In Task Scheduler, go to the **Task Scheduler Library** (on the left-hand side).  
- Find your task (it should have the name you gave it, e.g., "Automate File Copying").  
- Right-click the task and select `Run`.  
- This will manually trigger the task immediately.  
#### Step 14  
- If your task was set up to copy files, go to the destination folder and confirm that the files have been copied.

![t2p13](https://github.com/user-attachments/assets/55a6dcca-7dac-4a7a-bc32-95396df5bd85)

### Outcome  
By completing this Proof of Concept (PoC) of automating a task using Task Scheduler, you will:  
8. Successfully set up an automated task that triggers on a schedule or when manually run.  
9. Execute a batch script to copy files from a source folder to a destination folder automatically.  
10. Understand how to use Task Scheduler to automate repetitive tasks in Windows.  
11. Gain familiarity with task triggers, actions, and conditions in Task Scheduler.  
12. Save time and ensure consistent execution of file operations without manual intervention.  
13. Optionally test the task to verify that it runs as expected and achieves the desired outcome.  
14. Enhance your workflow automation skills with practical hands-on experience.  
