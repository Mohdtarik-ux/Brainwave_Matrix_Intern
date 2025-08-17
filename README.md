A static web portfolio deployed using AWS S3 and delivered globally via CloudFront CDN
<img width="1366" height="736" alt="Static web portfolio1 " src="https://github.com/user-attachments/assets/1c36a96b-096d-4dd6-b156-efaf418af2a2" />
<img width="1366" height="736" alt="static web portfolio2" src="https://github.com/user-attachments/assets/e292b634-ece8-4e92-9bc6-8c65de98670f" />

 # Live site URL:
https://d31vktgdbnjbx4.cloudfront.net

# Project Overview
This is a fully static web portfolio designed to showcase my skills and projects. It’s built with standard web technologies:

HTML for structure.
CSS for styling.
JavaScript for interactivity.
The site is hosted cost-effectively on AWS S3 with CloudFront CDN improving speed, availability, and security (HTTPS).

#Features
Fully responsive and mobile-friendly design
Gradient header and animated skill cards
Interactive elements like "SAY HELLO!" alert button
Simple and clean UI for showcasing projects
Fast global delivery with AWS CloudFront CDN over HTTPS

#Tech Stack & Tools
Technology	Purpose
HTML, CSS, JavaScript	Frontend design and interactivity
AWS S3	Static website hosting
AWS CloudFront	CDN with HTTPS for fast and secure access

# Code Snippets & Configurations
1. Bucket Policy for Public Read Access
json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadForGetBucketObjects",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::mohd-tarik-portfolio-2025/*"
    }
  ]
}
2. AWS CLI Command to Sync Files (upload & update)
bash
aws s3 sync ./ s3://mohd-tarik-portfolio-2025 --delete
This command uploads your local files to the S3 bucket, replacing files that no longer exist locally (--delete).

 3.Basic index.html Code Example
xml
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mohd Tarik's Portfolio</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header>
    <h1>Welcome to My AWS Portfolio</h1>
  </header>
  <section id="skills">
    <div class="skill-card">Cloud Enthusiast</div>
    <div class="skill-card">AWS Certified</div>
    <div class="skill-card">JavaScript Developer</div>
  </section>
  <button onclick="alert('Hello! Thanks for visiting.')">Say Hello!</button>
  <script src="main.js"></script>
</body>
</html>
4. Example CSS (styles.css)
css
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 20px;
  background: linear-gradient(to right, #4A90E2, #50E3C2);
  color: #fff;
  text-align: center;
}

.skill-card {
  background: rgba(255, 255, 255, 0.15);
  border-radius: 8px;
  padding: 15px;
  margin: 10px auto;
  width: 200px;
  font-weight: bold;
  box-shadow: 0 2px 6px rgba(0,0,0,0.3);
}
5. Example JavaScript (main.js)
javascript
document.querySelector('button').addEventListener('click', () => {
  alert('Hello! Thanks for visiting my portfolio.');
});

#Deployment Process (Step-by-step)
Step 1: 
Create an S3 Bucket
Go to AWS Console → S3 → Click Create bucket
Enter bucket name mohd-tarik-portfolio-2025
Region: Choose your preferred region
Enable: Static website hosting
Set the Index document to index.html
<img width="1366" height="736" alt="s3 bucket" src="https://github.com/user-attachments/assets/c7ea8505-f09f-4312-bf54-948117a05fcb" />



Step 2:
Configure Bucket Policy
Go to the Permissions tab of your bucket
Click Bucket policy and paste the JSON shown above
This ensures your files can be publicly accessed

Step 3:
Upload Files
Upload your static files including index.html, CSS, JS, and any images either via:
AWS Management Console upload interface, OR
AWS CLI command (shown above)

Step 4:
Setup CloudFront Distribution
In AWS Console, open CloudFront
Create new Distribution:
<img width="1366" height="736" alt="Cloudfront" src="https://github.com/user-attachments/assets/d16bc0a5-a7ed-48e0-a6c2-7c95811b9e4b" />


Origin: 
S3 website endpoint URL, e.g.,
mohd-tarik-portfolio-2025.s3-website-us-east-1.amazonaws.com
Set Default Cache Behavior → Redirect HTTP to HTTPS
Save and deploy distribution

Step 5:
Access Your Site
Open CloudFront URL in browser,
https://d31vktgdbnjbx4.cloudfront.net
Verify your site loads properly with CSS, JS, images

Step 6:
Monitor & Manage Billing
Check AWS Billing dashboard periodically
Keep within Free Tier to avoid unexpected charges
Delete unused resources when not needed
<img width="1366" height="736" alt="Static web portfolio1 " src="https://github.com/user-attachments/assets/dd706123-f377-4b66-b6a1-b04d46c25cf1" />



Hi! I’m Mohd Tarik, a cloud engineering intern and AWS enthusiast. 
I’m passionate about cloud computing and web development. Reach out if you want to collaborate or learn together!

🔗 Contact Me
LinkedIn: www.linkedin.com/in/
mohd-tarik-0294b0274
Email: mohdtarik2304@gmail.com

# How to Use This Repo
Clone or fork this repo to see the source code
Modify index.html, CSS, JS to add your projects or skills
Follow deployment steps to upload your updated portfolio to AWS

# THANK YOU



