# Engineering Decisions

## Engineering Philosophy

MNDweb was built around a practical engineering principle:

> Quality comes from good decisions, not expensive infrastructure.

The project was developed within a constrained production environment, requiring careful consideration of reliability, maintainability, and resource usage.

The goal was not to build the most complex system possible, but to build the right system for the actual requirements.

---

## Choosing a Modular Monolith

A modular monolith architecture was selected instead of separating the system into multiple independent services.

Reasons:

- The application size did not require distributed complexity
- The available infrastructure favored fewer processes
- Deployment needed to remain simple
- Maintenance needed to be manageable

The system still maintains clear boundaries between functional areas while avoiding unnecessary operational overhead.

---

## Avoiding Premature Microservices

Microservices were intentionally avoided because they would introduce additional complexity without providing meaningful benefits for the project's current requirements.

Additional services would require:

- More infrastructure management
- More memory usage
- More deployment considerations
- More operational overhead

A well-structured monolith provided the required flexibility while remaining efficient.

---

## Building a Custom CMS

A custom CMS was developed instead of relying on an external content management platform.

This decision was based on:

- Matching the client's workflow
- Maintaining control over features
- Avoiding unnecessary dependencies
- Keeping the system lightweight

The CMS was designed around the actual business requirements rather than forcing the workflow into an existing platform.

---

## Using Background Processing

Background processing was introduced for operations that should not affect user-facing requests.

Using Celery and Redis provided:

- Better workload separation
- Improved responsiveness
- More predictable execution of maintenance tasks

This allowed resource-intensive operations to run independently from normal application traffic.

---

## Prioritizing Observability

Even with a small infrastructure footprint, operational visibility remained important.

The system includes monitoring capabilities to track:

- Resource usage
- Storage status
- Application health

Observability was treated as a requirement rather than an optional feature.

---

## Optimizing Before Scaling

Instead of increasing infrastructure resources immediately, the system was optimized around the available environment.

Optimization decisions included:

- Reducing unnecessary services
- Controlling background workloads
- Automating maintenance tasks
- Monitoring resource usage

The approach was to improve efficiency first and scale only when actual requirements justified it.

---

## Balancing Simplicity and Scalability

The architecture was designed to remain simple while preserving future growth opportunities.

The system avoids unnecessary complexity today while keeping clear paths for future improvements.

Good architecture is not about predicting every future requirement, but about making current decisions that do not prevent future evolution.

---

## Final Lessons

MNDweb demonstrates that production-quality systems can be built on modest infrastructure when engineering decisions are made carefully.

The project reinforced several principles:

- Simplicity improves reliability
- Constraints encourage better design
- Automation reduces operational risk
- Observability improves confidence
- Appropriate architecture matters more than infrastructure size

The strongest systems are not always the largest systems. They are the systems that are intentionally designed for their purpose.