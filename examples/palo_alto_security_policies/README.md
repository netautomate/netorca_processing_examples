## Palo Alto Security Policies Deployment via NetOrca

In this example, we focus on the deployment of Security Policies for Palo Alto devices, leveraging a YAML schema to ensure accuracy and reliability.

### Service Overview
- **Service**: Security Policy Deployment
- **Platform**: Palo Alto Networks

This service allows the deployment of security policies for Palo Alto devices, using a consistent structure defined by a YAML schema.

### Schema Details
The schema ensures each deployment includes essential metadata and configuration details.

#### Required Fields
| Field | Type | Description |
|-------|------|-------------|
| `name` | string | Name of the security policy. |
| `action` | string | Action to take on the traffic. Options: allow, deny. |
| `source_zone` | string | Source zone for the traffic. |
| `destination_zone` | string | Destination zone for the traffic. |
| `source_address` | list | List of source IP addresses or networks. |
| `destination_address` | list | List of destination IP addresses or networks. |
| `application` | list | List of applications to match. |
| `service` | list | List of services to match. |

We prepared two ways of deploying security policies, imperative and declarative. Palo Alto does not support declarative deployments natively, but we try to mimic it by deploying all security policies together.

### Example Deployment Configuration
Here's an example YAML configuration for deploying a security policy:

```yaml
SECURITY_POLICY:
  - name: allow-web-traffic
    action: allow
    source_zone: Trust
    destination_zone: Untrust
    source_address:
      - 10.1.1.0/24
    destination_address:
      - any
    application:
      - web-browsing
      - ssl
    service:
      - application-default
```