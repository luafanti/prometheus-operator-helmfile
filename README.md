# Spring Boot monitoring with Prometheus Operator
Demo of Prometheus Operator and Grafana preinstalled dashboard. This repository is a part of [Dev.to article](https://dev.to/luafanti/spring-boot-monitoring-with-prometheus-operator-40g1)

### Prerequisites 

- kubernetes cluster
- helm & helmfile - [Installation Gist](https://gist.github.com/luafanti/df3116022157cabd516ccd26cb8f7565).

### Installation


```bash
helmfile apply -i
```

After a short while, you should see a message that you have successfully installed three releases.

```bash
UPDATED RELEASES:
NAME                    CHART                                        VERSION
kube-prometheus-stack   prometheus-community/kube-prometheus-stack    43.2.0
grafana-dashboards      local-charts/grafana-dashboards                1.0.0
demo                    luafanti/spring-debug-app                      1.0.0
```

* **kube-prometheus-stack**  - Prometheus Operator Helm Chart with ServiceMonitor configured to scrap demo Spring Boot application.
* **grafana-dashboards** - local Helm chart that installs ConfigMaps with predefined Grafana dashboards.
* **demo** - my Spring Boot demo application that exposes Prometheus's metrics. [GitHub repo link.](https://github.com/luafanti/spring-boot-debug-app)