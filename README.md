# how-to-install

This repository contains installation steps for the tools listed below.

List of tools:
- [Apache Spark](/Apache%20Spark/README.md)
- [Apache Kafka](/Apache%20Kafka/README.md)
- [Apache Airflow](/Apache%20Airflow/README.md)
- [gcloud](/gcloud/README.md)


The operating system which will be used for installing the tools is Linux OS, specifically Ubuntu-based version.

Environments:
1. Install Java
2. Virtual Environment

## Install Java
This tutorial contains steps to install Java and configure it in Linux.

1. Download Java Development Kit (JDK) from [here](https://www.oracle.com/java/technologies/downloads/).
2. Choose product that match your system requirement. For example, I choose the debian package.
![java-download-section](/img/java-download-section.png)
3. Save the file to your local machine.
4. Open a terminal, go to your download folder.
5. Install the debian package using command `sudo dpkg -i jdk-17_linux-x64_bin.deb`.
6. Check your java version using `java --version`.
7. Configure environment variables, using your preferred text editor. For example, I am using gedit, then type `sudo gedit /etc/environment`.
8. Make change in the file by giving information where the Java path is specified, `JAVA_HOME="/usr/lib/jvm/jdk-[your_version]` (to see the version, type `ls /usr/lib/jvm/`). Save the file.
9. Make final change by typing `source /etc/environment`.
