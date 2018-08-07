# Blackbox Exporter example #

Seguir a ordem abaixo para subir a stack de monitoramento. Dentro do arquivo `prometheus.yml` devemos adicionar os dominios a serem monitorados e também no final adicionar o IP e porta de onde está rodando o `blackbox_exporter`.

## Criando container do Blackbox Export ##

docker run -p 9115:9115 -d  --rm --name blackbox_exporter -v `pwd`:/config  prom/blackbox-exporter --config.file=/config/blackbox.yml

## Criando container do Prometheus ##

docker run --name prometheus --rm -p 9090:9090 -v `pwd`:/tmp/ quay.io/prometheus/prometheus --config.file=/tmp/prometheus.yml


