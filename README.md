# NGINX Observability & Alerting Lab
---

## Project Overview

This project demonstrates real-world DevOps observability and incident response.

I built a simple NGINX application, monitored it using Prometheus, configured Alertmanager to send email alerts, intentionally stopped NGINX, received a CRITICAL alert, fixed the issue, and then received a RESOLVED alert.

This proves full monitoring, alerting, and recovery — end to end

---

## Tech Stack

### Containerization & Orchestration
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](./docker-compose.yml)
[![Docker Compose](https://img.shields.io/badge/Docker_Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)](./docker-compose.yml)

### Monitoring & Observability
[![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)](./prometheus/prometheus.yml)
[![Alertmanager](https://img.shields.io/badge/Alertmanager-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)](./alertmanager/alertmanager.yml)

### Web Server
[![NGINX](https://img.shields.io/badge/NGINX-009639?style=for-the-badge&logo=nginx&logoColor=white)](./nginx/nginx.conf)

### Configuration
[![YAML](https://img.shields.io/badge/YAML-CB171E?style=for-the-badge&logo=yaml&logoColor=white)](./prometheus/prometheus.yml)

---

 ##  Project Structure
 
**devops-observability-lab**/

├── **nginx**/
 
└── nginx.conf

├── **prometheus**/

   └── prometheus.yml

├── **alertmanager**/

  └── alertmanager.yml

├── docker-compose.yml

├── README.md

---


# How the System Works

- NGINX runs inside a Docker container

- Prometheus scrapes NGINX metrics

- Alert rules detect downtime

- Alertmanager sends email alerts

- Alerts resolve automatically when service recovers

  ---

  # Failure Simulation (Intentional)

  **Step 1-Stop NGINX**
  - docker stop nginx_app

 **What Happened**

- Prometheus marked the target as DOWN

- Alert rule fired

- Alertmanager sent a CRITICAL email alert

  

<img width="1242" height="104" alt="2026-01-20_18h05_35" src="https://github.com/user-attachments/assets/1995c7fb-1c05-4bcc-a926-024db7db7f04" />

**Simulating Service Failure - Stopping NGINX container to trigger Prometheus alert**


---

<img width="888" height="334" alt="2026-01-19_21h54_34" src="https://github.com/user-attachments/assets/f1f01c46-9297-4e51-8aee-35ddc811277c" />

**Alertmanager Dashboard - Critical severity alert displayed for NGINX service downtime**

---

<img width="1564" height="237" alt="2026-01-19_21h54_02" src="https://github.com/user-attachments/assets/288c7833-4822-4c8d-bf99-9ecadec57d0b" />

**Alert Cleared - Prometheus Alert Active - NGINX down alert firing in Prometheus monitoring dashboard**


  ---

  # Incident Response & Recovery

  **Step 2-Restart NGINX**
  - docker start nginx_app

**What Happened**

- NGINX recovered

- Prometheus marked service as UP

- Alertmanager sent a RESOLVED email

  ---
  
# Alerting Evidence 

<img width="1094" height="631" alt="2026-01-20_18h08_30" src="https://github.com/user-attachments/assets/14f6be86-28d9-4b7b-937b-b0c5b4d44026" />

**Critical Alert Triggered - Email notification sent by Alertmanager when NGINX service goes down**

---

<img width="1099" height="630" alt="2026-01-20_18h08_51" src="https://github.com/user-attachments/assets/3a764cac-36ef-41be-8b28-042fbafc6867" />

**Alert Resolved - Email confirmation sent when NGINX service is restored and healthy**

---

## Key Learnings 

- Service health monitoring with Prometheus

- Email alerting with Alertmanager

- Debugging SMTP and config issues

- Incident detection and recovery

- Production-style observability workflow

---

  ##  Why This Project Matters

  **This project proves I can**:

- Monitor live services

- Detect failures

- Respond to incidents

- Restore services

- Validate fixes with alerts
  
---
