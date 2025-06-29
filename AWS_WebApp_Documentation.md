 	nextwork.org
Set Up a Web App
Using AWS and
VS Code
 
Introducing Today's Project!
So today i am going to setup a webapp in the cloud. I am gping to use AWS clpud to do this.
Key tools and concepts
Services I used were VScode and Amazon EC2 and key concepts we learnt are ssh connections, using an IDE launching an instance, editing our jsp file and using key-pairs.
Project reflection
One thing we didn't expect for the project is the secret mission where we also use the local terminal to try edit a file after using the IDE. It was fun for me to see the differnece and aslo see the changes made in the terminal.
This project took me 2hours and some troubleshooting time. It was most rewarding to see a SSH connection successfull to our EC2 insance over the Terminal or VS CODE SSH connection.
This project is part one of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project in couple of days.
Launching an EC2 instance
I started this project by launching an EC2 instance because EC2 instance are like Virtual Computers in the cloud. We want our web app be hosted on the cloud. So, we are launching an EC2 instance to develop web app's code.
I also enabled SSH
SSH is a protocol that will authorizes user like our self to access remote servers like EC2 instances. It's also a type of traffic that allow us to transfer data back and forth with our EC2 instances once we are connected to it.
Key pairs
A key-pair is a mechanism for us to get access or connect our EC2 instances that we have created in AWS. We created a key-pair for our EC2 instance. Key-pairs contains two half's public key that AWS keeps and a private key that we download.
Once I set up my key-pair, AWS automatically downloaded the private key file called nextwork-keypair.pem for safe keeping we moved that private key file into a folder called devops.
Set up VS Code
Microsoft's Visual Studio Code (VS Code) is an open-source, free code editor. Along with intelligent code completion, debugging tools, and Git integration, it supports a wide range of programming languages.
We installed VS Code to write and edit our webapp's code and VS Code also have usefull extections to connect to our EC2 instances, making development and remote server management more efficient and streamlined
 
My first terminal commands
A terminal is a place for us to send command to our computer what we wanted to do. The difference between a teminal and our interface is we provide the text commands in the terminal. The first command we used is to navigate to our devops folder.
We also updated our private key by running few commands those are icacls
"nextwork-keypair.pem" /reset icacls "nextwork-keypair.pem" /grant:r "USERNAME:R" icacls "nextwork-keypair.pem" /inheritance:r these are the commands that used access the file.
 
SSH connection to EC2 instance
To connect to my EC2 instance, I ran the command "ssh -i "nextwork-keypair.pem" ec2-user@<public-ip>". This command uses my private key to securely access the server. Before that i ensured port 22 was open in the security group.
This command required an IPv4 address
A server's IPV4 DNS is that identifies where the server lives in the cloud. In our case an EC2 instances IPV4 DNS is a usefull information to connect to our local computer. It will tell our local computer where to find the EC2 instance.
 
Maven & Java
Apache Maven is a tool that helps us with creating organizing java projects like this web app. This has lots of use cases like being package manager and also tools that uses templets for sping up projects like web apps.
Maven is required in this project to create our webapp using archetypes.
Java is a progarmming language that we are using to develop our webapp. Java is also used in developing mobile apps to large enterprise systems.
Java is required in this project because it lays the foundation in writing our webapp code. Maven also need java to work.
Create the Application
we generated a Java web app using the command like mvn archetype:generate to generate a webapp using a existing tempelate that it has. It aslo tell maven to call generated webapp project nextwork-web-project.
We install Remote-SSH which is an extenction in VScode. This extenction lest us connect VScode directly to a remote server like EC2 instance.
Configuration details required to set up a remote connection include the host name ie. EC2 instance, the location of the private key and user that we logged into our instance.
 
Create the Application
Using VS Code's file explorer, I could see a bunch of folders and sub folder that desgined our web app. These folder organize our webapp.
Two of the project folders created by Maven are src and webapp, where SRC is the parent folder that contain all the source code for the webapp.
 
Using Remote - SSH
index.jsp is the file in our webapp taht defines both html content I.E the static elements that go into our webapps page as well as any cfor generating dynamic content I.E content thats always changing.
We edited index.jsp by updating the HTML file to"Hello chandu".
 
 
 	NextWork.org
Everyone should be in a job they love.
Check out nextwork.org for more projects
 
