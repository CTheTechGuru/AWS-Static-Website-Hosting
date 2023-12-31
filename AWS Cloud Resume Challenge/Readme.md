
![Cloud](https://github.com/CTheTechGuru/AWS-Projects/assets/125163096/cf26a8eb-93ab-44b7-9537-f781f886120c)



I hosted a website on AWS using an S3 bucket, and I leveraged CloudFront as my CDN (Content Delivery Network).
To ensure security and proper domain management, I also utilized Route 53 and Certificate Manager.

Here are the steps I followed:

Step 1: Creating the S3 Bucket I started by creating an S3 bucket to store my website's static files. I made sure to enable the "Static website hosting" feature for the bucket and configured it to use the "index.html" file as the default root object.

Step 2: Uploading Website Files Next, I uploaded my website files (HTML, CSS, JavaScript, and any other assets) to the S3 bucket. I made sure to grant appropriate permissions to these files, allowing public read access, so they could be accessed by CloudFront.

Step 3: I Configured Bucket Permissions since I wanted my S3 bucket to be private and only accessible through CloudFront, I adjusted the bucket's permissions. I created an Origin Access Identity (OAI) in CloudFront and granted it read access to the S3 bucket. Then, I modified the bucket policy to deny public access and allow access only from the OAI.

Step 4: I created a CloudFront Distribution. In this step, I created a CloudFront distribution to serve as a CDN for my website. I configured it to use the S3 bucket as the origin and associated the OAI with the distribution. This ensured that CloudFront would fetch the website content from the S3 bucket while maintaining the bucket's private access.

Step 5: Set Up Route 53 To have a custom domain for my website. I used Route 53, AWS's DNS service. I created a hosted zone for my domain and added a record set of type "A" to point to my CloudFront distribution. This step allowed me to access my website using a user-friendly domain name.

Step 6: Obtained an SSL/TLS Certificate To secure my website with HTTPS, I utilized AWS Certificate Manager (ACM) to obtain an SSL/TLS certificate. I requested a certificate for my domain name, and once approved, I associated it with my CloudFront distribution. This enabled visitors to access my website securely.

Step 7: Testing and Finalizing Finally, I tested my website to ensure everything was working smoothly. I accessed it through my custom domain and confirmed that it was being served securely via HTTPS. I also checked that any changes made to the S3 bucket were reflected correctly through CloudFront's caching mechanism.



https://www.clowman.cloud
