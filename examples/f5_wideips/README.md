## F5 WideIP Deployment via NetOrca

In this example, we focus on the deployment of F5 WideIP objects, leveraging a YAML schema to ensure accuracy and reliability.

### Service Overview
- **Service**: WideIP Deployment
- **Platform**: F5 Networks

This service allows the deployment of WideIP objects for F5 devices, using a consistent structure defined by a YAML schema.

### Schema Details
The schema ensures each deployment includes essential metadata and configuration details.

#### Required Fields
| Field | Type | Description |
|-------|------|-------------|
| `name` | string | Name of the WideIP object. |
| `dc1_server` | string | Address of the DC1 Virtual Server. |
| `dc2_server` | string | Address of the DC2 Virtual Server. |
| `dc1_ratio` | integer | Load balancing priority/ratio of the DC1 Virtual Server. |
| `dc2_ratio` | integer | Load balancing priority/ratio of the DC2 Virtual Server. |

### Example Deployment Configuration
Here's an example YAML configuration for deploying a WideIP:

```yaml
WIDEIP:
  - name: my-wideip
    dc1_server: 10.1.1.1
    dc2_server: 10.1.1.2
    dc1_ratio: 1
    dc2_ratio: 1
``` 