# Skill-12: Deployment on Render Using Docker and Terraform

This project demonstrates deployment of a Spring Boot Library CRUD microservices application to Render using Dockerfiles and Terraform.

## Components
- `library-auth-service` — JWT login/authentication
- `library-book-service` — Book CRUD API backed by PostgreSQL
- `library-api-gateway` — public entry point for API requests
- `library-eureka-server` — used in the local Docker Compose setup; not deployed by the included Render Terraform configuration
- `compose.yaml` — local multi-container setup
- `terraform-render/` — provisions Render PostgreSQL and the three Render web services

## Deployment notes
1. Push the entire project folder contents to a GitHub repository; its root must contain `compose.yaml`, the service folders, and `terraform-render/`.
2. Read `terraform-render/README-START-HERE.txt` before deploying.
3. Use your own Render API key and a strong JWT secret. Never commit credentials or secrets.
4. Before running `terraform apply` or `terraform destroy`, carefully review the plan. Destroying the database deletes its data.
5. The included configuration requests Render free plans where available. Free-plan availability, limits, and database expiry can change; check the current Render dashboard and terms.

The Terraform resources in this version use the `skill-12-exp-` prefix. The Terraform examples use a placeholder GitHub repository URL; replace it with the repository where you uploaded this project. If you have already deployed an earlier `skill-11-...` or `skill-12-library-...` version, inspect the existing Terraform state and plan before applying: resource-name changes can create replacements rather than renaming existing Render services.
