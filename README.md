# 🚀 Hasura monitoring  

## 📌 Overview  
This project ensures **safe environment separation** for Hasura deployments using:  
- **Environment-specific configurations** to prevent accidental production changes.  
- **CI/CD pipelines** for controlled deployments.  
- **Monitoring with Prometheus** to track critical actions.  

## 🔥 Features  
✅ **Environment Flags** – Differentiate `development`, `staging`, and `production`.  
✅ **Stricter Access Control** – Prevent unsafe actions in production.  
✅ **CI/CD Integration** – Automate deployments with **GitHub Actions**.  
✅ **Monitoring with Prometheus** – Track and alert on critical events.  

## 🛠 Tech Stack  
- **Docker** – Containerized Hasura setup.  
- **GitHub Actions** – CI/CD pipeline for deployments.  
- **Prometheus** – Monitoring and alerting system.  

## 🚀 Setup Instructions  

### 1️⃣ Clone the repository  
```sh
git clone https://github.com/omar-xy/hasura-monitoring.git
cd hasura-monitoring
