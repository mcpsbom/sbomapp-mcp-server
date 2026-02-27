# Privacy Policy

**SBOMApp MCP Server**

## 1. Introduction

This Privacy Policy describes how **SBOMApp** ("we," "us," or "our"), operated by **IARM Information Security**, collects, uses, stores, and protects information when you use the SBOMApp MCP Server ("Service") hosted at `https://mcp.sbomapp.com/mcp`.

By using the Service, you agree to the collection and use of information as described in this policy.

---

## 2. Information We Collect

### 2.1 Authentication Data

- **API Keys:** We issue and store hashed API keys used to authenticate requests. API keys are associated with your account and are never stored in plain text after initial generation.
- **Machine Identifiers:** For trial accounts, we collect a hashed machine identifier to enforce per-device trial limits. The raw machine ID is never stored.

### 2.2 Data You Submit for Processing

When you use the Service, you may submit the following data for analysis:

- **Git Repository URLs:** Public or private repository URLs provided for SBOM generation.
- **Project Metadata:** Project name, version, and branch information you provide.

### 2.3 Automatically Collected Data

- **Request Logs:** IP address, timestamp, request method, endpoint, and response status code for security monitoring and abuse prevention.
- **Usage Metrics:** Token consumption counts, tool invocation counts, and API call frequency (aggregated per API key).
- **Session Data:** Temporary session identifiers for maintaining MCP protocol connections. Sessions are ephemeral and not persisted long-term.

### 2.4 Data We Do NOT Collect

- We do **not** collect your source code beyond the manifest/dependency files explicitly submitted for analysis.
- We do **not** collect personal information such as name, email, or physical address through the MCP server endpoint.
- We do **not** use cookies or browser tracking technologies on the MCP server.
- We do **not** collect telemetry from your IDE or development environment.

---

## 3. How We Use Your Information

We use the collected information solely for the following purposes:

| Purpose | Data Used |
|---|---|
| **SBOM Generation** | Git URLs, manifest files, project metadata |
| **Vulnerability Scanning** | Generated SBOM data, dependency information |
| **Dependency Analysis** | Manifest files, project metadata |
| **Authentication & Authorization** | API keys, machine identifiers |
| **Rate Limiting & Abuse Prevention** | Request logs, usage metrics |
| **Service Improvement** | Aggregated, anonymized usage statistics |
| **Security Monitoring** | Request logs, IP addresses |

We do **not** use your data for advertising, profiling, or selling to third parties.

---

## 4. Data Storage and Retention

### 4.1 Storage Location

All API keys is stored on secured servers. Database access is restricted to authenticated services only.

### 4.2 SBOM Output Data

- No Output data stored in server side.

### 4.3 Retention Periods

| Data Type | Retention Period |
|---|---|
| Request/access logs | 90 days |
| API key records | Until key is revoked or account is deleted |
| Session data | Duration of session (ephemeral) |
| Trial usage records | 1 year after trial expiration |
| Manifest file contents | Processed in-memory; not persisted after SBOM generation |

---

## 5. Data Sharing and Third Parties

### 5.1 No Sale of Data

We do **not** sell, rent, or trade your data to any third party.

### 5.2 Third-Party Services

The Service may interact with the following external services during SBOM generation:

- **Public Vulnerability Databases:** We query public CVE databases (e.g., NVD, OSV, GitHub Advisory Database) to identify known vulnerabilities in your dependencies. Only package names and versions are sent — no source code.
- **Public Package Registries:** We may query public package registries (e.g., npm, PyPI, Maven Central) to resolve dependency metadata.
- **ClearlyDefined:** We may query the ClearlyDefined API to retrieve open-source license information for your dependencies.

---

## 6. Data Security

We implement the following security measures to protect your data:

- **Encryption in Transit:** All communication with the MCP server is over HTTPS/TLS.
- **API Key Hashing:** API keys are cryptographically hashed before storage.
- **Access Controls:** Database access is restricted to authorized services with role-based access control.
- **Input Validation:** All inputs are validated and sanitized to prevent injection attacks and unauthorized file access.
- **Rate Limiting:** API rate limits are enforced to prevent abuse.
- **Audit Logging:** All access is logged for security monitoring.

---

## 7. Changes to This Policy

We may update this Privacy Policy from time to time. Changes will be reflected by updating the "Last Updated" date at the top of this document. We encourage you to review this policy periodically. Continued use of the Service after changes constitutes acceptance of the updated policy.

---

## 8. Contact Us

If you have questions, concerns, or requests regarding this Privacy Policy or our data practices, please contact us:

- **Email:** sbomappsupport@iarminfo.com
- **Website:** [https://sbomapp.com](https://sbomapp.com)
- **GitHub:** [https://github.com/mcpsbom/sbomapp-mcp-server](https://github.com/mcpsbom/sbomapp-mcp-server)

---

*This Privacy Policy applies to the SBOMApp MCP Server operated by IARM Information Security.*
