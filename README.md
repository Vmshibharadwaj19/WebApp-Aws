
# Set Up a Web App Using AWS and VS Code  
**Author:** Vamshi Prasad Goteti  
**Date:** 27/06/2025  
**Email:** vamshibharadwaj19@gmail.com  

---

## ✨ Introducing Today's Project  
Today I set up a simple web application in the cloud using **Amazon EC2** and **Visual Studio Code (VS Code)**. This was part of a hands-on DevOps learning journey with a goal of eventually building a full CI/CD pipeline.

---

## 🔧 Key Tools & Concepts  
- **Amazon EC2**: Virtual machine in the cloud for app deployment  
- **SSH Connections**: Secure login to the EC2 instance  
- **Key Pairs**: Secure authentication for remote access  
- **VS Code with Remote-SSH Extension**: Live editing files on the server  
- **Java & Maven**: Java-based web application creation using archetypes  

---

## 🚀 Project Reflection  
This 2-hour project included some real-world troubleshooting. One surprise was being asked to use both **VS Code Remote-SSH** and the **local terminal** to edit and validate changes on the server. Successfully SSH'ing into the EC2 instance and seeing the edits live was the most rewarding part!

---

## 🖥️ Launching an EC2 Instance  
We started by launching an **Ubuntu-based EC2 instance**. This server hosted our web app.  

---

## 🔐 Enabling SSH  
SSH allows secure command-line access to our EC2 instance. Port 22 was opened in the EC2 **security group** to allow this connection.

**Key command used:**
```bash
ssh -i "nextwork-keypair.pem" ec2-user@<your-public-ip>
```

---

## 🗝️ Creating Key Pairs  
A key pair was created through AWS Console. The **private key** `nextwork-keypair.pem` was downloaded and moved into a folder called `devops`.

**Windows Permissions Fix:**
```bash
icacls "nextwork-keypair.pem" /reset
icacls "nextwork-keypair.pem" /grant:r "USERNAME:R"
icacls "nextwork-keypair.pem" /inheritance:r
```

---

## 🧑‍💻 Setting Up VS Code  
Installed the **Remote-SSH extension** in VS Code, allowing direct connection and editing of server files.

Configuration included:
- EC2 public IP as hostname
- Path to the `.pem` file
- SSH username: usually `ubuntu`

---

## ☕ Maven & Java  
- Installed **Java and Maven** on EC2 to generate the web app.  
- Used Maven archetypes to scaffold a basic Java web project.

**Command used to generate the project:**
```bash
mvn archetype:generate
```

---

## 🗂️ Application Structure  
Using VS Code's file explorer, I could see the generated project folders:
- `/src` - Contains Java source code
- `/webapp` - Contains static and dynamic HTML (like `index.jsp`)

We edited `index.jsp` to display:
```html
<h1>Hello Vamshi</h1>
```

---

## ✍️ Remote Editing with VS Code  
The Remote-SSH extension allowed me to:
- Browse the server filesystem  
- Edit files in real-time  
- View updates by refreshing the hosted site  

---

## 📅 What’s Next?  
This was just **Part 1** of a series of DevOps projects. Upcoming steps include:
- CI/CD automation with GitHub Actions  
- Dockerizing the application  
- Hosting via Nginx or Load Balancer  

---

**🌐 Learn More:** Check out [NextWork.org](https://nextwork.org) for more DevOps projects and tutorials.  

---

**Everyone deserves to be in a job they love.**
