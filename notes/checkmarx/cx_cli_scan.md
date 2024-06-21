To obtain the API key for Checkmarx One CLI authentication (`cx auth --key YOUR_API_KEY`), you need to generate the API key from your Checkmarx One account. Here’s how you can do that:

### Step-by-Step Guide to Generate API Key

1. **Log in to Checkmarx One**:
   - Open your web browser and navigate to your Checkmarx One login page.
   - Enter your credentials to log in.

2. **Navigate to API Key Management**:
   - Once logged in, look for the user profile menu. This is typically found in the top-right corner of the Checkmarx One interface.
   - Click on your user profile and look for an option like "API Keys" or "API Management". The exact navigation might differ based on the Checkmarx One version you are using.

3. **Generate a New API Key**:
   - In the API key management section, there should be an option to generate a new API key. Click on this option.
   - Provide a name or description for the API key to identify its purpose.
   - Set the required permissions for the API key. Ensure that it has sufficient permissions for the operations you intend to perform with the CLI.

4. **Copy the API Key**:
   - Once the API key is generated, copy it. Ensure you store it in a secure location as it will be used to authenticate your CLI.

### Using the API Key with Checkmarx One CLI

1. **Authenticate the CLI**:
   - Open your terminal on the Ubuntu system where you have Checkmarx One CLI installed.
   - Use the following command to authenticate using the API key you generated:
     ```bash
     cx auth --key YOUR_API_KEY
     ```
   - Replace `YOUR_API_KEY` with the actual API key you copied from the Checkmarx One web interface.

### Example Workflow

1. **Open Terminal**:
   ```bash
   cd /path/to/your/project
   ```

2. **Authenticate with API Key**:
   ```bash
   cx auth --key YOUR_ACTUAL_API_KEY
   ```

3. **Run a Scan**:
   ```bash
   cx scan create --project-name "Your Project Name" --source .
   ```

### Troubleshooting and Additional Help

- **Checkmarx Documentation**: Refer to the [Checkmarx One documentation](https://checkmarx.com/documentation) for detailed steps and screenshots.
- **Support**: If you have trouble finding the API key management section or generating the key, contact Checkmarx support for assistance.

By following these steps, you should be able to generate an API key from your Checkmarx One account and use it to authenticate the CLI for running scans on your project.