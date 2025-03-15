# Elasticsearch docker-compose
Docker-compose for single node Elasticsearch cluster

See .env file for configuration.

Based on the 3 node [`docker-compose.yml`](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html) by Elastic.

I created this setup for easy experimenting with Elasticsearch. On test environments I don't have the need or space for a 3 node cluster.

Disadvantages:
* A self signed certificate is used that might prevent easy connections to the cluster from Java , Logstash or other tools.
* Kibana by default phones home on startup using https. If you are running this behind a corporate man in the midle firewall, these connections will fail because the spoofed certificates are not trusted. 
  Getting Machine learning models into Elasticsearch from within Kibana will fail for the same reason. You can get around this by using the Eland tool.

