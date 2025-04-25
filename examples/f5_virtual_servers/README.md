## F5 Virtual Servers Deployment via NetOrca

In this example, we focus on the deployment of F5 Virtual Servers with pool members, leveraging a YAML schema to ensure accuracy and reliability.

### Service Overview
- **Service**: Virtual Server Deployment with Pool Members
- **Platform**: F5 Networks

This service allows the deployment of Virtual Servers with associated pools and pool members for F5 devices, using a consistent structure defined by a YAML schema.

### Schema Details
The schema ensures each deployment includes essential metadata and configuration details.

#### Required Fields
| Field | Type | Description |
|-------|------|-------------|
| `name` | string | Name of the Virtual Server. |
| `ip` | string | IP address of the Virtual Server. |
| `port` | integer | Port number for the Virtual Server. |
| `pool_members` | array | List of pool member IP addresses. |

### Example Deployment Configuration
Here's an example YAML configuration for deploying a Virtual Server with pool members:

```yaml
VIRTUAL_SERVER:
  - name: my-virtual-server
    ip: 10.1.1.1
    port: 80
    pool_members:
      - 10.1.2.1
      - 10.1.2.2
      - 10.1.2.3
```

### Deployment Process
1. The configuration is defined in a YAML file
2. An AS3 template processes the configuration
3. The AS3 declaration is deployed to the F5 device
4. The Virtual Server and pool members are created automatically