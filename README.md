# SBOM for VS Code by SBOMApp! 

# “AI wrote the code – now audit what’s inside” 

SBOM MCP Server - SBOMApp MCP Server brings software supplychain security assistant inside VS Code. With a simple natural language prompt, developers can instantly generate SBOMs (SPDX/CycloneDX), scan for CVEs, Verify Licence Compliance, and get actionable remediation guidance.  

No switching tools, no manual scripts, everything happens right inside your editor, keeping you fast, secure, and focused.  

![alt text](https://res.cloudinary.com/instahippo/image/upload/v1760869330/sbom-label-1.png)

## Why teams choose SBOMApp MCP: 

Endtoend visibility: Build complete SBOMs (including transitive deps) from local workspaces or Git repos, then attach them to builds and releases. 

Actionable security: Run vulnerability scans, drill into CVE details, and get fix versions and upgrade paths. 

License clarity: Identify copyleft and other risky licenses early with auditfriendly summaries. 

Copilot + MCP native: Works naturally in Agent Mode, so prompts like “generate sbom”, “scan vulnerabilities”   

Frictionless onboarding: Start with a 7day free trial or connect your enterprise server using secure tokens stored by VS Code. 

Designed for securityminded engineering orgs: Whether you’re shipping regulated software, hardening your SDLC, or preparing for customer SBOM requests, SBOMApp MCP delivers the SBOM, CVE, and license insights your teams need 

# Absolute Privacy Guarantee!

We don’t store your code, your SBOMs, your dependencies, or any project data — ever. 
Only your email (for free trial) and API token are stored securely. Everything else stays completely on your machine.

# SBOMApp MCP Server

Connect to a remote SBOM MCP Server to perform software bill of materials analysis, vulnerability scanning, opensource license details and dependency management.

## Quick Start Guide

### Step 1: Install the Extension

1. Open VS Code
2. Go to Extensions (`Ctrl+Shift+X` or `Cmd+Shift+X` on Mac)
3. Search for **"SBOMApp MCP Server"**
4. Click **Install**

Or install directly from the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=iarm-mcp-server.sbom-mcp-server)


### Step 2: Free Trial - Get Started Instantly!

New users get a **FREE 90-day trial** with **100 Tokens** - no credit card required!

#### Automatic Trial Registration:
1. Install the extension
2. On first launch, you'll be prompted to start your free trial
3. Enter your email address
4. Your API key is automatically configured - you're ready to go!

**Simple steps to Activate Trial!**

**prerequisites** : Visual Studio Code should be Installed with langauage Models enabled.

- Click on the SBOM MCP status bar!

- Click on the start free trial option,

- Click on th start free trial popup,

- Enter your official email-id & click Enter,

- After sucessful Registration, you will get the trial activation notification!

- Reload the Window using the command "CTRL+SHIFT+P" or click "Command Palette" and Select "Developer:Reload Window" to Refresh the MCP Server!

#### Trial Features:
| Feature | Trial |
|---------|-------|
| Validity | 90 days |
| Token Requests | 100 tokens |
| SBOM Generation | yes |
| Vulnerability Scanning | yes |

#### Upgrade to Pro:
When your trial expires or tokens are exhausted, upgrade at: **https://payment.sbomapp.com** or **https://sbomapp.com**

#### Manual Configuration (Enterprise Users):
If you have a license key from your administrator:
1. Press `Ctrl+Shift+P` → **"SBOMApp: Configure Remote Server"**
2. Enter your **Server URL**: `https://mcp.sbomapp.com/mcp`
3. Enter your **API Key**

### Step 3: Test the Connection

1. Press `Ctrl+Shift+P` again
2. Type **"SBOMApp: Test Connection"** and press Enter
3. You should see a success message with available tools count

### Step 4: Restart the VS code.
Mandatory step! Once credentials and connections are tested, Kindly restart the VS Code.

### Step 5: Start Using "@sbomapp" in chat box

Once connected (green status bar shows ✓), you can ask GitHub Copilot:

> **Note:** Ensure your project is imported in VS Code before using SBOMApp MCP.
```
"@sbomapp/help"
"@sbomapp Generate an SBOM for my current project or 
Generate an SBOM for my current project".
"@sbomapp scan vulnerabilities" or "Check if lodash 4.17.0 has any security vulnerabilities" 
```
---

## Features

-  **Easy Configuration**: Simple setup wizard to connect to your SBOM MCP Server
-  **Secure Authentication**: Bearer token authentication with secure storage
-  **Connection Testing**: Verify your server connection before use
-  **Status Bar Indicator**: See connection status at a glance
-  **Tool Browser**: View all available SBOM analysis tools
-  **Direct Tool**: Say "@sbomapp Generate SBOM for my current project" in chat - it just works!

## Commands

| Command | Description |
|---------|-------------|
| `SBOMApp: Start Free Trial` | Register for a free 7-day trial |
| `SBOMApp: Check Trial Status` | View remaining tokens and expiry |
| `SBOMApp: Check Token Usage` | View detailed Token usage statistics |
| `SBOMApp: Configure Remote Server` | Set up server URL and API key |
| `SBOMApp: Test Connection` | Verify connection to the server |
| `SBOMApp: Show Available Tools` | Browse available SBOM analysis tools |
| `SBOMApp: Disconnect` | Disconnect from the server |

## Configuration

This extension provides the following settings:

| Setting | Description | Default |
|---------|-------------|---------|
| `sbomRemoteMcp.serverUrl` | URL of the remote SBOM MCP Server | (empty) |
| `sbomRemoteMcp.apiKey` | API key for authentication | (empty) |
| `sbomRemoteMcp.autoConnect` | Auto-connect on VS Code startup | `true` |
| `sbomRemoteMcp.showStatusBar` | Show status in status bar | `true` |

## Available Tools

Once connected, you can use these SBOM analysis tools with GitHub Copilot:

| Tool | Description |
|------|-------------|
| `sbomapp_generateSbomFromWorkspace` | Generate SBOM, scan vulnerabilities, analyze dependencies, and check licenses for your **current project** |
| `generate_sbom` | Generate a complete SBOM with vulnerability report for your project |
| `scan_vulnerabilities` | Scan your project for security vulnerabilities with CVE details |
| `analyze_dependencies` | Analyze all dependencies — types, licenses, and risk assessment |

> **Tip:** Just type "generate sbom", "scan vulnerabilities", or "analyze dependencies" in Copilot chat — the extension **automatically** analyzes your current project!

## Example Copilot Prompts after SBOM and vulnerabilities Generation 

Try asking Copilot these questions:

- "Fix the above Identified vulnerabilities"
- "Replace component_1 with suitable secure component"

## Requirements

- VS Code 1.106 or higher
- Access to a running SBOM MCP Server
- Valid API key for authentication

## Getting an API Key

### Option 1: Free Trial (Recommended for Individual Users)
- Start the extension and follow the trial registration prompt
- Or run command: `SBOMApp: Start Free Trial`
- **Trial includes**: 90 days, 100 Tokens

### Option 2: Purchase Pro License
- Visit **https://payment.sbomapp.com** or **https://sbomapp.com** to purchase
- Get Tokens and advanced features
- API key delivered instantly via email

### Option 3: Enterprise License
- Contact your SBOM MCP Server administrator
- Email: **sbomappsupport@iarminfo.com**

## Troubleshooting

### Connection Failed
- Verify the server URL is correct (should end with `/mcp`)
- Check that the server is running and accessible
- Ensure your API key is valid and not expired
- Check if firewall allows the connection

### Tools Not Working
- Make sure the connection is established (green ✓ in status bar)
- Check VS Code MCP settings are configured correctly
- Try disconnecting and reconnecting
- Restart VS Code if issues persist

### Status Bar Not Showing
- Check that `sbomRemoteMcp.showStatusBar` is enabled in settings
- Try reloading VS Code (`Ctrl+Shift+P` → "Reload Window")

### Check Token Usage Status
- Click on the status bar "SBOM MCP" → Select "Check token Usage"
- View detailed usage statistics in the output panel

### Check Trial Status
- Click on the status bar "SBOM MCP" → Select "Check Trial Status"
- View remaining tokens, days left, and upgrade options
- Status bar shows trial info: `✓ SBOM MCP [Trial: 450]`

### Trial Expired or Tokens Exhausted
- Status bar shows: ` SBOM MCP [Trial Expired]`
- Click "Upgrade Now" in the popup to purchase Pro license
- Or run command: `SBOMApp: Configure Remote Server` to enter a new API key
- Upgrade at: **https://payment.sbomapp.com** or **https://sbomapp.com**

### Authentication Errors
- Verify your API key is correct
- Ensure the API key has proper permissions
- Contact your administrator if the key was recently rotated

## Privacy & Security

- API keys are stored in VS Code's secure storage
- All communication uses HTTPS (when configured)
- No data is sent to third parties
- Credentials are never logged or exported


## Support

- 📧 Email: sbomappsupport@iarminfo.com
