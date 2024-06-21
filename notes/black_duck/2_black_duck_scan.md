Step-by-step guide on how to use the Black Duck Scan Docker container to scan your project source code.

### Prerequisites
1. **Docker Installed**: Ensure you have Docker installed on your machine.
2. **Black Duck Account**: You need an account with Black Duck to get access to the Black Duck server and obtain necessary credentials.

### Step-by-Step Guide

#### Step 1: Pull the Black Duck Scan Docker Image
First, pull the Black Duck Scan Docker image from Docker Hub:
```bash
docker pull blackducksoftware/blackduck-scan
```

#### Step 2: Prepare Your Project for Scanning
Ensure your project source code is in a directory on your local machine. For this example, let's assume your project is located at `/path/to/your/project`.

#### Step 3: Set Up Black Duck Credentials
You'll need the following information to connect to the Black Duck server:
- **BLACKDUCK_URL**: The URL of your Black Duck server.
- **BLACKDUCK_API_TOKEN**: The API token for authenticating with the Black Duck server.
- **BLACKDUCK_TRUST_CERT**: Whether to trust the Black Duck server's certificate (true/false).

Set these values in your environment or pass them directly to the Docker command.

#### Step 4: Run the Black Duck Scan
Run the Black Duck Scan Docker container with the appropriate environment variables and volume mappings. Here's the command:

```bash
docker run \
  --rm \
  -v /path/to/your/project:/scan \
  -e BLACKDUCK_URL="https://your.blackduck.server" \
  -e BLACKDUCK_API_TOKEN="your_api_token" \
  -e BLACKDUCK_TRUST_CERT=true \
  blackducksoftware/blackduck-scan
```

### Explanation of Command
- **--rm**: Automatically remove the container when it exits.
- **-v /path/to/your/project:/scan**: Mount the project directory into the container at `/scan`.
- **-e BLACKDUCK_URL**: Set the Black Duck server URL.
- **-e BLACKDUCK_API_TOKEN**: Set the API token for authentication.
- **-e BLACKDUCK_TRUST_CERT**: Trust the server's SSL certificate.

### Step 5: Review Scan Results
After the scan completes, the results will be available in the Black Duck server's web interface. Log in to your Black Duck server to review the findings related to vulnerabilities, license compliance, and code quality issues.

### Troubleshooting
- **Connection Issues**: Ensure the Black Duck server URL and API token are correct and the server is reachable.
- **SSL Certificate Issues**: If you encounter SSL certificate issues, ensure that `BLACKDUCK_TRUST_CERT` is set to `true`.
- **Permission Issues**: Make sure you have appropriate permissions to run Docker commands and access the project directory.

### Additional Configuration
If you need to pass additional configuration options to the scan, refer to the Black Duck documentation for more details on environment variables and scan options.

By following these steps, you should be able to successfully scan your project using the Black Duck Scan Docker container. If you encounter any specific issues or have additional questions, feel free to ask!