**Table of Contents**
**Google Cloud Platform (GCP) Access & Configuration**

1.1. Setting up GCP CLI (gcloud)

1.2. Authenticating Accounts and Configuring Projects 

1.3. Gcloud Cli commands

**Google Cloud Platform (GCP) Access & Configuration**

This section provides a step-by-step guide to setting up and configuring access to Google Cloud Platform (GCP) resources using the gcloud command-line interface (CLI)

**Step 01. Setting up GCP CLI (gcloud)**

The gcloud CLI is the primary tool for managing your Google Cloud resources from the command line.

**01. Installing gcloud CLI on Windows**
Download the Google Cloud SDK installer: Navigate to the official Google Cloud SDK download page (https://cloud.google.com/sdk/docs/install) and download the installer for Windows.

![1](https://github.com/user-attachments/assets/509cfe61-5db2-4718-a8fe-43d54a1e0881)

Run the installer: Once the download is complete, run the executable file. Follow the prompts in the Google Cloud SDK Setup wizard.

![2](https://github.com/user-attachments/assets/3e4676fe-e8c7-40f3-8877-acde80490e43)

![3](https://github.com/user-attachments/assets/5dc0bfe6-9ba9-431d-8ceb-d0f4bbdfff7c)


![4](https://github.com/user-attachments/assets/2e737646-efe5-4ca7-ac27-8beeaf5dfd93)


![5](https://github.com/user-attachments/assets/a9cbb00b-a72d-4f44-9f6d-85f39a702cb1)


![6](https://github.com/user-attachments/assets/39ccf971-e06e-4c62-9b76-e6bb8b816a51)


![7](https://github.com/user-attachments/assets/a48a0dc7-ceb8-413b-823d-0f301a74bbd1)


Choose installation options:

Welcome: Click "Next".

License Agreement: Accept the license agreement and click "Next".

Installation Options: Choose "Install for all users" or "Install for current user only" based on your preference. Click "Next".

Destination Folder: Choose the installation directory. The default is usually C:\Program Files\Google\Cloud SDK. Click "Next".

Setup Type: Select "Typical" for a standard installation. Click "Next".


Components: Ensure "gcloud CLI" is selected. You can also choose to install other components like gsutil (for Cloud Storage) and bq (for BigQuery) if needed. Click "Install".

Complete the installation: After the installation finishes, you will typically be prompted to initialize the SDK. Check "Start Google Cloud SDK Shell" and "Run gcloud init" to proceed with the initial configuration. Click "Finish".

Verify the installation: Open a new command prompt or PowerShell window and type gcloud version. You should see the installed gcloud CLI version, confirming a successful installation. ![9](https://github.com/user-attachments/assets/d7cb96b3-de9e-479a-9c7a-77c7801aa665)

**Step 02. Installing gcloud CLI on Mac**

Download the Google Cloud SDK archive: Navigate to the official Google Cloud SDK download page (https://cloud.google.com/sdk/docs/install) and download the appropriate archive for macOS (e.g., google-cloud-sdk-*-darwin-x86_64.tar.gz).

Extract the archive: Open Terminal and navigate to the directory where you downloaded the archive. Extract the contents:

tar -xzf google-cloud-sdk-*-darwin-x86_64.tar.gz
This will create a google-cloud-sdk directory.

Install and initialize the SDK: Navigate into the extracted directory and run the install.sh script:

cd google-cloud-sdk
./install.sh
The script will prompt you to add gcloud to your PATH and enable shell command completion. It is recommended to accept these options. You may need to restart your shell for the changes to take effect.

Initialize the SDK: After installation, initialize the SDK:

gcloud init
This command will guide you through authenticating your account and configuring a default project.

Verify the installation: Open a new Terminal window and type gcloud version. You should see the installed gcloud CLI version.

**Step 03. Authenticating Accounts and Configuring Projects**

After installing the gcloud CLI, you need to authenticate your Google account and configure a default GCP project to work with.

![8](https://github.com/user-attachments/assets/7c152f2b-4253-40dc-81ac-ad3da208cf0a)


**03. Authenticating Your Google Account**

To authenticate the gcloud CLI with your Google account, use the gcloud auth login command:

gcloud auth login
This command will open a web browser, prompting you to sign in with your Google account. Once authenticated, your credentials will be stored locally, allowing the gcloud CLI to access GCP resources on your behalf.

![10](https://github.com/user-attachments/assets/a4e44736-7fec-4fcb-a946-645585ef7ac1)


![11](https://github.com/user-attachments/assets/2fe0d62b-5317-47d0-9da1-704b12f33997)


**3.1. Configuring a Default Project**

After authentication, you can set a default GCP project for your gcloud CLI. This saves you from specifying the project ID with every command.

List available projects: To see a list of projects you have access to, run:
gcloud projects list
![12](https://github.com/user-attachments/assets/e3b2ccc2-e682-4bd2-bd8d-fbef5536ae80)

2. Set a default project: Use the gcloud config set project command, replacing YOUR_PROJECT_ID with the actual ID of your GCP project: bash gcloud config set project YOUR_PROJECT_ID  You can find your project ID in the GCP Console dashboard or by using the gcloud projects list command.

![13](https://github.com/user-attachments/assets/2e497f2f-5e7f-45bb-9abc-bcf97b03220b)

 ![14](https://github.com/user-attachments/assets/b1f93cac-8f56-45de-ad05-beb831fe64d6)


3. Verify current configuration: To check your current active account and project, use: bash gcloud config list
   ![15](https://github.com/user-attachments/assets/925373a6-2534-4d3b-aa0c-530dc061c793)

**Step 04:Google CLI Commands**

gcloud init: Initialize, authorize, and configure the gcloud CLI.

gcloud version: Display version and installed components.

gcloud components install: Install specific components.

gcloud components update: Update your gcloud CLI to the latest version

gcloud config set project: Set a default Google Cloud project to work on.

gcloud info: Display current gcloud CLI environment details.


**4.1 Help**

gcloud help: Search the gcloud CLI reference documents for specific terms.

gcloud feedback: Provide feedback to the gcloud CLI team.

gcloud topic: Supplementary help material for non-command topics like accessibility, filtering, and formatting.

**4.2 Personalization**

gcloud config set: Define a property (like compute/zone) for the current configuration.

gcloud config get: Fetch the value of a gcloud CLI property.

gcloud config list: Display all the properties for the current configuration.

gcloud config configurations create: Create a new named configuration.

gcloud config configurations list: Display a list of all available configurations.

gcloud config configurations activate: Switch to an existing named configuration.

**4.3 Authorization and Credentials**

gcloud auth login: Authorize Google Cloud access for the gcloud CLI with Google Cloud user credentials and set the current account as active.

gcloud auth activate-service-account: Authorize Google Cloud access similar to gcloud auth login but with service account credentials.

gcloud auth application-default: Manage your Application Default Credentials (ADC) for Cloud Client Libraries.

gcloud auth list: List all credentialed accounts.

gcloud auth print-access-token: Display the current account's access token.

gcloud auth revoke: Remove access credentials for an account.


**4.4 Projects**

gcloud projects describe: Display metadata for a project (including its ID).

gcloud projects add-iam-policy-binding: Add an IAM policy binding to a specified project.

**4.5 IAM**
gcloud iam list-grantable-roles: List IAM grantable roles for a resource.

gcloud iam roles create: Create a custom role for a project or org.

gcloud iam service-accounts create: Create a service account for a project.

gcloud iam service-accounts add-iam-policy-binding: Add an IAM policy binding to a service account.

gcloud iam service-accounts set-iam-policy-binding: Replace existing IAM policy binding.

gcloud iam service-accounts keys list: List a service account's keys.

**4.6 Docker & Google Kubernetes Engine (GKE)**
gcloud auth configure-docker: Register the gcloud CLI as a Docker credential helper.

gcloud container clusters create: Create a cluster to run GKE containers.

gcloud container clusters list: List clusters for running GKE containers.

gcloud container clusters get-credentials: Update kubeconfig to get kubectl to use a GKE cluster.

gcloud container images list-tags: List tag and digest metadata for a container image.

**4.7 Virtual Machines & Compute Engine**

gcloud compute zones list: List Compute Engine zones.

gcloud compute instances create: Create a VM instance.

gcloud compute instances describe: Display a VM instance's details.

gcloud compute instances list: List all VM instances in a project.

gcloud compute disks snapshot: Create snapshot of persistent disks
.
gcloud compute snapshots describe: Display a snapshot's details.

gcloud compute snapshots delete: Delete a snapshot.

gcloud compute ssh: Connect to a VM instance by using SSH.


**4.8 Serverless & App Engine**

gcloud app deploy: Deploy your app's code and configuration to the App Engine server.

gcloud app versions list: List all versions of all services deployed to the App Engine server.

gcloud app browse: Open the current app in a web browser.

gcloud app create: Create an App Engine app within your current project.

gcloud app logs read: Display the latest App Engine app logs.

**4.9 Miscellaneous**

gcloud kms decrypt: Decrypt ciphertext (to a plaintext file) using a Cloud Key Management Service key.

gcloud logging logs list: List your project's logs.

gcloud sql backups describe: Display info about a Cloud SQL instance backup.

gcloud sql export sql: Export data from a Cloud SQL instance to a SQL file
