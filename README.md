# 🚀 Hasura monitoring  

## 📌 Overview  
This project ensures **safe environment separation** for Hasura deployments using:

- **Environment-specific configurations** to prevent accidental production changes.  
- **Challenge**: Prevent accidental changes to the production Hasura instance by differentiating it from dev/staging.
- **Solution**: Deployed via separate Docker Compose files and GitHub Actions workflows.
- **Tech Stack**: Hasura GraphQL Engine, PostgreSQL, Docker Compose, GitHub Actions.
- **CI/CD pipelines** for controlled deployments.  
- **Monitoring with Prometheus** to track critical actions.

## 🔥 Features  
✅ **Environment Flags** – Differentiate `development`, and `production`.  
✅ **Stricter Access Control** – Prevent unsafe actions in production.  
✅ **CI/CD Integration** – Automate deployments with **GitHub Actions**.  
✅ **Monitoring with Prometheus** – Track and alert on critical events.  

## Prerequisites

- Docker and Docker Compose installed
- GitHub account for CI/CD
- Basic familiarity with Hasura and PostgreSQL

## Setup Instructions

### Local Development

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/omar-xy/hasura-monitoring.git
   cd hasura-monitoring

2. Create a `.env` file in the root of the project using the provided template:

   ```bash
   cp .env.template .env

3. Update the   `.env` file with your PostgreSQL credentials

### .env

```ini
# .env.template
# PostgreSQL password for both dev and prod environments
POSTGRES_PASSWORD=

# hasura admin secret for development/staging environment
HASURA_ADMIN_SECRET_DEV=

# hasura admin secret for production environment
HASURA_ADMIN_SECRET_PROD=
```

---

## Run Development Environment:

    ```bash
    docker-compose -f docker-compose.dev.yml up -d --env-file .env
    ```

---> Access Hasura at http://localhost:8080 (admin secret: your_dev_secret).

## Run Production Environment:

    ```bash
    docker-compose -f docker-compose.prod.yml up -d --env-file .env
    ```

---> Access Hasura at http://localhost:8081 (admin secret: your_prod_secret).


- **Solution Details**

- Problem: Identical Hasura Console UIs for dev/staging and prod risk accidental production changes.

- Fix: Set Hasura Admin Secret in respective environments.

- CI/CD: Separate GitHub Actions workflows (deploy-dev.yml, deploy-prod.yml) simulate deployment isolation.
