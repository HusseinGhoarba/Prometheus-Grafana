# $${\color{red}Prometheus-and-Grafana}$$	

### A Small project that cover the monitoring of a virtual machine from Amazon `EC2` (Applications, Containers & Resources)

>### Project Components:

<img src="prometheus-grafana.png" width=600>

>### Requires:

- At first read the PDF file [Prometheus&Grafana]() if you hadn't work with the Prometheus & Grafana before.

- A virtual Machine from [AMAZON](https://aws.amazon.com/console/) --> Create an `EC2 Instance`

- Install Pre-requests, Prometheus, .... and other from the [Full-Demo's](https://github.com/HusseinGhoarba/Prometheus-Grafana/tree/main/Installation-Demos) 

>### Project Gallery  

- EC2 with machine-type `t2-micro`, `Key-Pair`, Image of OS `Ubuntu`, disk storage = `12G` and security group as follows:  

<img src="Gallery/01-EC2.png" width=600>

- Allow the next ports in the security groups so that you can access the `Prometheus`, `Alertmanager` & `Grafana`.  

<img src="Gallery/02-Security-Group.png" width=600>

- Open a Terminal and `SSH` to connect to the `EC2`and change the tagged parts of the next command:
```
ssh -i `<add-path/key.pem>` ubuntu@`<Public-IP-of-EC2>`
```
<img src="Gallery/03-ssh-inside-the-EC2.png" width=600>

- Install the requires from the [Pre-requests-&-Demo's](https://github.com/HusseinGhoarba/Prometheus-Grafana/tree/main/Installation-Demos) ... After installation we have:
    - `Prometheus` as a service which listen on localhost of the machine on port `9090`
    <img src="Gallery/08-prometheus-service.png" width=600>
    <img src="Gallery/04-promethues-server.png" width=600>
    - Final Configuration-file-of-prometheus `/etc/prometheus/prometheus.yml`:
    <img src="Gallery/05-prometheus.yml.png" width=600>
    <img src="Gallery/06-prometheus.yml.png" width=600>
    - `CAdvisor` container for monitoring the containers:
    <img src="Gallery/07-cadvisor-container.png" width=600>
    - `node-exporter` as a service:
    <img src="Gallery/09-node-exporter-service.png" width=600>
    - Avery simple `nodejs-App` within a file `index.js`:
    <img src="Gallery/10-index.js-nodeApp.png" width=600>
    - `slack` application for `nodeApp-Down-Alert` on a channel:
    <img src="Gallery/11-1-slac-app.png" width=600>
    <img src="Gallery/11-2-slack-application.png" width=600>
    - `rule` quieries:
    <img src="Gallery/12-rules.yml-file.png" width=600>
    <img src="Gallery/13-rules-in-server.png" width=600>
    <img src="Gallery/14-alerts-on-server.png" width=600>
    - Configuration file of the `alertmanager` `/etc/alertmanager/alertmanager.yml`
    <img src="Gallery/15-configuration-of-alert.png" width=600>
    - `alertmanager` as a service and it listens on port `9093`:
    <img src="Gallery/16-alertmanager-service.png" width=600>
    <img src="Gallery/17-alertmanager-server.png" width=600>
    - Enable / run the `nodeApp`: 
    <img src="Gallery/18-enable-nodeApp.png" width=600>
        - `prometheus` alert section
        <img src="Gallery/19-prometheus-shot-after-enable-app.png" width=600>
        - `alertmanager`:
        <img src="Gallery/20-alertmanager-shot-after-enable-nodeApp.png" width=600>
        - `slack` notification:
        <img src="Gallery/21-slack-shot-after-enable-nodeApp.png" width=600>

    - `Grafana` as a service and it listens on port `3000`:
    <img src="Gallery/22-grafana-check-service.png" width=600>
    - After adding `Data Source` of the grafana as `Prometheus` and configure dashboards
    <img src="Gallery/23-grafana-shot.png" width=600>
    <img src="Gallery/24-grafana-shot-for-container-metrics.png" width=600>
    <img src="Gallery/25-grafana-shot-for-docker-metrics.png" width=600>
    <img src="Gallery/26-grafana-shot-for-EC2-metrics.png" width=600>