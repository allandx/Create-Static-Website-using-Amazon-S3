# Create-Static-Website-using-Amazon-S3
Documentation to create a Static Website using Amazon S3

Intro

To create and configure a simple stattic website in S3 which consist files like HTML, CSS, JavaScript, fonts and image

Create S3 Bucket**

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

2. ### Enable Static Website hosting###

1. Click the **Properties** tab.
2. Scroll to the bottom of the screen to find the *Static website hosting* section.
3. On the right in the *Static website hosting* section, click **Edit**.
4. On the *Edit static website hosting* page, set the following values:
    - *Static website hosting*: **Enable**
    - *Hosting type*: **Host a static website**
    - *Index document*: **index.html**
    - *Error document*: **error.html**
5. Scroll down, and click **Save changes**.
6. Scroll back down to the *Static website hosting* section.
7. Open the listed endpoint URL in a new browser tab. You'll see a `403 Forbidden` error message.

3. ## Apply Bucket Policy ##

1. Back in S3, click the **Permissions** tab.
2. In the *Bucket policy* section, click **Edit**.
3. In the *Policy* box, enter the following JSON statement (replacing `<BUCKET_ARN>` with the bucket ARN provided right above the *Policy* box):
    
    ```
    {
      "Version":"2012-10-17",
      "Statement":[{
         "Sid":"PublicReadGetObject",
         "Effect":"Allow",
         "Principal": "*",
         "Action":["s3:GetObject"],
         "Resource":["<BUCKET_ARN>/*"]
      }]
    }
    ```
    
    > Note: Ensure the trailing /* is present so the policy applies to all objects within the bucket.
    > 
4. Click **Save changes**.
5. Refresh the browser tab with the static website (the endpoint URL you opened a minute ago). This time, it should load the site correctly.
6. Add a `/` at the end of the URL and some random letters (anything that's knowingly an error). This will display your `error.html` page.


