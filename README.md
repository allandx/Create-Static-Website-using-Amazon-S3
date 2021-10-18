# Create-Static-Website-using-Amazon-S3
Documentation to create a Static Website using Amazon S3

Intro

To create and configure a simple stattic website in S3 which consist files like HTML, CSS, JavaScript, fonts and image

### **Create S3 Bucket**

1. Begin by navigating to the [GitHub repository for the code](https://github.com/ACloudGuru-Resources/Course-Certified-Solutions-Architect-Associate/tree/master/labs/creating-a-static-website-using-amazon-s3).
2. Select the **error.html** file.
3. Above the code area, click **Raw**.
4. Right-click and select **Save Page As**, and save the file as **error.html**.
    
    > Note: If you are using Safari as your web browser, ensure that you remove the .txt from the end of the filename. Also, ensure that the Format is Page Source. When asked whether you want to save the file as plain text, click Don't Append.
    > 
5. Repeat this for the **index.html** file.
6. From the AWS Management Console, navigate to S3.
7. Click **Create bucket**.
8. Set the following values:
    - *Bucket name*: **my-bucket-** with the AWS account number or another series of numbers at the end to make it globally unique
    - *Region*: **US East (N. Virginia) us-east-1**
9. In the *Block Public Access settings for this bucket* section, un-check *Block all public access*.
    - Ensure all 4 permissions restrictions beneath it are also un-checked.
10. Check the box to acknowledge that turning off all public access might result in the bucket and its objects becoming public.
11. Leave the rest of the settings as their defaults.
12. Click **Create bucket**.
13. Click the radio button next to the bucket name to select it.
14. Click **Copy ARN**.
15. Select the bucket name.
16. Click **Upload**.
17. Click **Add files**, and upload the `error.html` and `index.html` files you previously saved from GitHub.
18. Leave the rest of the settings as their defaults.
19. Click **Upload**.
20. Click **Close** in the upper right.



2. Enable Static Website hosting
