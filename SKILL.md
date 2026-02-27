# Skills — SBOMApp MCP Server

> What the SBOMApp MCP Server can do for AI assistants and their users.

---

## Overview

**SBOMApp** is a remote MCP server that provides Software Bill of Materials (SBOM) generation, vulnerability scanning, and dependency analysis capabilities to AI assistants. It enables any MCP-compatible AI client to analyze software projects for security risks, license compliance, and dependency health — directly from the conversation.

**Server URL:** `https://mcp.sbomapp.com/mcp`
**Protocol:** MCP over Streamable HTTP (JSON-RPC 2.0)

---

## Tools

### 1. `generate_sbom`

**Generate a complete Software Bill of Materials from a Git repository.**

Creates a comprehensive software inventory by cloning a repository, identifying all direct and transitive dependencies, scanning for known vulnerabilities (CVEs), and checking license information.

**What it returns:**
- Full CycloneDX SBOM with all components
- Component count (direct + transitive dependencies)
- Detected languages and package managers
- Vulnerability summary by severity (Critical / High / Medium / Low)
- Count of affected components
- Persistent storage of the SBOM for later retrieval

**Supported inputs:**
- Public Git URLs (`https://github.com/owner/repo`)
- Private Git URLs (with configured access)
- Custom branch, project name, and version

**Example prompts a user might ask:**
- *"Generate an SBOM for https://github.com/expressjs/express"*
- *"Analyze the security of this repo: https://github.com/fastify/fastify"*
- *"Create a software bill of materials for my GitHub project"*

---

### 2. `scan_vulnerabilities`

**Scan an existing SBOM for security vulnerabilities.**

Takes an SBOM file (CycloneDX JSON or XML) and scans all listed components against known vulnerability databases, returning CVE details with severity ratings and remediation guidance.

**What it returns:**
- Vulnerability count by severity level
- List of vulnerable components with CVE IDs
- Severity classification for each vulnerability
- Description and remediation guidance per CVE

**Example prompts:**
- *"Scan this SBOM for vulnerabilities"*
- *"Are there any critical CVEs in my project's dependencies?"*
- *"Check my SBOM file for security issues"*

---

### 3. `analyze_dependencies`

**Analyze all dependencies in a project from a Git URL.**

Provides a detailed breakdown of a project's dependency tree, including license distribution, dependency types, direct vs. transitive dependency counts, and a vulnerability overview.

**What it returns:**
- Total dependency count (direct + transitive)
- License distribution (top licenses used)
- Dependency type breakdown (library, framework, etc.)
- Vulnerability summary across all dependencies
- Top 10 dependencies with version and license info

**Example prompts:**
- *"Analyze the dependencies of https://github.com/pallets/flask"*
- *"What licenses are used in this project's dependencies?"*
- *"Give me a dependency breakdown for this repo"*

---

### 4. `generate_sbom_from_local`

**Generate an SBOM from local manifest files — works from any IDE without a Git URL.**

The AI agent reads the user's local dependency/manifest files and sends their contents to this tool. This enables SBOM generation for projects that aren't on GitHub/GitLab, including private local projects.

**What it returns:**
- Same comprehensive output as `generate_sbom`
- Full CycloneDX SBOM, vulnerability scan, component summary
- Persistent storage of results

**Supported manifest files:**

| Ecosystem | Files |
|---|---|
| **Node.js** | `package.json`, `package-lock.json`, `yarn.lock`, `pnpm-lock.yaml` |
| **Python** | `requirements.txt`, `Pipfile`, `pyproject.toml`, `poetry.lock`, `setup.py` |
| **Java** | `pom.xml`, `build.gradle`, `build.gradle.kts` |
| **Go** | `go.mod`, `go.sum` |
| **Rust** | `Cargo.toml`, `Cargo.lock` |
| **PHP** | `composer.json`, `composer.lock` |
| **Ruby** | `Gemfile`, `Gemfile.lock` |
| **.NET** | `.csproj`, `packages.config`, `nuget.config` |
| **Swift** | `Package.swift`, `Package.resolved` |
| **Dart** | `pubspec.yaml`, `pubspec.lock` |
| **Elixir** | `mix.exs`, `mix.lock` |

**Example prompts:**
- *"Generate an SBOM for my current project"*
- *"Scan my local project for vulnerabilities"*
- *"What dependencies does my workspace have?"*

---

## Key Capabilities

### Multi-Language Support
Supports 15+ programming language ecosystems including JavaScript/TypeScript, Python, Java, Go, Rust, C#, PHP, Ruby, Swift, Dart, and more.

### Vulnerability Detection
Scans against public CVE databases (NVD, OSV, GitHub Advisory Database) and classifies vulnerabilities by severity: Critical, High, Medium, Low.

### License Compliance
Identifies and reports the license of every dependency, enabling compliance checks against organizational policies.

### Persistent SBOM Storage
Generated SBOMs are stored and accessible from the SBOMApp dashboard for historical tracking, comparison, and reporting.

### Security by Design
- Local file path access is blocked on the remote server
- All inputs are validated and sanitized
- API key authentication with hashed storage
- HTTPS encryption for all communication
- Rate limiting and audit logging

---

## Authentication

All tools require a valid API key passed as a Bearer token in the `Authorization` header.

```
Authorization: Bearer sbom_<your_api_key>
```

API keys can be obtained from [https://sbomapp.com](https://sbomapp.com). Trial keys with limited tokens are also available.

---

## Supported Clients

| Client | Transport | Status |
|---|---|---|
| VS Code (SBOMApp Extension) | Remote MCP | Supported |
| Cursor | SSE / Streamable HTTP | Supported |
| Claude Desktop | Streamable HTTP | Supported |
| Claude Code | HTTP | Supported |
| Any MCP-compatible client | Streamable HTTP | Supported |

---

## Example Conversation Flow

**User:** *"Generate an SBOM for https://github.com/expressjs/express and tell me if there are any vulnerabilities."*

**AI Assistant** (using `generate_sbom` tool):
1. Clones the repository
2. Detects `package.json` (Node.js ecosystem)
3. Resolves all direct and transitive dependencies
4. Scans every component against vulnerability databases
5. Returns a structured report with component counts, vulnerability summary, and affected packages

---

## Limitations

- Git URL sources only for `generate_sbom` and `analyze_dependencies` (local paths blocked for security)
- `generate_sbom_from_local` requires the AI agent to read and send manifest file contents
- SBOM generation time depends on project size and dependency count
- Rate limits apply per API key
