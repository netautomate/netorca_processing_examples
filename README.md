# NetOrca Processing Examples

Welcome! 👋 This repository contains practical examples to help **Service Owner teams** quickly automate service requests using **NetOrca**.

## 📂 What You'll Find in This Repository

This repository is structured into clear sections to help you easily understand and implement NetOrca automations:

- **[Basics](./basics/)**:  
  Fundamental, easy-to-follow examples demonstrating core automation concepts. Ideal for teams getting started with NetOrca for the first time.

- **[Examples](./examples/)**:  
  Real-world use cases illustrating how NetOrca can be leveraged for specific standalone scenarios like:
  - **F5 BIG-IP**: GTM(DNS)/LTM deployments, WAF deployments and tuning
  - **Palo Alto Firewalls**: policy deployments and management
  - **ServiceNow**: integrating standard change records

  It also covers more advanced and complex scenarios combining multiple devices and services, such as:
  - **Three-tier Application Deployment** – combining AWS EC2, AWS ALB, and ServiceNow Standard Change Record, all orchestrated, automated, and tracked through NetOrca.

The repository will continuously grow with additional use cases, making it easier to see how NetOrca can streamline your infrastructure automation workflows.

## 🌟 What is NetOrca?

**NetOrca** simplifies how infrastructure and network teams deliver services—like firewalls, load balancers, DNS records, and more—to application teams within your organization.

With NetOrca:

- **Service Owners** define reusable services.
- **Consumers** easily request these services.
- NetOrca manages approvals, tracking, and integrates seamlessly with your existing automation tools (Ansible, Terraform, etc.).

**In short:** NetOrca makes infrastructure self-service, fast, and reliable.

![Placeholder: NetOrca Workflow](images/netorca_overview.png)  
*Suggested diagram: Consumers requesting services through NetOrca, with Service Owner automation deploying changes.*

## ✅ Overview of Automation Workflow

When teams request services through NetOrca, each request is represented as a **Service Item**.

Each **Service Item** can have multiple associated **Change Instances**, representing specific actions such as:

- **CREATE** – Initial creation of the service
- **MODIFY** – Updates or changes to existing services
- **DELETE** – Removal of services

### 📌 Change Instance Lifecycle

Each **Change Instance** moves through these states:

- **PENDING** – Automatically set after initial JSON schema validation (defined in your service definition).
- **APPROVED** – Set after successful second-level validation (e.g., business logic checks, resource availability, conflict checks).
- **REJECTED** – Set if second-level validation fails.

Approved Change Instances move forward to deployment and can then become:

- **COMPLETED** – Successfully deployed.
- **ERRORED** – Deployment failed, requires investigation or retry.

### 🚦 Typical Workflow Phases

Automation typically involves two clear phases:

#### 1. **Validation Phase**:
- Process **PENDING** Change Instances.
- Perform detailed validation checks.
- Mark each Change Instance as **APPROVED** or **REJECTED**.

#### 2. **Deployment Phase**:
- Deploy **APPROVED** Change Instances.
- Update the Change Instance state to **COMPLETED** upon successful deployment, or **ERRORED** if deployment fails.

Each Service Item can undergo this lifecycle multiple times as consumers request further modifications or eventual removal.

---

## 📖 Further Reading

- [NetOrca Official Documentation](https://docs.netorca.io)

Happy automating! 🚀
