# rbac

Role-Based Access Control (RBAC) configuration for Ortelius.

This repository centralizes RBAC role definitions and permission policies that govern how users and services interact with Ortelius APIs and resources.

---

## Repository Contents

| File | Purpose |
|------|---------|
| `rbac.yaml` | Core RBAC definitions (roles, permissions, scopes) |
| `.gitignore` | Standard ignore rules |

> This repo is focused exclusively on access control definitions and does not include application logic.  

---

## What is RBAC?

RBAC (Role-Based Access Control) is an authorization model that restricts system access based on assigned **roles**, where each role encapsulates a set of **permissions**. RBAC simplifies permissions management, improves security, and aligns access with organizational responsibilities. :contentReference[oaicite:0]{index=0}

---

## RBAC Structure (Conceptual)

The RBAC model typically includes:

- **Roles**  
  Named collections of permissions scoped to specific system functions (e.g., `admin`, `reader`, `maintainer`).

- **Permissions**  
  Actions that subjects (users, services) are allowed to perform (e.g., `read:image`, `write:image`, `delete:image`).

- **Bindings / Assignments**  
  Mappings that link identities to roles within particular scopes (projects, namespaces).

> Actual definitions and naming conventions are sourced from the repository's `rbac.yaml`.

---

## Related Projects

ortelius – API and backend service for Ortelius.

frontend – Next.js UI for Ortelius search and exploration.


---

## Usage

RBAC definitions in this repository can be used to:

1. **Deploy Access Policies**  
   Apply role definitions to infrastructure or services that enforce access control for the Ortelius API.

2. **Generate Documentation**  
   Use tooling to render human-friendly tables of roles and permissions for audit and onboarding.

3. **Automate CI/CD Security Policies**  
   Integrate these rules into CI/CD pipelines or policy engines (e.g., OPA, Kubernetes RBAC) as required.

---

## Example (Illustrative)

Below is a conceptual snippet showing how RBAC roles might be defined (your actual `rbac.yaml` may differ):

```yaml
roles:
  - name: ortelius_admin
    description: Full administrative access
    permissions:
      - "*"
  - name: ortelius_reader
    description: Read-only access to Ortelius resources
    permissions:
      - "ortelius:read:*"
```
 

## License

Apache License 2.0

### Community

- Website: [https://ortelius.io](https://ortelius.io)
- GitHub: [https://github.com/ortelius](https://github.com/ortelius)
- Discord: [https://discord.gg/ortelius](https://discord.gg/ortelius)

Maintained by the Ortelius open-source community.

