
## Table of Contents


1.  [Google Cloud Platform (GCP) Access & Configuration](#google-cloud-platform-gcp-access--configuration)
   
    1.1. [Setting up GCP CLI (gcloud)](#setting-up-gcp-cli-gcloud)-IN Windows OS

    1.2. [Setting up GCP CLI (gcloud)](#setting-up-gcp-cli-gcloud)-IN Mac OS
    
    1.3. [Authenticating Accounts and Configuring Projects](#authenticating-accounts-and-configuring-projects)
    
    1.4. [Gcloud Cli commands](gcloud-cli-commands)


#  Google Cloud Platform (GCP) Access & Configuration

This section provides a step-by-step guide to setting up and configuring access to Google Cloud Platform (GCP) resources using the `gcloud` command-line interface (CLI)

### Step 01. Setting up GCP CLI (gcloud)

The `gcloud` CLI is the primary tool for managing your Google Cloud resources from the command line. 

#### 01. Installing `gcloud` CLI on Windows

1.  **Download the Google Cloud SDK installer:**
    Navigate to the official Google Cloud SDK download page ([https://cloud.google.com/sdk/docs/install](https://cloud.google.com/sdk/docs/install)) and download the installer for Windows.
![1](https://github.com/user-attachments/assets/46f73b11-88cb-4fa3-b017-b077a4c1a45a)

2.  **Run the installer:**
    Once the download is complete, run the executable file. Follow the prompts in the Google Cloud SDK Setup wizard.
![2](https://github.com/user-attachments/assets/24bb07d0-8cab-4aec-8395-7c24abd1d5ce)


![3](https://github.com/user-attachments/assets/c0da6151-c86e-4c2f-bc87-e5aa99b66af9)


![4](https://github.com/user-attachments/assets/57baaf00-14bd-46b9-8a5c-1cf37071b96b)


![5](https://github.com/user-attachments/assets/d5692d87-cc0c-4280-8861-c50a77048cbe)


![6](https://github.com/user-attachments/assets/2b589f3c-b4e0-45ae-8b2c-4209131ea93f)


![7](https://github.com/user-attachments/assets/bdf33cc1-d734-4693-9586-3d48db8adc04)




3.  **Choose installation options:**
    *   **Welcome:** Click "Next".
    *   **License Agreement:** Accept the license agreement and click "Next".
    *   **Installation Options:** Choose "Install for all users" or "Install for current user only" based on your preference. Click "Next".
    *   **Destination Folder:** Choose the installation directory. The default is usually `C:\Program Files\Google\Cloud SDK`. Click "Next".
    *   **Setup Type:** Select "Typical" for a standard installation. Click "Next".
    *   **Components:** Ensure "gcloud CLI" is selected. You can also choose to install other components like `gsutil` (for Cloud Storage) and `bq` (for BigQuery) if needed. Click "Install".

4.  **Complete the installation:**
    After the installation finishes, you will typically be prompted to initialize the SDK. Check "Start Google Cloud SDK Shell" and "Run `gcloud init`" to proceed with the initial configuration. Click "Finish".

5.  **Verify the installation:**
    Open a new command prompt or PowerShell window and type `gcloud version`. You should see the installed `gcloud` CLI version, confirming a successful installation.
![9](https://github.com/user-attachments/assets/d7f86361-4f34-44b4-a12e-5909a7a9ecca)


### Step 02. Installing `gcloud` CLI on Mac

1.  **Download the Google Cloud SDK archive:**
    Navigate to the official Google Cloud SDK download page ([https://cloud.google.com/sdk/docs/install](https://cloud.google.com/sdk/docs/install)) and download the appropriate archive for macOS (e.g., `google-cloud-sdk-*-darwin-x86_64.tar.gz`).

2.  **Extract the archive:**
    Open Terminal and navigate to the directory where you downloaded the archive. Extract the contents:
    ```bash
    tar -xzf google-cloud-sdk-*-darwin-x86_64.tar.gz
    ```
    This will create a `google-cloud-sdk` directory.

3.  **Install and initialize the SDK:**
    Navigate into the extracted directory and run the `install.sh` script:
    ```bash
    cd google-cloud-sdk
    ./install.sh
    ```
    The script will prompt you to add `gcloud` to your PATH and enable shell command completion. It is recommended to accept these options. You may need to restart your shell for the changes to take effect.

4.  **Initialize the SDK:**
    After installation, initialize the SDK:
    ```bash
    gcloud init
    ```
    This command will guide you through authenticating your account and configuring a default project.

5.  **Verify the installation:**
    Open a new Terminal window and type `gcloud version`. You should see the installed `gcloud` CLI version.

### Step 03. Authenticating Accounts and Configuring Projects

After installing the `gcloud` CLI, you need to authenticate your Google account and configure a default GCP project to work with.

![8](https://github.com/user-attachments/assets/8b4b56ce-bd08-4a2e-ac63-0d55036d7761)

#### 03. Authenticating Your Google Account

To authenticate the `gcloud` CLI with your Google account, use the `gcloud auth login` command:

```bash
gcloud auth login
```

This command will open a web browser, prompting you to sign in with your Google account. Once authenticated, your credentials will be stored locally, allowing the `gcloud` CLI to access GCP resources on your behalf.



![10](https://github.com/user-attachments/assets/b086f412-591f-43c3-9592-1245e4d596d3)




![11](https://github.com/user-attachments/assets/1585ea5b-4075-4a31-91a3-7689acbaf1bd)










#### 3.1. Configuring a Default Project

After authentication, you can set a default GCP project for your `gcloud` CLI. This saves you from specifying the project ID with every command.

1.  **List available projects:**
    To see a list of projects you have access to, run:
    ```bash
    gcloud projects list
    ```
![12](https://github.com/user-attachments/assets/6df6b7b1-59f3-4bf4-96a7-4f7ddbef8aef)

2.  **Set a default project:**
    Use the `gcloud config set project` command, replacing `YOUR_PROJECT_ID` with the actual ID of your GCP project:
    ```bash
    gcloud config set project YOUR_PROJECT_ID
    ```
    You can find your project ID in the GCP Console dashboard or by using the `gcloud projects list` command.

![13](https://github.com/user-attachments/assets/280ab49a-c7e5-4d99-af57-dd7c233abcad)

![14](https://github.com/user-attachments/assets/3f62ddfb-e949-4c98-a214-20823615527c)

3.  **Verify current configuration:**
    To check your current active account and project, use:
    ```bash
    gcloud config list
    ```
![15](https://github.com/user-attachments/assets/410f89ca-39b0-418d-a4a9-9a52de877573)




## step 04 Google CLI Commands


- [`gcloud init`](https://cloud.google.com/sdk/gcloud/reference/init): Initialize, authorize, and configure the gcloud CLI.
- [`gcloud version`](https://cloud.google.com/sdk/gcloud/reference/version): Display version and installed components.
- [`gcloud components install`](https://cloud.google.com/sdk/gcloud/reference/components/install): Install specific components.
- [`gcloud components update`](https://cloud.google.com/sdk/gcloud/reference/components/update): Update your gcloud CLI to the latest version.
- [`gcloud config set project`](https://cloud.google.com/sdk/gcloud/reference/config/set): Set a default Google Cloud project to work on.
- [`gcloud info`](https://cloud.google.com/sdk/gcloud/reference/info): Display current gcloud CLI environment details.

### Help


- [`gcloud help`](https://cloud.google.com/sdk/gcloud/reference/help): Search the gcloud CLI reference documents for specific terms.
- [`gcloud feedback`](https://cloud.google.com/sdk/gcloud/reference/feedback): Provide feedback to the gcloud CLI team.
- [`gcloud topic`](https://cloud.google.com/sdk/gcloud/reference/topic): Supplementary help material for non-command topics like accessibility, filtering, and formatting.

### Personalization


- [`gcloud config set`](https://cloud.google.com/sdk/gcloud/reference/config/set): Define a property (like compute/zone) for the current configuration.
- [`gcloud config get`](https://cloud.google.com/sdk/gcloud/reference/config/get): Fetch the value of a gcloud CLI property.
- [`gcloud config list`](https://cloud.google.com/sdk/gcloud/reference/config/list): Display all the properties for the current configuration.
- [`gcloud config configurations create`](https://cloud.google.com/sdk/gcloud/reference/config/configurations/create): Create a new named configuration.
- [`gcloud config configurations list`](https://cloud.google.com/sdk/gcloud/reference/config/configurations/list): Display a list of all available configurations.
- [`gcloud config configurations activate`](https://cloud.google.com/sdk/gcloud/reference/config/configurations/activate): Switch to an existing named configuration.

### Authorization and Credentials


- [`gcloud auth login`](https://cloud.google.com/sdk/gcloud/reference/auth/login): Authorize Google Cloud access for the gcloud CLI with Google Cloud user credentials and set the current account as active.
- [`gcloud auth activate-service-account`](https://cloud.google.com/sdk/gcloud/reference/auth/activate-service-account): Authorize Google Cloud access similar to `gcloud auth login` but with service account credentials.
- [`gcloud auth application-default`](https://cloud.google.com/sdk/gcloud/reference/auth/application-default): Manage your Application Default Credentials (ADC) for Cloud Client Libraries.
- [`gcloud auth list`](https://cloud.google.com/sdk/gcloud/reference/auth/list): List all credentialed accounts.
- [`gcloud auth print-access-token`](https://cloud.google.com/sdk/gcloud/reference/auth/print-access-token): Display the current account's access token.
- [`gcloud auth revoke`](https://cloud.google.com/sdk/gcloud/reference/auth/revoke): Remove access credentials for an account.

### Projects


- [`gcloud projects describe`](https://cloud.google.com/sdk/gcloud/reference/projects/describe): Display metadata for a project (including its ID).
- [`gcloud projects add-iam-policy-binding`](https://cloud.google.com/sdk/gcloud/reference/projects/add-iam-policy-binding): Add an IAM policy binding to a specified project.

### IAM


- [`gcloud iam list-grantable-roles`](https://cloud.google.com/sdk/gcloud/reference/iam/list-grantable-roles): List IAM grantable roles for a resource.
- [`gcloud iam roles create`](https://cloud.google.com/sdk/gcloud/reference/iam/roles/create): Create a custom role for a project or org.
- [`gcloud iam service-accounts create`](https://cloud.google.com/sdk/gcloud/reference/iam/service-accounts/create): Create a service account for a project.
- [`gcloud iam service-accounts add-iam-policy-binding`](https://cloud.google.com/sdk/gcloud/reference/iam/service-accounts/add-iam-policy-binding): Add an IAM policy binding to a service account.
- [`gcloud iam service-accounts set-iam-policy-binding`](https://cloud.google.com/sdk/gcloud/reference/iam/service-accounts/set-iam-policy): Replace existing IAM policy binding.
- [`gcloud iam service-accounts keys list`](https://cloud.google.com/sdk/gcloud/reference/iam/service-accounts/keys/list): List a service account's keys.

### Docker & Google Kubernetes Engine (GKE)



- [`gcloud auth configure-docker`](https://cloud.google.com/sdk/gcloud/reference/auth/configure-docker): Register the gcloud CLI as a Docker credential helper.
- [`gcloud container clusters create`](https://cloud.google.com/sdk/gcloud/reference/container/clusters/create): Create a cluster to run GKE containers.
- [`gcloud container clusters list`](https://cloud.google.com/sdk/gcloud/reference/container/clusters/list): List clusters for running GKE containers.
- [`gcloud container clusters get-credentials`](https://cloud.google.com/sdk/gcloud/reference/container/clusters/get-credentials): Update `kubeconfig` to get `kubectl` to use a GKE cluster.
- [`gcloud container images list-tags`](https://cloud.google.com/sdk/gcloud/reference/container/images/list-tags): List tag and digest metadata for a container image.

### Virtual Machines & Compute Engine



- [`gcloud compute zones list`](https://cloud.google.com/sdk/gcloud/reference/compute/zones/list): List Compute Engine zones.
- [`gcloud compute instances create`](https://cloud.google.com/sdk/gcloud/reference/compute/instances/create): Create a VM instance.
- [`gcloud compute instances describe`](https://cloud.google.com/sdk/gcloud/reference/compute/instances/describe): Display a VM instance's details.
- [`gcloud compute instances list`](https://cloud.google.com/sdk/gcloud/reference/compute/instances/list): List all VM instances in a project.
- [`gcloud compute disks snapshot`](https://cloud.google.com/sdk/gcloud/reference/compute/disks/snapshot): Create snapshot of persistent disks.
- [`gcloud compute snapshots describe`](https://cloud.google.com/sdk/gcloud/reference/compute/snapshots/describe): Display a snapshot's details.
- [`gcloud compute snapshots delete`](https://cloud.google.com/sdk/gcloud/reference/compute/snapshots/delete): Delete a snapshot.
- [`gcloud compute ssh`](https://cloud.google.com/sdk/gcloud/reference/compute/ssh): Connect to a VM instance by using SSH.

### Serverless & App Engine



- [`gcloud app deploy`](https://cloud.google.com/sdk/gcloud/reference/app/deploy): Deploy your app's code and configuration to the App Engine server.
- [`gcloud app versions list`](https://cloud.google.com/sdk/gcloud/reference/app/versions/list): List all versions of all services deployed to the App Engine server.
- [`gcloud app browse`](https://cloud.google.com/sdk/gcloud/reference/app/browse): Open the current app in a web browser.
- [`gcloud app create`](https://cloud.google.com/sdk/gcloud/reference/app/create): Create an App Engine app within your current project.
- [`gcloud app logs read`](https://cloud.google.com/sdk/gcloud/reference/app/logs/read): Display the latest App Engine app logs.

### Miscellaneous


- [`gcloud kms decrypt`](https://cloud.google.com/sdk/gcloud/reference/kms/decrypt): Decrypt ciphertext (to a plaintext file) using a Cloud Key Management Service key.
- [`gcloud logging logs list`](https://cloud.google.com/sdk/gcloud/reference/logging/logs/list): List your project's logs.
- [`gcloud sql backups describe`](https://cloud.google.com/sdk/gcloud/reference/sql/backups/describe): Display info about a Cloud SQL instance backup.
- [`gcloud sql export sql`](https://cloud.google.com/sdk/gcloud/reference/sql/export/sql): Export data from a Cloud SQL instance to a SQL file.








