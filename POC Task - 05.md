## Create a new branch in your Git repository for testing. Add a new feature and merge it
### Introduction:
In this Proof of Concept (POC), Git is used for version control to manage the development workflow. Git allows developers to create separate branches for new features, isolate them from the main branch, and merge them back after completion. This ensures organized and collaborative development.

### Overview:
This POC demonstrates how to:
1. Initialize a Git repository.
2. Create and switch between branches.
3. Commit changes in different branches.
4. Merge feature branches into the main branch.
5. Delete branches after completing the work.

### Objectives:
* To initialize and set up a Git repository.
* To create and manage feature branches (e.g., testing-feature).
* To demonstrate adding, committing, and merging code.
* To showcase how to delete branches after their purpose is served.
* To learn how to resolve merge conflicts if any arise during the process.

### Importance:
- **Version Control:** Helps track changes, revert to previous versions, and avoid conflicts in the codebase.
- **Collaboration:** Different team members can work on separate features simultaneously without interfering with each other's work.
- **Branching:** Isolates new features or bug fixes, ensuring stability in the main branch (master or main).
- **Efficiency:** Merging branches allows rapid integration of new features without disrupting ongoing work.
- **Clean Workflow:** Deleting feature branches after merging keeps the repository clean and manageable.

### Step-by-Step Overview:
#### Step 1:
Create a folder and name it `sample`.

![Screenshot 2025-02-02 141942](https://github.com/user-attachments/assets/fc91fd56-fcb2-4e25-bbfa-b68781553838)
#### Step 2:
Set the path to the folder created in the first step (`sample`).

![Screenshot 2025-02-02 142050](https://github.com/user-attachments/assets/7552ef1b-5601-4cf3-9f1f-2d1b327948a6)
#### Step 3:
Initialize Git by typing this command:
```sh
git init
```
This command will create a `.git` folder inside your folder, which tells Git to start tracking your files.

![Screenshot 2025-02-02 142129](https://github.com/user-attachments/assets/2c6d9afe-8852-4c50-a8c7-9be6a07b75ed)
#### Step 4:
Create a simple file to start the repository:
```sh
touch sample.txt
```

#### Step 5:
Add the file to Git:
```sh
git add sample.txt
```

#### Step 6:
Save this change in Git with a commit message:
```sh
git commit -m "initial commit"
```

![Screenshot 2025-02-02 142345](https://github.com/user-attachments/assets/e7de2c51-54df-4b07-9786-b1fa1a7e923d)
#### Step 7:
Create and switch to a new branch called `test`:
```sh
git checkout -b test
```

#### Step 8:
Add a new file for our feature:
```sh
touch test.txt
```

#### Step 9:
Stage the changes:
```sh
git add test.txt
```

#### Step 10:
Commit the changes:
```sh
git commit -m "test"
```

#### Step 11:
Switch to the master branch:
```sh
git checkout master
```

![Screenshot 2025-02-02 142656](https://github.com/user-attachments/assets/74245748-d874-43a7-8d27-b7167203ac22)
#### Step 12:
Merge changes from `test` to `master`:
```sh
git merge test
```

#### Step 13:
Once the merge is done, delete the `test` branch:
```sh
git branch -d test
```

![Screenshot 2025-02-02 142811](https://github.com/user-attachments/assets/faeb0b0a-e3e1-4459-88eb-906d90caa82b)
#### Step 14:
Now, check the files in the folder:
```sh
ls
```

![Screenshot 2025-02-02 142845](https://github.com/user-attachments/assets/1d1d53cf-3e39-477e-885c-087c91c674df)
### Outcome:
By completing this PoC of managing branches in Git for a local repository, you will:
- Successfully initialize a Git repository in your local project folder.
- Create and manage multiple branches for feature development and experimentation.
- Track and commit changes made to files in different branches.
- Merge feature branches back into the main branch while maintaining project integrity.
- Gain hands-on experience with key Git commands such as `git init`, `git add`, `git commit`, `git checkout`, and `git merge`.
