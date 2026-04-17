🌍 Earth Obscura (AWS Edition)
Earth Obscura is a high-availability web application deployed on a custom AWS Cloud architecture. This project demonstrates a secure, tiered network design using Public and Private subnets, integrated with automated content delivery and a managed database backend.

🏗 System Architecture
The project is hosted on a highly secure AWS infrastructure designed for scalability and performance.

Infrastructure Components:
VPC (Virtual Private Cloud): An isolated private network in the cloud.

Public Subnets: Houses the ALB (Traffic Manager) and EC2 (Virtual Servers) for public access.

Private Subnets: Secure zone for the RDS (Database) and EFS (Shared File System) to prevent direct internet exposure.

S3 (Storage Buckets): Stores static assets (images/videos) for the website.

RDS (Managed Database): A primary database instance with a Standby Replica in a different subnet for automated backups and failover.

EFS (Elastic File System): Shared network storage accessible by multiple EC2 instances.

🚦 Request Workflow
The traffic flows from the user to the server through the following path:

DNS (Hostinger): User enters the URL, which is pointed to AWS nameservers.

Route 53 (DNS Service): Routes the domain request to the CloudFront distribution.

CloudFront (CDN): Speeds up delivery by caching content at "Edge Locations" near the user.

Internet Gateway (IGW): The entry point into the AWS VPC.

ALB (Application Load Balancer): Receives the traffic and distributes it to the healthy EC2 instances.

EC2 (Virtual Servers): Runs the Node.js backend to process logic and serve the frontend.

RDS (Database): The EC2 fetches/stores data from this secure backend layer.

🛠 Tech Stack
Frontend: React/HTML/CSS (Standard Web Stack)

Backend: Node.js (JavaScript)

Cloud: AWS (EC2, RDS, S3, CloudFront, Route 53, ALB, EFS)

Database: MySQL/PostgreSQL via AWS RDS

🚀 Deployment Steps
1. Clone the Repository
Bash
git clone https://github.com/Kaushik4636/Earth-obscura-aws-version.git
cd Earth-obscura-aws-version
2. Configure Backend
Create a .env file or update your config.js to connect to your RDS endpoint:

JavaScript
// Database connection
const host = "your-db-instance.xxxxxx.rds.amazonaws.com"; 
3. Start the Server
Using PM2 to ensure the virtual server keeps running:

Bash
npm install
sudo npm install -g pm2
pm2 start index.js --name "earth-obscura"
📋 Architecture Key (Glossary)
EC2: Virtual Computer / Server

S3: Storage Buckets

RDS: Managed Database

ALB: Traffic Manager

VPC: Private Cloud Network

Author
Kaushik
