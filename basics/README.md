# NetOrca Basics: Core Automation Patterns

This section contains foundational patterns and building blocks that demonstrate how to integrate with NetOrca as a Service Owner. These patterns serve as the basis for more complex examples.

## What's Inside?

This repository includes automation examples for two common approaches:

- **Declarative Automation**  
  For systems like F5 BIG-IP (AS3), where you send one complete configuration describing your desired end-state.

- **Imperative Automation**  
  For devices like Palo Alto firewalls, where changes are applied individually in incremental steps.

Additionally:

- **Validation Workflow**  
  Shows how you can easily add validation or approval steps before deployment.

All examples use clear Ansible playbooks and Terraform modules to quickly get you started.

## Directory Structure

- **ansible/**
  - `declarative_submission.yaml` - Template for declarative service automation
  - `imperative_submission.yaml` - Template for imperative service automation  
  - `validation.yaml` - Template for adding validation steps
  - `declaration.j2` - Jinja2 template for generating example declarations

- **terraform/**
  - `declarative/` - Terraform modules for declarative services
  - `imperative/` - Terraform modules for imperative services

## Key Concepts in NetOrca Integration
### Definitions
**Service**: A well defined piece of infrastructure that can be requested	by a Customer
**Service Item**: A single instance of a service as requested by a Consumer
**Change Instance**: A change ticket that has been spawned due to create/delete/modify actions associated with a Service Item

### Service Owner Flow
As a Service Owner, your integration with NetOrca typically involves these key steps:

1. **Schema Definition**  
   Define what your Service looks like using JSONSchema standard

2. **Validation**  
   Process PENDING Change Instanecs and validate business/technical rules

3. **Deployment**  
   Process APPROVED Change Instances and implement the changes


### NetOrca API Interaction
The included templates show the essential API interactions:
- **Getting Change Instances**  
  Retrieve all Changes made to new or existing Service Items

- **Getting Service Items**  
  Retrieve all current Service Instances (Customer requests) that match criteria

- **Run your automation**
  Service Items and Change Instances give you declarations which are translated to infrastructure config with Ansible, Terraform or any other script/tool.

- **Updating Change Instances**  
  Report back on processed requests (rejected/completed/errored)

## Getting Started

1. **Check the Basics:**  
   Explore detailed steps and concepts in the **[Overview of Automation Workflow](../README.md)**.

2. **Choose Your Automation Style:**  
   - **Declarative:** All-at-once deployments.
   - **Imperative:** Step-by-step incremental deployments.

3. **Customize & Integrate:**  
   Replace placeholders in the examples with your actual service names, endpoints, and credentials.

## Next Steps

Once you understand these basic patterns, explore the more detailed examples in the [examples](../examples/) directory, which demonstrate how to apply these patterns to specific technologies like F5, Palo Alto, AWS, and more.
