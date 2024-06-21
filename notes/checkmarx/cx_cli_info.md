Checkmarx One is the unified cloud platform that combines various Checkmarx security solutions. The CLI for Checkmarx One allows you to interact with the platform for tasks such as initiating scans, retrieving results, and managing projects.

Below are some common Checkmarx One CLI commands with examples to help you get started.

### 1. **Authenticate**

Before performing any operations, you need to authenticate with the Checkmarx One server.

```bash
cx auth login --username <your-username> --password <your-password> --tenant <your-tenant> --host <checkmarx-server-url>
```

### 2. **Create a New Project**

To create a new project on Checkmarx One:

```bash
cx projects create --name <project-name> --team <team-id> --repo-type <repository-type> --repo-url <repository-url> --repo-username <repo-username> --repo-password <repo-password>
```

### 3. **Initiate a Scan**

To start a new scan for an existing project:

```bash
cx scans create --project-id <project-id> --branch <branch-name> --preset <preset-id> --engine-configuration <engine-config-id>
```

### 4. **List Projects**

To list all projects:

```bash
cx projects list
```

### 5. **Get Scan Results**

To get the results of a specific scan:

```bash
cx scans results --scan-id <scan-id> --format <json/xml/html>
```

### 6. **Retrieve a Specific Project's Details**

To get detailed information about a specific project:

```bash
cx projects get --project-id <project-id>
```

### 7. **List Presets**

To list all available scan presets:

```bash
cx presets list
```

### 8. **List Scan Engines**

To list all available scan engines:

```bash
cx engines list
```

### Example Workflow

Here’s an example workflow that covers creating a project, initiating a scan, and retrieving the results.

1. **Authenticate:**

```bash
cx auth login --username user@example.com --password examplepassword --tenant exampletenant --host https://example.checkmarx.net
```

2. **Create a New Project:**

```bash
cx projects create --name MyProject --team Team123 --repo-type git --repo-url https://github.com/user/myproject.git --repo-username mygitusername --repo-password mygitpassword
```

3. **Initiate a Scan:**

First, you need to find the project ID for "MyProject":

```bash
cx projects list
```

Suppose the project ID is `12345`. Now, initiate a scan for the master branch:

```bash
cx scans create --project-id 12345 --branch master --preset High --engine-configuration Default
```

4. **List Scans to Get the Latest Scan ID:**

```bash
cx scans list --project-id 12345
```

Assume the latest scan ID is `67890`.

5. **Get Scan Results:**

```bash
cx scans results --scan-id 67890 --format json > scan_results.json
```

### Notes

- **Environment Variables:** Instead of passing credentials in commands, consider using environment variables for security.
- **Documentation:** Always refer to the official Checkmarx One CLI documentation for the most up-to-date and detailed information.
- **Help Command:** Use the `--help` flag with any command to get detailed usage information.

```bash
cx --help
```

This guide should help you get started with the Checkmarx One CLI for various common tasks. Make sure to customize the commands with your specific project details and credentials.