# Capstone Project: Introduction to Cloud Computing 
## Capstone Project: E-Commerce Platform Deployment with Git, Linux, and AWS

### Project Instructions:

I have been assigned to develop an e-commerce website named **MarketPeak** for a new online marketplace. This platform will include essential features such as product listings, a shopping cart, and user authentication. To streamline development, I will be obtaining and preparing a pre-designed website template that meets the project requirements, rather than building the site from scratch.

The main objectives are to manage version control with Git, set up and configure the platform in a Linux environment, and deploy it on an AWS EC2 instance for scalability. This project will showcase my skills in using Git, Linux, and AWS to create a functional e-commerce platform.

---

## Step 1: Development on Local Workstation

### Task 1: Implement Version Control with Git

**1.1 Initialize Git Repository**

To begin, create the project directory named **MarketPeak_Ecommerce**, navigate into it, and initialize it as a Git repository.

> **Note:** For this project, I am using **Git Bash** on a Windows workstation to execute these shell commands, as it provides a Unix-like command-line experience.

### **Commands**
```
mkdir MarketPeak_Ecommerce
cd MarketPeak_Ecommerce
git init
```

![](img/1.mkdir.png)


## Task 1.2 Obtain and Prepare the E-commerce Website Template

Instead of building the website from scratch, I'll use a pre-existing e-commerce template. This approach allows me to focus on deployment and operational aspects rather than on web development, which is typically handled by web/software developers.

 **Download a Website Template**
Visit **[Tooplate](https://www.tooplate.com/)** or another free template resource to find a suitable e-commerce template. Choose one that is ready-for-use and requires minimal customization.

 **Recommended Template**
It is suggested to use the specific template provided or one that meets the project's requirements.

![](img/1.2websitedownload.png)

 **Prepare the Template:** Extract the downloaded template into the project directory,
 MarketPeak_Ecommerce.

 ![](img/1.2bunzip.png)

 ## Task 1.3 Stage and commit the Template to Git

 In this step, I will add the website files to the Git repository, configure my global Git settings, and make an initial commit with a descriptive message.

  **Add Files:** Add all website files to the staging area.

  **Configure Git User Information:** Set up global configuration with my actual git username and email address.

  **Commit Changes** Commit the changes with a clear and descriptive message.

**Commands**

```

git add .
git config --global username "YourUsername"
git config --global user.email "youremail@example.com"
git commit -m "Initial commit with basic e-commerce site structure" 
```
![](img/1.3gitadd.png)

## Task 1.4 Push the code to your respository

After initializing your Git repository and adding your e-commerce website template, the next step is to push your code to a remote repository on GitHub. This step is crucial for version control and collaboration.

**.** Create a Remote Repository on GitHub: Log into your GitHub account and create a new repository named MarketPeak_Ecommerce. Leave the repository empty without initializing it with a README, .gitignore, or license. 

![](img/1.4createrepo.png)
![](img/1.4bcreaterepo.png)

**.** Link Your Local Repository to GitHub: In your terminal, within your project directory, add the remote respository URL to your local repository configuration.

**.** Push Your Code: upload your local repository content to Github. Once you have linked your local repository to Github, use the following command to push your commits from our local main branch to the remote repository. This enables you to store your project in the cloud and share it with others.

**Commands**

```
git remote add origin https://github.com/Joy-it-code/MarketPeak_Ecommerce.git
git branch -M main
git push -u origin main
```





