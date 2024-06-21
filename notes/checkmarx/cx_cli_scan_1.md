Using the Checkmarx One CLI to scan your project involves a few steps: configuring your Checkmarx One environment, running the scan, and reviewing the results. Here’s how to do it:

### Step 1: Set Up Your Checkmarx One Environment

1. **Install Checkmarx One CLI**:
   Since you have already installed the CLI on your Ubuntu system, ensure it's properly installed by checking its version:
   ```bash
   cx version
   ```

2. **Authenticate the CLI**:
   You need to authenticate the CLI with your Checkmarx One account. This typically involves setting up API keys or tokens. The process can vary, so refer to the documentation provided by Checkmarx One or contact their support for the specific method used in your organization.

   Here’s an example of authenticating using an API key:
   ```bash
   cx auth --key YOUR_API_KEY
   ```

### Step 2: Configure Your Project

1. **Navigate to Your Project Directory**:
   ```bash
   cd /path/to/your/project
   ```

2. **Initialize the Project Configuration**:
   If required, you may need to initialize a configuration file for Checkmarx in your project directory:
   ```bash
   cx init
   ```

### Step 3: Run the Scan

To scan your project, use the following command:
```bash
cx scan create --project-name "Your Project Name" --source .
```

### Step 4: Monitor the Scan

Monitor the scan progress directly from the CLI:
```bash
cx scan status --scan-id SCAN_ID
```

### Step 5: Retrieve and Review the Results

Once the scan is complete, you can retrieve and review the results:

1. **Get Scan Results**:
   ```bash
   cx scan results --scan-id SCAN_ID --format json > results.json
   ```

2. **Review Results**:
   Open and review the `results.json` file to understand the vulnerabilities and issues identified in your project.

### Example Workflow

Here’s a complete example workflow:

1. **Navigate to Your Project Directory**:
   ```bash
   cd /path/to/your/project
   ```

2. **Authenticate the CLI** (if not already authenticated):
   ```bash
   cx auth --key YOUR_API_KEY
   ```

3. **Run the Scan**:
   ```bash
   cx scan create --project-name "Your Project Name" --source .
   ```

4. **Monitor the Scan**:
   ```bash
   cx scan status --scan-id SCAN_ID
   ```

5. **Retrieve and Save Results**:
   ```bash
   cx scan results --scan-id SCAN_ID --format json > results.json
   ```

6. **Open and Review the Results**:
   ```bash
   cat results.json
   ```

### Troubleshooting and Additional Help

- **Checkmarx Documentation**: Refer to the [official Checkmarx One CLI documentation](https://checkmarx.com/documentation) for detailed commands and options.
- 
- **Support**: Contact Checkmarx support for specific issues or questions related to your environment and configuration.

