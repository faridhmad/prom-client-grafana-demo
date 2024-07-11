# prom-client-grafana-demo

## Overview

This project demonstrates how to monitor a Node.js application using Prometheus for metrics collection and Grafana for visualization. It's designed to be a simple yet informative example of setting up basic observability for your Node.js services.

## Features

* **Metrics Collection:** Collects default Node.js metrics (memory usage, event loop lag, garbage collection) using the `prom-client` library.
* **Custom Health Endpoint:** Provides a `/health` endpoint to check server status, uptime, and memory usage.
* **Metrics Endpoint:** Exposes a `/metrics` endpoint for Prometheus to scrape.
* **Dockerized Setup:** Includes a `Dockerfile` for containerizing the application.
* **Docker Compose Configuration:**  Simplifies development with a `docker-compose.yml` file to run the app, Prometheus, and Grafana.

## Prerequisites

* Docker
* Docker Compose
* Node.js and npm (if running outside of Docker)

## Getting Started

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/faridhmad/prom-client-grafana-demo
   cd prom-client-grafana-demo
   ```

2. **Run with Docker Compose:**

   ```bash
   docker-compose up -d
   ```

3. **Access the App:**

   * Your Node.js app will be available at `http://localhost:8081`.
   * Prometheus will be available at `http://localhost:9090`.
   * Grafana will be available at `http://localhost:3000`. (Default login: admin/admin)

5. **Configure Prometheus:**
   * **Important:**
     * Find your machine's local public IP address (e.g., using `ipconfig` or `ifconfig`). 
     * Replace `<your-machine-local-ip>` in `prometheus-config.yml` with your actual IP.

   * Add Prometheus as a data source in Grafana.
   * Import dashboards (you can find Node.js-specific dashboards in the Grafana community).

6. **Configure Grafana:**

   * Add Prometheus as a data source in Grafana.
   * Import dashboards (you can find Node.js-specific dashboards in the Grafana community).

## Customization

* **Custom Metrics:** Add your own application-specific metrics to `index.js` using the `prom-client` library.
* **Health Checks:** Extend the `/health` endpoint to check external dependencies (databases, APIs).
* **Alerting:** Set up alerts in Prometheus based on metric thresholds.

## Contributing

Feel free to submit pull requests or open issues to report problems or suggest enhancements.
