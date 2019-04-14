# mini-hadoop-vm

This project focused on building VM (.ova file) for Hadoop sandbox just like Google Cloud Platform (GCP) Single Node Terminal.

## Step 1: Preparation

1. Download Ubuntu Mini https://help.ubuntu.com/community/Installation/MinimalCD
2. Download Virtualbox https://www.virtualbox.org/wiki/Downloads

## Step 2: Setting

1. Install Virtualbox
2. Setup for Linux Ubuntu with requirement specification: HDD 32GB and RAM 8GB
3. Start VM
4. Mount Ubuntu Mini
5. Setup Ubuntu Mini until ready to use, requirement additional software:  OpenSSH and Basic Ubuntu Server
6. Install Java
   - `sudo apt-get install default-jdk`
7. Customize your Terminal for fancy looking
   - Edit `~/.bashrc`
     - `sudo nano ~/.bashrc`
   - Change 
     - From
       - `#force_color_prompt=yes` 
     - To 
       - `force_color_prompt=yes`
   - Save
   - Re-run
     - `source ~/.bashrc`
8. Download and extract Hadoop
   - Download
     - `wget https://dist.apache.org/repos/dist/release/hadoop/common/hadoop-3.1.2/hadoop-3.1.2.tar.gz`
   - Extract
     - `tar -xzvf hadoop-3.1.2.tar.gz` 
   - Move
     - `sudo mv hadoop-3.1.2 /usr/local/hadoop`
9. Configure Java Link
   - Edit `hadoop-env.sh`
     - `sudo nano /usr/local/hadoop/etc/hadoop/hadoop-env.sh`
   - Change 
     - From
       - `#export JAVA_HOME=${JAVA_HOME}`
     - To 
       - `export JAVA_HOME=$(readlink -f /usr/bin/java | sed "s:bin/java::")`
   - Save
10. Test Hadoop `/usr/local/hadoop/bin/hadoop`
