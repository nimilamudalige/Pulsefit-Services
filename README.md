# PulseFit — Services (Parent / Super-Repository)

## Project Description

This is the **parent repository** for the PulseFit business services tier.
It is a super-repository that ties together three independent child
repositories as Git submodules:

- [`member-service`](https://github.com/nimilamudalige/member-service) — gym member profiles (MySQL) + Cloud Storage photo upload
- [`class-service`](https://github.com/nimilamudalige/class-service) — fitness class catalog (MySQL)
- [`booking-service`](https://github.com/nimilamudalige/booking-service) — class bookings (MongoDB) + Firestore audit log

Each microservice is independently deployable and independently
auto-scaled on GCP — its own health check, instance template and regional
Managed Instance Group — see `deployment/GCP_CLI_DEPLOYMENT_GUIDE.md` in the
workspace root.

## Technology Stack

- Java 25, Spring Boot 4.0.8, Spring Cloud 2025.1.3, Spring Data (JPA + MongoDB)
- Git submodules (polyrepo architecture)
- PM2 for process management on each VM

## Setup / Getting Started

```bash
git clone --recurse-submodules https://github.com/nimilamudalige/pulsefit-services.git
cd pulsefit-services
# Start the platform first (config-server, service-registry, api-gateway),
# then run member-service, class-service, booking-service in any order.
```

If you already cloned without `--recurse-submodules`:

```bash
git submodule update --init --recursive
```

## Student Information

- **Student Name:** Pasan Nimila
- **Student Number:** 2301692034
- **Slack Handle:** pasan_nimila (optional)
- **GCP Project ID:** pulsefit-capstone
