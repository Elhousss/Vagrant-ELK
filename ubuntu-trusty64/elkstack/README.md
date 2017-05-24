# Docker ELK stack

ce repository est basé sur les images officielles:

* [elasticsearch](https://github.com/elastic/elasticsearch-docker)
* [logstash](https://github.com/elastic/logstash-docker)
* [kibana](https://github.com/elastic/kibana-docker)

# configuration indisponsable

## Setup

1. Installer [Docker](http://docker.io).
2. Installer [Docker-compose](http://docs.docker.com/compose/install/) **version >= 1.6**.

# Usage

demarrer ELK stack en executant *start_sh.sh*:

```bash
$ .start_sh.sh
```

executer la commande suivante pour tester l'execution de elasticsearch:

```bash
$ curl -X gET http://localhost:9200
```
vous pouvez vous connectez a kibana par le lien :

```bash
http://localhost:5601
```
si vous voulez injecter des logs, la config de logstash vous le permer via TCP:

```bash
$ nc localhost 5000 < /path/to/logfile.log
```

les ports d'ecoute sont:
* 5000: Logstash TCP input.
* 9200: Elasticsearch HTTP
* 9300: Elasticsearch TCP transport
* 5601: Kibana

pour consulter les logs de logstash
 
```bash
$ cd ./logstash/logs
```
pour consulter les logs d'elasticsearch
 
```bash
$ cd ./elasticsearch/logs
```
 