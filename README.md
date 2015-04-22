# What is SBT?

![logo](logo.png)

sbt is an open source build tool for Scala and Java projects, similar to Java's Maven or Ant.

> [wikipedia.org/wiki/SBT_(software))

This image is based on [Oracle JRE 8](https://github.com/1science/docker-java/tree/oracle-jre-8) and the image size is approximately 230 MB.

# Included plugins

The following [Elasticsearch plugins](http://www.elastic.co/guide/en/elasticsearch/reference/1.x/modules-plugins.html) are installed :

 - [Kopf](https://github.com/lmenezes/elasticsearch-kopf) : Web admin interface for elasticsearch
 - [HQ] (https://github.com/royrusso/elasticsearch-HQ) : Monitoring and Management Web Application 
 - [AWS Cloud](https://github.com/elastic/elasticsearch-cloud-aws) : EC2 discovery and S3 Repository

# Supported tags

-	[`0.13.8`, `latest`](https://github.com/1science/docker-sbt/tree/0.13.8)


# Usage

You can run the default `elasticsearch` command simply:

```
docker run -d 1science/elasticsearch
```

You can also pass in additional flags to `elasticsearch`:

```
docker run -d 1science/elasticsearch elasticsearch -Des.node.name="TestNode"
```

This image comes with a default set of configuration files for `elasticsearch`, but if you want to provide your own set of configuration files, you can do so via a volume mounted at `/usr/share/elasticsearch/config`:

```
docker run -d -v "$PWD/config":/usr/share/elasticsearch/config 1science/elasticsearch
```

This image is configured with a volume at `/usr/share/elasticsearch/data` to hold the persisted index data. Use that path if you would like to keep the data in a mounted volume:

```
docker run -d -v "$PWD/esdata":/usr/share/elasticsearch/data 1science/elasticsearch
```

# License

All the code contained in this repository, unless explicitly stated, is
licensed under ISC license.

A copy of the license can be found inside the [LICENSE](LICENSE) file.