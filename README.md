docker-compose.yml (in version 3.2) config file which contains:
- 3 services (web, sidekiq and crono)
- Each of these services work with "docker deploy" command (possible to deploy it to Swarm)
- Each of these services have a memory limit of 800Mb and CPU set to 0.25
- Docker image for each service is quay.io/netguru/baseimage:0.10.2
- "Web" service has attached to volumes:
    staging-assets:/app/public/assets
    /var/log/app:/app/log
- Service "web" and "sidekiq" use a "swarm" network which is external
- Service "sidekiq" and "crono" use "internal" network
