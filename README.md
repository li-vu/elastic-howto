# ELASTIC HOW-TO

## Installation for Mac OS X

1. Elasticsearch

```shell
brew install elasticsearch
elasticsearch
```

Open `http://localhost:9200/` in a browser.

Configuration location: `/usr/local/etc/elasticsearch/`

2. Kibana

```shell
brew install kibana
kibana
```
Open `http://localhost:5601/` in a browser.

In order to add other indexes other than `logstash*` ones, uncheck *Index contains time-based events*.

Configuration location: `/usr/local/etc/kibana/`

3. logstash

```shell
brew install kibana
```

Example configuration:
```
input {
    file {
        path => "/var/log/system.log"
        start_position => beginning 
    }
}

output {
  elasticsearch { 
  host => "localhost"
  cluster => "elasticsearch_lvho"
  }
  stdout { codec => rubydebug }
}
```

## More

- [How to install Elasticsearch, Kibana, logstash](https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-4-on-ubuntu-14-04)
- [Effective web crawler](http://rmmod.com/effective-web-crawler/)
- [Having fun with Elasticsearch and Python, part I](http://bitquabit.com/post/having-fun-python-and-elasticsearch-part-1/)
- [Scrapy Tutorial](http://doc.scrapy.org/en/1.0/intro/tutorial.html)
