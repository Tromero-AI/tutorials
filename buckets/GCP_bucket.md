# How to Download Your GCP Bucket Data (A Quick Guide to Have Your Data in the Palm of Your Hand)

In this short guide, we'll walk you through how to get your valuable data onto your Tromero instances, enabling you to build the next AI model of the future. Please note that this tutorial is intended for Tromero OS templates. If you are using your own image, the following commands may not work.

This guide consists of four easy steps:
1. Installation of Google Cloud CLI
2. Authentication via the Google Cloud CLI
3. Downloading your data from your bucket
4. Uploading data to your buckets

After these steps, you will be proficient in managing your data with GCP.

## Step 1 - Installing Google Cloud CLI

1. Ensure that the package list is updated:

    ```bash
    sudo apt-get update
    ```

2. Install the necessary packages:

    ```bash
    sudo apt-get install apt-transport-https ca-certificates gnupg curl
    ```

3. Import the Google Cloud public key:

    ```bash
    curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo gpg --dearmor -o /usr/share/keyrings/cloud.google.gpg
    ```

4. Add the gcloud CLI distribution URI as a package source:

    ```bash
    echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
    ```

5. Update the package list and install the gcloud CLI:

    ```bash
    sudo apt-get update && sudo apt-get install google-cloud-cli
    ```

## Step 2 - Authentication via the Google Cloud CLI

1. Initialize gcloud:

    ```bash
    gcloud init
    ```

   This command will prompt you to log in, showing a link that you can copy and paste into your browser. The browser will ask you to log in with your Google account and will then provide an authentication token. Copy and paste this token into your terminal for authentication.

2. After logging in, the terminal will display a list of projects to choose from. You can also configure the default compute region and zone.

## Step 3 - Downloading Your Data from Your Bucket

To download data from a specific bucket, use the following command to copy the contents of a file into your local file system:

```bash
gsutil cp gs://[BUCKET_NAME]/[OBJECT_NAME] [LOCAL_FILE_PATH]

```

# Step 4 - Uplodaing your data to your chosen bucket

- To upload a directory you can you use the following command:

```bash
gsutil cp -r [LOCAL_DIRECTORY]/* gs://[BUCKET_NAME]
```

- To upload a single file 

```bash
gsutil cp [LOCAL_FILE_PATH] gs://[BUCKET_NAME]/[OBJECT_NAME]
```
