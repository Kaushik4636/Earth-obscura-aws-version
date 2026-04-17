🌍 Earth Obscura (AWS Edition)

Earth Obscura is a highly available web application deployed on a custom AWS cloud architecture. It demonstrates a secure, scalable, and performance-oriented infrastructure using a tiered network design with public and private subnets, automated content delivery, and a managed database backend.

---

🏗 System Architecture

The application is hosted on a secure AWS infrastructure designed for reliability and scalability.

Infrastructure Components:

- VPC (Virtual Private Cloud): An isolated network environment within AWS.
- Public Subnets: Contain the Application Load Balancer (ALB) and EC2 instances for handling incoming traffic.
- Private Subnets: Securely host backend resources like RDS and EFS, preventing direct internet access.
- S3 (Simple Storage Service): Stores static assets such as images and videos.
- RDS (Relational Database Service): Managed database with a standby replica in a separate subnet for high availability and failover.
- EFS (Elastic File System): Shared storage accessible across multiple EC2 instances.

---

🚦 Request Workflow

1. The user enters the domain name.
2. DNS (Hostinger) points the request to AWS nameservers.
3. Route 53 routes the request to the CloudFront distribution.
4. CloudFront serves cached content from edge locations for faster delivery.
5. Traffic enters the VPC via the Internet Gateway (IGW).
6. The Application Load Balancer (ALB) distributes requests to healthy EC2 instances.
7. EC2 instances process requests using the Node.js backend.
8. Data is fetched from or stored in the RDS database.

---

🛠 Tech Stack

- Frontend: React, HTML, CSS
- Backend: Node.js
- Cloud Services: AWS (EC2, RDS, S3, CloudFront, Route 53, ALB, EFS)
- Database: MySQL / PostgreSQL (via AWS RDS)

---

🚀 Deployment Steps

1. Clone the Repository

```bash
git clone https://github.com/Kaushik4636/Earth-obscura-aws-version.git
cd Earth-obscura-aws-version
Configure Backend

Create a .env file or update config.js with your RDS endpoint:

const host = "your-db-instance.xxxxxx.rds.amazonaws.com";
Start the Server

Use PM2 to keep the server running:

npm install
sudo npm install -g pm2
pm2 start index.js --name "earth-obscura"

📋 Architecture Key (Glossary)

EC2: Virtual Server
S3: Object Storage
RDS: Managed Database Service
ALB: Application Load Balancer
VPC: Virtual Private Cloud

👤 Author

Kaushik
