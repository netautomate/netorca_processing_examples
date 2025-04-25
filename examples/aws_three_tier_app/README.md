## Three-Tier Application Deployment via NetOrca

In this example, we focus on the deployment of a Three-Tier Application in AWS, leveraging a JSON schema to ensure accuracy and reliability.

### Service Overview
- **Service**: Three-Tier Application Deployment
- **Platform**: AWS (Amazon Web Services)

This service allows the deployment of a three-tier application architecture (web, application, and database tiers) in AWS, using a consistent structure defined by a JSON schema.

### Schema Details
The schema ensures each deployment includes essential metadata and configuration details.

#### Required Fields
| Field | Type | Description |
|-------|------|-------------|
| `name` | string | Name of the three-tier application. Must start with a letter and be up to 60 characters. |
| `image` | string | Identifier for the application image (virtual machine). |
| `description` | string | Short description of the application. |
| `size` | string | Size of the application instance. Options: small, medium, large. |
| `owner` | string | Owner of the application deployment. |
| `environment` | string | Deployment environment. Options: prod, uat, staging, dev. |

### Example Deployment Configuration
Here's an example YAML configuration for deploying a three-tier application:

```yaml
name: my-app
image: ami-1234567890abcdef
description: A sample three-tier application deployed via NetOrca.
size: medium
owner: john.doe
environment: prod
```