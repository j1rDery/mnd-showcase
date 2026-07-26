# Infrastructure

## Production Environment

MNDweb was deployed on a lightweight VPS environment designed around a strict resource budget.

The production server:

- VPS hosting environment
- 512MB RAM
- 10GB storage
- Linux-based operating system
- No Docker runtime
- Django-based application stack

The infrastructure was intentionally simple to minimize operational overhead and maximize available resources for the application itself.

The deployment environment was selected based on the project's actual requirements rather than relying on unnecessary infrastructure complexity.

---

## Resource Constraints

Running a production application on a 512MB RAM VPS introduced several practical limitations.

Common development conveniences were not always suitable for this environment.

For example:

- Heavy development tools could consume too much memory
- Container-based workflows would introduce additional overhead
- Background services needed careful consideration
- Storage usage needed continuous monitoring
- Operational visibility needed to be implemented without heavy monitoring infrastructure

These constraints influenced architectural and operational decisions throughout the project.

---

## Deployment Approach

The deployment workflow prioritized reliability and low resource usage.

Because the server had limited memory, deployment and maintenance were performed using lightweight tools:

- SSH-based server access
- Command-line administration
- Direct application deployment
- Minimal background services

This approach reduced infrastructure overhead and kept more resources available for the production application.

The deployment strategy focused on simplicity and predictability rather than introducing additional layers that would increase maintenance requirements.

---

## Infrastructure Decisions

The infrastructure strategy was based on a simple principle:

> Quality comes from good engineering decisions, not expensive infrastructure.

Instead of increasing server resources immediately, the system was optimized around the available environment.

Key decisions:

- Avoid unnecessary infrastructure complexity
- Use only required services
- Keep the deployment stack lightweight
- Optimize application behavior before scaling hardware
- Automate repetitive operational tasks

The goal was not to build the largest infrastructure possible, but to build a reliable system appropriate for the project's requirements.

---

## Lessons Learned

Limited infrastructure forces better engineering discipline.

Working within a 512MB RAM environment highlighted the importance of:

- Understanding resource consumption
- Choosing appropriate technologies
- Avoiding unnecessary complexity
- Designing systems with operational costs in mind

A well-designed system can provide reliable production service even with modest infrastructure when engineering decisions are made carefully.