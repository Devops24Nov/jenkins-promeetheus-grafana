# jenkins-promeetheus-grafana

1. jenkins container
    dockeer run -i -t -d -P --name=jenkins jenkins
    
  1.1 install  promethues plugin for mjenkins metrics


2. prometheus
    docker run -i -t -d -p 9090:9090 --name=prometheus prom/prometheus 
    2.1 : update prometheus.yaml file
     - jobname: 'jenkins'
       metrics_path: /prometheus
       static_configs:
         targets: ['jenkinsurl']

3. grafana:
    docker run -i -t -d -p 3000:3000 --name=grafana grafana/grafana 
    
    3.1 : update data source about prometheus
