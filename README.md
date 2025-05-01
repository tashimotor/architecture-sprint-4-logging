# ELK Stack + Nginx Logging Project

This project provides an environment for collecting, storing, and visualizing Nginx web server logs using the ELK stack (Elasticsearch, Logstash, Kibana) together with Filebeat.

---

## Main Components

- **Nginx** — a web server that generates detailed access and error logs.
- **Filebeat** — a lightweight log shipper that forwards Nginx logs.
- **Logstash** — processes, parses, and transforms incoming logs.
- **Elasticsearch** — stores and indexes logs for fast search and analysis.
- **Kibana** — visualizes and analyzes logs via a convenient web interface.

---

## Project Structure

```
project-root/
|
|-- compose.yml             # Docker Compose configuration for all services
|-- conf/
|    |-- nginx/             # Nginx configuration files
|    |-- logstash/          # Logstash configs and pipelines
|    |-- filebeat/          # Filebeat configuration
|    |-- elasticsearch/     # Elasticsearch configuration
|    |-- kibana/            # Kibana configuration
|
|-- var/log/nginx/          # Mounted directory for Nginx logs
|
|-- elasticsearch/data/     # Elasticsearch data storage
```


---

## Quick Start

1. **Clone the repository:**
```shell script
git clone <repo-url>
   cd <project-root>
```


2. **Create required directories:**
```shell script
mkdir -p var/log/nginx elasticsearch/data
```


3. **Start all services:**
```shell script
docker compose up -d
```


4. **Service Ports:**
    - Nginx: [http://localhost:8080](http://localhost:8080)
    - Kibana: [http://localhost:5601](http://localhost:5601)
    - Elasticsearch: [http://localhost:9200](http://localhost:9200)

---

## Data Flow

1. Nginx writes logs to `var/log/nginx`.
2. Filebeat reads newly generated logs and forwards them to Logstash.
3. Logstash processes and parses log data, then sends it to Elasticsearch.
4. Kibana provides powerful visualization and search of the collected logs.

---

## Requirements

- Docker
- Docker Compose

---

## Notes

- All components communicate over a shared Docker bridge network.
- Key configuration files are stored in the `conf` folder and mounted into containers.
- The setup is customizable and supports additional log sources and pipelines.

---

## License

This project is intended for educational and demonstration purposes only.  
All trademarked names belong to their respective owners.

---

**Need help or have questions? Feel free to reach out!**
