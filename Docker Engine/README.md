# Docker Engine on Ubuntu

The steps are completely sourced from [Docker documentation](https://docs.docker.com/engine/install/ubuntu/#installation-methods).

## Installation

The docker installation will be using the repository.

### Set up the repository

1. Update the `apt` package index and install packages to allow `apt` to use a repository over HTTPS.

    ```bash
    sudo apt-get update

    sudo apt-get install \
        ca-certificates \
        curl \
        gnupg \
        lsb-release
    ```

2. Add Docker's official GPG key.

    ```bash
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    ```

3. Use the following command to set up the stable repository.

    ```bash
    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    ```

### Install Docker Engine

1. Update the `apt` package index, and install the latest version of Docker Engine and containerd.

    ```bash
    sudo apt-get update

    sudo apt-get install docker-ce docker-ce-cli containerd.io
    ```

2. Verify that Docker Engine is installed correctly by running the `hello-world` image.

    ```bash
    sudo docker run hello-world
    ```

    This command downloads a test image and runs it in a container. When the container runs, it prints a message and exits.


## Post-installation for Linux

The Docker daemon binds to a Unix socket instead of a TCP port. By default that Unix socket is owned by the user `root` and other users can only access it using `sudo`. The Docker daemon always runs as the root user. To run Docker without command `sudo`, create a group and add a user.

1. Create the `docker` group.

    ```bash
    sudo groupadd docker
    ```

2. Add your user to the `docker` group.

    ```bash
    sudo usermod -aG docker $USER
    ```

3. Log out and log back in so that your group membership is re-evaluated. On Linux, you can run the following command to activate the changes to groups.

    ```bash
    newgrp docker
    ```

4. Verify that you can run `docker` without `sudo`.

    ```bash
    docker run hello-world
    ```

## Enable and disable Docker to start on boot

On Debian and Ubuntu, the Docker service is configured to start on boot by default. To automatically start Docker and Containerd on boot for other distros, use the following command.

```bash
sudo systemctl enable docker.service
sudo systemctl eable containerd.service
```

To disable this behaviour,

```bash
sudo systemctl disable docker.service
sudo systemctl disable containerd.service
```
