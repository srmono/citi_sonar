Here's a guide to installing, starting, and stopping SonarQube, as well as setting up the required environment variables on Ubuntu:

## Installation:

### Step 1: Prerequisites
- Ensure Java Development Kit (JDK) 11 or later is installed on your system. You can install it using:
  ```
  sudo apt update
  sudo apt install default-jdk
  ```

### Step 2: Download and Extract SonarQube
- Download the latest version of SonarQube from the [official website](https://www.sonarqube.org/downloads/).
- Extract the downloaded archive to your desired installation directory, for example:
  ```
  sudo tar -xzf sonarqube-<version>.zip -C /opt
  ```

### Step 3: Configure SonarQube
- Open the `sonarqube-<version>/conf/sonar.properties` file and configure the server settings as needed, such as database connection details.
  ```
  sudo nano /opt/sonarqube-<version>/conf/sonar.properties
  ```

## Starting SonarQube:

### Step 1: Start SonarQube Server
- Navigate to the SonarQube installation directory:
  ```
  cd /opt/sonarqube-<version>/bin/linux-x86-64
  ```
- Start the SonarQube server:
  ```
  sudo ./sonar.sh start
  ```

## Stopping SonarQube:

### Step 1: Stop SonarQube Server
- Navigate to the SonarQube installation directory:
  ```
  cd /opt/sonarqube-<version>/bin/linux-x86-64
  ```
- Stop the SonarQube server:
  ```
  sudo ./sonar.sh stop
  ```

## Setting up Environment Variables:

### Step 1: Define Environment Variables
- Open the `.bashrc` file using a text editor:
  ```
  nano ~/.bashrc
  ```
- Add the following lines at the end of the file to define SonarQube related environment variables:
  ```
  export SONAR_HOME=/opt/sonarqube-<version>
  export PATH=$PATH:$SONAR_HOME/bin/linux-x86-64
  ```

### Step 2: Reload Bash Profile
- Reload the `.bashrc` file to apply the changes:
  ```
  source ~/.bashrc
  ```

### Step 3: Verify Environment Variables
- Verify that the environment variables are set correctly by running:
  ```
  echo $SONAR_HOME
  echo $PATH
  ```

Now, you have installed SonarQube, started and stopped the server, and set up the required environment variables on Ubuntu. You can access the SonarQube web interface by navigating to `http://localhost:9000` in your web browser.