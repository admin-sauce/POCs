## Deploy your static website using GitHub Pages: Host your local Git repository’s static website directly using GitHub Pages

### Introduction
GitHub Pages is a static site hosting service designed to publish your projects directly from a GitHub repository. It allows developers to showcase their work, create personal websites, or host documentation in an efficient, free, and straightforward way.

### Overview
This project demonstrates how to deploy a static website using GitHub Pages. Starting with the basics of setting up a GitHub repository, we’ll explore each step required to host a functional static website. This includes initializing a Git repository, pushing files to GitHub, and configuring GitHub Pages for deployment.

#### Key Features of GitHub Pages:
- Free hosting for public repositories.
- Support for static files (HTML, CSS, JavaScript).
- Easy integration with version control through Git.

### Objectives
1. Learn the fundamentals of GitHub Pages and its deployment process.
2. Understand the importance of static website hosting and its use cases.
3. Gain hands-on experience in using Git and GitHub for project versioning and hosting.
4. Successfully publish a static website and make it publicly accessible.

### Importance of Hosting with GitHub Pages
1. **Cost-effective:** Free for public repositories, making it accessible for students and developers.
2. **Version Control:** Seamlessly integrates with GitHub, enabling easy updates and collaboration.
3. **Visibility:** A great way to showcase personal portfolios, projects, or documentation.
4. **Ease of Use:** Minimal setup required compared to other hosting platforms.
5. **Custom Domains:** Option to configure custom domains, enhancing the professional appeal of your website.

### Step-by-Step Overview

#### Step 1: Create a New Repository
- Log in to GitHub.
- Click the green **"New"** button on the top-right of your GitHub homepage.
- Give your repository a name, e.g., `my-static-website`.
- Leave other settings as default and click **"Create repository"**.

#### Step 2: Prepare Your Project
- Create a folder (e.g., `my-static-website`) where you’ll keep all your website files.
- Inside that folder, create the main file for your website called `index.html`.
- Example content for `index.html`:
  ```html
  <!DOCTYPE html>
  <html>
  <head><title>My Static Website</title></head>
  <body>
      <h1>Welcome to My Website!</h1>
      <p>This is hosted using GitHub Pages.</p>
  </body>
  </html>
  ```

![Screenshot 2025-02-04 202452](https://github.com/user-attachments/assets/a8950d99-2aa2-48b3-af4c-fc4b6e44be33)
#### Step 3: Initialize a Git Repository
Open Command Prompt and navigate to the folder where your `index.html` file is saved using `cd` command.
Run the following commands:
```sh
git init
git add .
git commit -m "Initial commit"
```

#### Step 4: Link Local Repository to GitHub
- Copy your repository URL from GitHub.
- Run the following command in the Command Prompt:
  ```sh
  git remote add origin <your-repository-url>
  ```
- Push your files to GitHub:
  ```sh
  git push -u origin main
  ```

![Screenshot 2025-02-04 203117](https://github.com/user-attachments/assets/9ef6d06e-9e6d-41dc-bd1c-a428e55c5090)
#### Step 5: Enable GitHub Pages
6. Go to your repository on GitHub.
7. Click on the **Settings** tab.
8. Scroll down to the **Pages** section.
9. Under **Source**, select:
   - **Branch:** `main`
   - **Folder:** `/ (root)`
10. Click **Save**.

![Screenshot 2025-02-04 203237](https://github.com/user-attachments/assets/f529390e-2acb-4ae6-8d6c-ee36e26d7fbe)
#### Step 6: Access Your Website
- Wait a few minutes for GitHub Pages to deploy your site.
- Visit your website at: `https://<your-username>.github.io/<your-repository>`

![Screenshot 2025-02-04 203307](https://github.com/user-attachments/assets/0f43a9e3-dc23-4d30-9b48-de25a8446f87)
### Outcome
By completing this PoC of deploying a static website using GitHub Pages, you will:
1. Successfully create and configure a GitHub repository for your project.
2. Initialize a Git repository in your local project folder and link it to GitHub.
3. Upload your static website files (HTML, CSS, JavaScript) to GitHub.
4. Enable GitHub Pages in the repository settings to host your static website.
5. Access your static website live on the web via a GitHub Pages URL.
6. Gain hands-on experience with Git commands like `git init`, `git add`, `git commit`, `git remote add`, and `git push`.
7. Understand the process of hosting a static site for free using GitHub Pages.
