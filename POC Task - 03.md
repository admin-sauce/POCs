## Set Up a Local Git Repository: Initialize a Git repository locally and version control your static website
### Introduction
Version control is a fundamental practice in software development that allows you to manage changes to your code over time. It provides a systematic way to track updates, collaborate with others, and revert to previous versions if needed. Git is one of the most widely used version control systems, known for its efficiency, flexibility, and distributed nature.

In this POC, we’ll initialize a local Git repository to version control your static website. By doing so, you’ll be able to track changes to your project files, experiment with new features in a controlled way, and easily share your project with others if needed. Setting up a Git repository is a critical step towards maintaining a structured and reliable workflow, especially for developers and teams working on collaborative projects.

### Overview
Here’s what we will cover in this setup:

1. Installing Git: Ensure Git is installed on your system and properly configured.
2. Creating a Local Repository: Initialize a Git repository in the root folder of your static website.
3. Staging and Committing Files: Add your project files to the staging area and commit them to the repository to save a snapshot of your work.
4. Reviewing the Repository State: Use Git commands to check the status of your repository and verify that everything is tracked properly.

### Objectives
By the end of this POC, you will:

1. Understand the Basics of Version Control: Gain insight into the importance of Git for managing and tracking changes in your projects.
2. Set Up a Git Repository: Learn how to initialize a Git repository to version control your static website locally.
3. Track Changes Effectively: Understand how to stage and commit files to ensure every change is logged.
4. Organize Your Project: Maintain a clean and structured workflow for your static website, with the ability to roll back changes when needed.
5. Prepare for Collaboration: Lay the groundwork to share your repository and collaborate with others using Git when required.

### Importance of Setting Up a Local Git Repository

- **Track Changes:** Git records all modifications, ensuring a clear history of your project.
- **Rollback:** Easily revert to previous versions to recover from mistakes.
- **Collaboration:** Prepares your project for teamwork, enabling smooth integration of changes.

### Step-by-Step Overview

#### Step 1
Search for "Git" in Chrome, download it, and click the "Downloads" option on the website.

![t3p1](https://github.com/user-attachments/assets/ac7497c2-c0af-4d19-8483-d857451d97c8)
#### Step 2
Click the Windows option on the download page and follow the installation wizard.

![t3p2](https://github.com/user-attachments/assets/7a0258ad-ada9-4ed3-9001-6c8ba5041b99)
#### Step 3
Create a folder named `website` on your desktop for your static website.
Inside that folder, create a simple HTML file named `index.html`. You can write some basic HTML.

![t3p3](https://github.com/user-attachments/assets/c67a12a9-c80e-4a71-8eb8-cf7a40356521)
#### Step 4
Open the Command Prompt and navigate to the `website` folder.


#### Step 5
Initialize Git by typing this command:
```sh
git init
```
This command will create a `.git` folder inside your project folder, which tells Git to start tracking your files.

#### Step 6
Next, we need to tell Git to start tracking your website files. Use the following command to add all files:
```sh
git add .
```
This command adds all the files to Git’s tracking system.

#### Step 7
Set Up Your Name and Email Globally. Git uses this information to track who made the changes.

![t3p6](https://github.com/user-attachments/assets/24ad0b63-54b0-4e9a-a563-40ff381be821)
#### Step 8
Now, we need to save these changes in Git. Use the following command to commit your changes:
```sh
git commit -m "Initial commit of my static website"
```
The `-m` flag allows you to add a message about your changes.

#### Step 9
Create a New Repository on GitHub:
6. Log in to GitHub.
7. Click the green "New" button on the top-right of your GitHub homepage.
8. Name your repository, for example, `poc-website`.
9. Leave the other settings as default, and click "Create repository".

#### Step 10
Add the Remote Repository URL to Your Local Repository:
```sh
git remote add origin https://github.com/yourusername/my-website.git
```
Replace `yourusername` with your GitHub username and `my-website` with the name of your GitHub repository.

#### Step 11
Rename the current branch to `main`:
```sh
git branch -M main
```

#### Step 12
Push your local repository to GitHub and set the upstream branch:

![t3p10](https://github.com/user-attachments/assets/66d94828-d32a-44a5-9e71-163970255a9c)
#### Step 13
Verify Your Files on GitHub:
10. Open your web browser and navigate to your GitHub repository (e.g., `https://github.com/yourusername/my-website`).
11. You should see your website files there!

![t3p11](https://github.com/user-attachments/assets/277c47c9-367a-4b17-8aca-2c874fd7933d)
### Expected Outcome
By completing this PoC of setting up a local Git repository, you will:

12. Successfully initialize a Git repository in your local static website folder.
13. Track changes made to your website files (HTML, CSS, etc.) using Git version control.
14. Understand the basic Git commands (`git init`, `git add`, `git commit`) for version control.
15. Commit your changes locally with a descriptive commit message.
16. Gain hands-on experience with Git and how it helps manage and track website file changes.
