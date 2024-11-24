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

![](img/1.4dpushfile.png)

## Step 2: AWS Deployment

To deploy the MarketPeak_Ecommerce platform, you will start by setting up an Amazon EC2 instance.

## Task 2.1 setup an AWS EC2 instance for deployment

**.** Log in to the AWS Management Console.

![](img/2.1awslogin.png)

**.** Launch an EC2 instance using an amazon Linux AMI.

![](img/2.1instance.png)

**.** Showing an EC2 instance running

![](img/2.1ainstace.png)

**.** Make sure you are logged into your EC2 instance using SSH. You should see a command prompt indicating you are on your instance, typically something like:

![](img/2.1cawslinked.png)

## Task 2.2: Clone the reposirory on the Linux server 

Before deploying your e-commerce platform, you need to clone the GitHub repositoryto your AWS EC2 instance. This process involves authenticating with GitHub and choosing between two primary methods of cloning a repository: SSH and HTTPS.

  **.** Navigate to your repository in github console

  **.** Select the **'code'** as highlighted in the image below

![](img/2.2code.png)

## SSH Method:

  **.** On your EC2 instance, generate SSH keypair using ssh-keygen as shown

  **Command**

  ```ssh-keygen```

  ![](img/2.2bsshkeygen.png)

  **.** Cat and copy the public key.

Command:

```cat /home/ec2-user/.ssh/id_rsa.pub```

![](img/2.2cat.png)

  **.** Adding ssh public key to Github repository by clicking on your image icon, click on settings, then click on ssh and Gkeys.

![](img/2.2dimageicon.png)
![](img/2.2newssh.png)
![](img/2.2sshkeyb.png)
![](img/2.2sshkeyc.png)

After adding the SSH key to your GitHub account, you should be able to use it for secure access to your GitHub repositories from your EC2 instance or any system where the private key is stored.

  **.** Use the SSH clone the repository

  **Command**

  ```git clone git@github.com:Joy-it-code/MarketPeak_Ecommerce.git```

![](img/2.2sshclone.png)

![](img/2.2gitclone.png)

## **HTTPS Method:**

For repositories that you plan to clone without setting up SSH keys, use the HTTPS URL. GitHub will prompt for your username and password:

**Note** that github.com no longer accept password, but you will have to generate tokens

**Command:**

git clone https://github.com/Joy-it-code/MarketPeak_Ecommerce.git

## Task 2.3 install a Web Server on EC2

Apache HTTP Server (httpd) is a widely used web server that serves HTML files and content over the internet. Installing it on Linux EC2 server allows you to host to host MarketPeak E-commerce site

**.** Install Apache web server on the EC2 instance: Note that httpd is the software name for Apache on redhats systems using yum package manager

**Commands:**

```
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```
![](img/2.3installed.png)
![](img/2.3asymlinkreplaced.png)

**Configure httpd for website:**

  **.** Prepare the Web Directory: Clear the default httpd web directory and copy MarketPeak Ecommerce website files to it.

  Reload httpd: Apply the changes by reloading the httpd service.

**Commands** 

```
sudo rm -rf /var/www/html/*
sudo cp -r ~/MarketPeak_Ecommerce/* /var/www/html/
sudo systemctl reload httpd
```
![](img/2.4rm-rf.png)
![](img/2.4systemc.png)


**Task 2.4 Access Website from browser**

Access website from browser with httpd configured and website files in place, MarketPeak Ecommerce platform is now live on the internet: Open a web browser and access the public IP (http://13.61.13.134/2129_crispy_kitchen/) of your EC2 instance to view the deployed website.

![](img/2.4webaccess.png)

## Step 3: Continous Integration and Deployment Workflow

To ensure a smooth workflow for developing, testing and deploying my e-commerce platform, follow this structured approach. it covers making changes in a development environment, utilizing version control with Git, and deploying updates to your production to server on AWS.

## **Task 3.1: Developing New Features and Fixes**

**.** Create a development Branch: Begin your development work by creating a separate branch. This isolates new features and bug fixes from the stable version of your website.

**Commands**

```
git branch development
git checkout development
```
  **.** Implement Changes: On the development branch, add your new features or bug fixes. This might include updating web pages. In my case, I just changes the slide image.

## Task 3.2: Version control with Git

  **.** Stage your changes: Once you have made the changes, stage the files you modified. You an add them individually, or if you have only changed the slide image, you can stage everything with.

  **.** Commit your changes: After staging,commit your changes with a clear message describing the update.

  **.** Push changes to remote development branch: push your changes to the remote development branch to keep everything update.

**Commands**

```
git add .
git commit -m "Add new features or fix bugs"
git push origin development
```

![](img/3.2gitadd.png)

## **Task 3.3: Pull Requests and merge to the main branch**

  **.** Create a Pull Request (PR): On GitHub, create a pull request to merge the development branch into the main branch. This process is crucial for code review and maintaining code quality.

