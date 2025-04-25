## API Gateway Deployment via NetOrca

In this example, we focus on the deployment of API Gateway services, leveraging a JSON schema to ensure accuracy and reliability.

### Service Overview
- **Service**: API Gateway Deployment
- **Platform**: API Gateway

This service allows the deployment of API endpoints with features like authentication, rate limiting, and CORS support.

### Directory Structure
```
api_gateway/
├── customer_request_example/      # Example request configurations
│   └── application1.yaml          # Full-featured Customer configuration example
├── deployment/                    # Deployment playbooks and templates
│   ├── api_gateway_deploy.yaml    # Main deployment playbook
│   └── as3_template.j2            # F5 AS3 template
├── service_owner_schema/          # Schema definitions
│   └── api_gateway_schema.json    # JSON schema defining the service structure
└── README.md                      # This documentation
```

### Schema Details
The schema ensures each deployment includes essential metadata and configuration details.

#### Required Fields
| Field | Type | Description |
|-------|------|-------------|
| `name` | string | Name of the API endpoint with environment suffix (e.g., "api-service-prod") |
| `base_path` | string | API endpoint path (e.g., "/api/users") |
| `target_url` | string | Backend service URL (e.g., "https://internal-service:8080") |

#### Optional Fields
| Field | Type | Description |
|-------|------|-------------|
| `methods` | array | Allowed HTTP methods (default: ["GET", "POST", "PUT", "DELETE"]) |
| `rate_limit` | object | Request rate limiting configuration |
| `requests_per_minute` | integer | Maximum requests allowed per minute |
| `burst_size` | integer | Maximum requests allowed in a burst |
| `authentication` | string | Authentication method ("none", "jwt", "api_key", "oauth2") |
| `cors` | object | Cross-Origin Resource Sharing settings |
| `enabled` | boolean | Enable/disable CORS (default: false) |
| `allowed_origins` | array | List of allowed origins |
| `allowed_methods` | array | List of allowed HTTP methods |
| `allowed_headers` | array | List of allowed request headers |

### Example Deployment Configuration

#### Simple Configuration (Required Fields Only)
```yaml
API_GATEWAY:
  - name: simple-api-prod
    base_path: /api/simple
    target_url: https://internal-service:8080
```

#### Comprehensive Configuration (All Features)
```yaml
API_GATEWAY:
  - name: user-service-prod
    base_path: /api/users
    target_url: https://internal-user-service:8443
    methods:
      - GET
      - POST
      - PUT
      - DELETE
    rate_limit:
      requests_per_minute: 1000
      burst_size: 100
    authentication: jwt
    cors:
      enabled: true
      allowed_origins:
        - https://app.example.com
      allowed_methods:
        - GET
        - POST
        - PUT
        - DELETE
        - OPTIONS
      allowed_headers:
        - Content-Type
        - Authorization
```

### Deployment Process
1. The configuration is defined in a YAML file
2. NetOrca validates the configuration against the schema
3. The API Gateway service is deployed with the specified settings
4. The API endpoint becomes accessible through the configured base path 