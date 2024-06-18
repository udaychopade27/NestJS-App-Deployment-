
# Cloning and Deploying NestJS "Hello World" App on AWS EC2

---

## Overview:

Welcome to this beginner's guide! In this tutorial, we'll walk through the process of cloning a NestJS "Hello World" application from GitHub and deploying it on an AWS EC2 instance. NestJS is a framework built on Node.js, designed to create powerful and scalable server-side applications.

## Prerequisites:

Before we begin, make sure you have the following:

- An AWS account with access to the EC2 service.
- Basic familiarity with using the terminal or command prompt.
- Some knowledge of Git and GitHub (don’t worry, we'll guide you through!).
- An SSH client installed on your computer (for connecting to the EC2 instance).

## Step 1: Cloning the GitHub Repository

1. **Clone the Repository**: Open your terminal (or command prompt) on your computer.
   
   ```bash
   git clone https://github.com/nestjs/typescript-starter.git
   ```


## Step 2: Setting Up the AWS EC2 Instance

1. **Launch an EC2 Instance**: Log in to your AWS Management Console.
   
   - Go to the EC2 Dashboard and click on "Launch Instance".
   - Choose "Ubuntu Server" as your instance type and follow the setup wizard.
   - Configure the instance details, storage, tags, and most importantly, the security group. Make sure to allow inbound traffic on port 22 (SSH).
   - also allow inbound traffic on port 3000 in which the application is running.

## Step 3: Connecting to the EC2 Instance

1. **Connect via SSH**: Once your EC2 instance is up and running, note down its public DNS or IP address.
   
   - Open your terminal (or command prompt) again.
   - Use SSH to connect to your EC2 instance. You'll need the private key (.pem file) you downloaded during instance setup.
   
     ```bash
     ssh -i /path/to/your-key.pem ubuntu@your-ec2-public-dns
     ```

     Replace `/path/to/your-key.pem` with the path to your private key file and `your-ec2-public-dns` with your instance's public DNS.

## Step 4: Installing Node.js and npm on EC2 Instance

1. **Setup Node.js and npm**: Now that you’re connected to your EC2 instance via SSH:
   
   ```bash
   sudo apt update
   sudo apt install nodejs npm -y
   ```

   These commands update the package lists and install Node.js and npm on your EC2 instance. You can verify the installations by checking the versions:
   
   ```bash
   node -v
   npm -v
   ```

## Step 5: Deploying the NestJS App on EC2 Instance

1. **Navigate to Your App**: Move into the directory where you cloned your NestJS repository:
   
   ```bash
   cd your-repo-name
   ```

2. **Install Dependencies**: Use npm to install the project dependencies:
   
   ```bash
   npm install
   ```

3. **Build and Start the App**: If your app requires building (check the `package.json` file), run the build command and start your NestJS application:
   
   ```bash
   npm run start
   ```

## Step 6: Accessing the Deployed NestJS App

1. **Open Your Web Browser**: To see your NestJS app in action, open a web browser.

2. **Enter the URL**: Type in the public IP address or public DNS of your EC2 instance, followed by the port number if specified (typically port 3000 for NestJS):
   
   ```
   http://your-ec2-public-dns:3000
   ```

   Replace `your-ec2-public-dns` with your EC2 instance's public DNS. You should now see the "Hello World" message from your NestJS app!

---

## For more details, visit the [NestJS video Explanation ](https://www.loom.com/share/fc61b1d414ef42c2b27628a8d7aa6f48?sid=c2c82d44-339c-4893-955e-6af3106e4e5c).


## Conclusion:

Great job! we have  successfully cloned a NestJS "Hello World" app from GitHub and deployed it on an AWS EC2 instance. 


