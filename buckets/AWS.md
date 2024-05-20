# How to Download Your AWS S3 Storage Bucket Data (A Quick Guide to Have Your Data in the Palm of Your Hand)

This guide provides instructions on how to install the AWS Command Line Interface (CLI), configure it, and use it to manage data in an AWS S3 bucket.
This guide consists of four easy steps:
1. Installation of AWS CLI
2. Authentication via the AWS CLI
3. Downloading your data from your bucket
4. Uploading data to your buckets

## Steps

### Step 1 - Create or Edit IAM User
- Log in to the AWS Management Console.
- Navigate to **IAM** (Identity and Access Management).
- Choose **Users** from the navigation pane.
- Click **Add user** or select an existing user.
- Enable **Programmatic access**.
- Attach the **AmazonS3FullAccess** policy (adjust as necessary based on your security requirements).
- Review and create the user.
- In the final screen, download the CSV file containing the user's new Access Key ID and Secret Access Key or copy them securely.

### Step 2 - Installing AWS CLI
- Open your terminal.
- Run the following commands to download and install the AWS CLI:
    ```bash
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
    unzip awscliv2.zip
    sudo ./aws/install
    ```

### Step 3 - Authentication via AWS CLI
- In your terminal, configure the AWS CLI with your new IAM user credentials:
    ```bash
    aws configure
    ```
- Enter the **Access Key ID** and **Secret Access Key** when prompted.
- For **Default region name** and **Default output format**, press Enter to use the defaults or specify your preferences.

### Step 4 - Downloading Your Data from Your Bucke
- Use the following command to download data from your S3 bucket to a local directory:
    ```bash
    aws s3 sync s3://your-bucket-name local-directory
    ```
- Replace `your-bucket-name` with your actual S3 bucket name.
- Replace `local-directory` with the path to where you want to store the files on your local machine.

### Step 5 - Uplodaing your data to your chosen buckett
- To upload data from your local directory back to the S3 bucket:
    ```bash
    aws s3 sync local-directory s3://your-bucket-name
    ```
- Use the same replacements as mentioned in the download step.
