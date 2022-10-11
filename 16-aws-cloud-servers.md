# AWS Cloud Servers

Putting servers in the cloud.

## AWS EC2

An EC2 instance is a virtual machine that can be quickly provisioned and orchestrated using either the GUI console, the command line, or scripts. They can be used for web apps or for other computations like data analysis or machine learning. For web apps, they can cheaper than using a PaaS like Heroku.

The EC2 virtual machines come is sizes from micro to XL can are charged by how long you run them. 

## EB Elastic Beanstalk

EC2 instances can be orchestrated by scripts, but EB can help you to do the most common tasks of running a web app written in the most common ecosystems such as Node.js, Python, or Java. It will choose an updated version of Linux and install the stack you choose. Then it will run your app and add things like a load balancer to give you a working web server almost automatically. It also gives you tools to monitor the EC2 instances it creates.
