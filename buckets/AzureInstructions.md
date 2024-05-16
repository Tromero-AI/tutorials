# How to Download Your Azure Blob Storage Bucket Data (A Quick Guide to Have Your Data in the Palm of Your Hand)

In this short guide, we'll walk you through how to get your valuable data onto your Tromero instances, enabling you to build the next AI model of the future. Please note that this tutorial is intended for Tromero OS templates. If you are using your own image, the following commands may not work.

This guide consists of four easy steps:
1. Installation of Azure Blob Storage CLI
2. Authentication via the Azure Blob Storage CLI
3. Downloading your data from your bucket
4. Uploading data to your buckets

After these steps, you will be proficient in managing your data with Azure.

## Step 1 - Installing Azure Blob Storage CLI

1. Install Azure Cli:

    ```bash
    curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
    ```

    or else check Azure's guide to installing the Azure Cli:

    https://learn.microsoft.com/en-us/cli/azure/install-azure-cli


## Step 2 - Authentication via the Azure Cloud CLI

1. Initialize gcloud:

    ```bash
    az login
    ```

   This command will prompt you to log in, showing a link that you can copy and paste into your browser. The browser will ask you to paste in the code that Azure has sent to you in your terminal.

2. After logging in, you can use the azure cli to upload and download your data from Azure.

## Step 3 - Downloading Your Data from Your Bucket

To download data from a specific bucket, use the following command to copy the contents of a file into your local file system:

```bash
az storage blob download --account-name <StorageAccountName> --container-name <ContainerName> --name <BlobName> --file <PathToLocalFile>
```

# Step 4 - Uplodaing your data to your chosen bucket

- To upload a directory you can you use the following command:

```bash
az storage blob upload --account-name <StorageAccountName> --container-name <ContainerName> --file <PathToLocalFile> --name <BlobName>
```

- To upload a single file 

```bash
az storage blob upload --account-name <StorageAccountName> --container-name <ContainerName> --file <PathToLocalFile> --name <BlobName>
```
