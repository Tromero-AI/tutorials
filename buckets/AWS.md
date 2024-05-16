# AWS CLI Setup and S3 Data Management Guide

This guide provides instructions on how to install the AWS Command Line Interface (CLI), configure it, and use it to manage data in an AWS S3 bucket.

## Requirements

- AWS Account
- IAM user with appropriate permissions
- Access to a Linux-based terminal (for Windows, use WSL or a similar tool)

## Steps

### 1. Create or Edit IAM User
- Log in to the AWS Management Console.
- Navigate to **IAM** (Identity and Access Management).
- Choose **Users** from the navigation pane.
- Click **Add user** or select an existing user.
- Enable **Programmatic access**.
- Attach the **AmazonS3FullAccess** policy (adjust as necessary based on your security requirements).
- Review and create the user.
- In the final screen, download the CSV file containing the user's new Access Key ID and Secret Access Key or copy them securely.

### 2. Install AWS CLI
- Open your terminal.
- Run the following commands to download and install the AWS CLI:
    ```bash
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
    unzip awscliv2.zip
    sudo ./aws/install
    ```

### 3. Configure AWS CLI
- In your terminal, configure the AWS CLI with your new IAM user credentials:
    ```bash
    aws configure
    ```
- Enter the **Access Key ID** and **Secret Access Key** when prompted.
- For **Default region name** and **Default output format**, press Enter to use the defaults or specify your preferences.

### 4. Download Data from S3 Bucket
- Use the following command to download data from your S3 bucket to a local directory:
    ```bash
    aws s3 sync s3://your-bucket-name local-directory
    ```
- Replace `your-bucket-name` with your actual S3 bucket name.
- Replace `local-directory` with the path to where you want to store the files on your local machine.

### 5. Upload Data to S3 Bucket
- To upload data from your local directory back to the S3 bucket:
    ```bash
    aws s3 sync local-directory s3://your-bucket-name
    ```
- Use the same replacements as mentioned in the download step.