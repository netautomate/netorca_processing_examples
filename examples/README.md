# NetOrca Processing Examples

This directory contains illustrative examples of how to use NetOrca for various network automation tasks. These examples are meant to demonstrate concepts and patterns, and may require adjustments to work in your specific environment.

## Directory Structure

- `./basics/` - Contains fundamental building blocks and reusable components
  - `ansible/` - Contains core Ansible playbooks and templates
    - `declarative_submission.yaml` - Template for declarative automation (e.g., F5 AS3)
    - `imperative_submission.yaml` - Template for imperative automation (e.g., Palo Alto)
    - `validation.yaml` - Template for adding validation steps
    - `declaration.j2` - Jinja2 template for declarations
  - `terraform/` - Contains Terraform examples and components
- `./examples/` - Contains complete examples that combine basic components

## How to Use These Examples

### Combining Basics with Examples

1. **Choose Your Automation Style**
   - **Declarative Automation** (e.g., F5 AS3)
     - Use `./basics/ansible/declarative_submission.yaml` as your base
     - Replace the custom logic section with your specific implementation
   - **Imperative Automation** (e.g., Palo Alto)
     - Use `./basics/ansible/imperative_submission.yaml` as your base
     - Add your specific device configuration steps

2. **Understanding the Examples**
   - Each example demonstrates how to implement a specific use case
   - Examples show where to insert your custom logic within the basic templates
   - Follow the pattern of:
     - Getting change instances
     - Processing service items
     - Implementing your custom logic
     - Updating change instance records

3. **Creating Your Implementation**
   - Copy the appropriate basic template
   - Add your custom logic where indicated
   - Ensure proper variable handling
   - Test thoroughly
