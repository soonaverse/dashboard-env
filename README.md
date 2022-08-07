# Dashboard & Hornet Environment
This repository holds the generic configuration for Hornet, Prometheus and Grafana configuration that has been developed for the Soonaverse. The Grafana dashboard is based on an initial dashboard created by Dr. Electron

The Dashboard is located at: https://github.com/soonaverse/dashboard-env/blob/main/assets/grafana/dashboards/dashboard.yaml

The Hornet Environment adds to the current Stardust Hornet environemt to add some configuration to the .env file to make administration easier and the transition from test to prod environemts more standard.

Node exporter docker contain has been added to support dashboard panels that show CPU/Disk/Load and other node metrics. This can be disabled by editing the .env file and removing the `dc-node-exporter.yml` from the following line:
```
COMPOSE_FILE=docker-compose.yml:dc-node-exporter.yml:dc-hornet-api-loadbal.yml
```

Also each optional INX plugin and prometheus and grafana can be enabled and disabled by adding them or removing them from the following line in the .env file:
```
COMPOSE_PROFILES="indexer,dashboard,prometheus,grafana,traefik"
```

This environment is intendeed to be a proposed implementation using the current Stardust Hornet configuration. It is set up to show different options of the docker environment but will not be maintained or supported other than to provide a template for others to add to their own Hornet node installations. This is not intended to be an automatic Hornet installation.
