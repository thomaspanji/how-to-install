# gcloud CLI

## Installation
The steps written below are those who uses Linux OS. All steps are sourced from [here](https://cloud.google.com/sdk/docs/install).

1. Download Google Cloud SDK for Linux 64-bit (x86_64).

```bash
curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-sdk-379.0.0-linux-x86_64.tar.gz
```


2. Extract the contents to your home directory.
```bash
cd ~
tar -xf ~/Downloads/google-cloud-sdk-379.0.0-linux-x86.tar.gz
```

3. Use the install script to add the gcloud CLI tools to your `PATH`.

```bash
./google-cloud-sdk/install.sh
```
4. Answer `Y` when prompted to every question in the terminal. Then, open a new terminal so that the changes take effect.

5. Initialize the gcloud CLI by running `gcloud init`.

```bash
./google-cloud-sdk/bin/gcloud init
```

6. *(Optional)* Install additional components using the [component manager](https://cloud.google.com/sdk/docs/managing-components).

7. To display gcloud cheat sheet, run:

```bash
gcloud cheat-sheet
```
