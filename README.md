# Deployment-of-a-Static-Website-Using-AWS-S3-and-CloudFront

### This project details the steps to establish a static website using AWS services. We'll utilize S3 to host website files, apply a public read policy to a private bucket, and deliver content globally through CloudFront. This guide aims to demonstrate a simple and secure method for efficient website deployment on AWS.

### You might be wondering what CloudFront is and what its benefits are. According to Amazon Web Services, Amazon CloudFront accelerates the distribution of your static and dynamic web content, including .html, .css, .php, image, and media files. When users request your content, CloudFront delivers it via a global network of edge locations, ensuring low latency and high performance.
----
----

# Download a staticwebsite

The first thing to do is to download a static website from any of the following link and extract all.

* https://www.themezy.com/free-website-templates/246-free-responsive-app-website-template or

* https://www.tooplate.com/

# Creating and Configuring the S3 Bucket

After logging into my AWS account, I headed straight to the S3 service by searching for "S3" in the console's search bar. I needed to create a new bucket for my static website, so I clicked on "Create bucket." I named this bucket
"cloud-web-app123"

![](./Static-Website/step%201%20create%20s3.png)
![](./Static-Website/step%201%20bis.png)
![](./Static-Website/step1%20bis2.png)

2- Once the bucket was set up, I clicked on its name to access it. Here, I found the option to upload files. I clicked on "Upload" and selected the static files for my website—HTML, CSS, and any images I planned to use. After confirming all files were ready, I clicked "Upload" to move everything to the root directory of my new S3 bucket.

![](./Static-Website/step%202%20upload.png)

* Uploaded folders

![](./Static-Website/step%203%20uploaded%20files.png)

3.Once my files were uploaded, the next step was to make them accessible as a website. To do this, I navigated to the Permissions tab of my bucket. Here, I found the option for Static website hosting. I clicked on it to configure the settings needed to serve my static content. I enabled static website hosting by selecting the option "Use this bucket to host a website." In the text boxes provided, I entered the name of my index document which is index.html. After filling in these details, I saved the settings.

![](./Static-Website/step%204%20edit%20bucket.png)
![](./Static-Website/step%204%20bis1.png)
![](./Static-Website/)

4. Next, i went to the bucket, i selected the objects then actions, Make public using ACL. After that i went to the properties of my bucket, copied the URL of the static website, opened a new tab and pasted it. My webapp is accessible but NOT SECURE. In this case, we need to configure a CloudFront Distribution to make it secure.

![](./Static-Website/step%204%20bis%202.png)

![](./Static-Website/step%204make%20public.png)

![](./Static-Website/step%205%20website%20link.png)

![](./Static-Website/step%206%20web%20pic.png)

----
----

# Setting Up AWS CloudFront

5- After configuring my S3 bucket to host the static website, I proceeded to set up AWS CloudFront for global content distribution. I began by navigating to the CloudFront service through the AWS Management Console search.

6- I started the creation of a new distribution by clicking on "Create distribution." For the origin domain, I selected my S3 bucket URL from the dropdown menu. In the origin access settings, I chose "Origin access control settings." I clicked on "Create new OAC," and a pop-up appeared where I confirmed that my origin name was displayed correctly. I left all other settings as default and proceeded to create the OAC.

* First, i went to the my bucket permission and Block all public access.

![](./Static-Website/step%207%20-%20cloudfront.png)

![](./Static-Website/step%208%20distri.png)

![](./Static-Website/step%209%20create.png)

![](./Static-Website/step%2010%20oac.png)

7- Continuing with the configuration, I scrolled down to the distribution settings and set the Default root object to index.html, ensuring that CloudFront serves the index.html file when accessing the root URL of the distribution.

![](./Static-Website/correction%20policy.png)

![](./Static-Website/step%2012%20edit%20policy.png)

9- Went back to the CloudFront Distribution and ensure it was Enabled. I clicked on the distribution ID, copied the distribution domain name and pasted in a new tab my browser.

My static-website was successfully deployed and secure as expected.

![](./Static-Website/web%20secure.png)

This is how to host a secure static website usng a s3 bucket CloudFront.

## Well done...You made it to the end!









