# README

The Online Discourse Insight Explorer will let users visualize how various media sources are using hashtags on twitter. It is on an ELK stack.

![Pretty albino elk striding across the path](https://www.thelocal.se/userdata/images/article/3ebf43712d0b75536cef1578d71cd4cdb79d3cd9d8f60dcbcd5647cc8c11b699.jpg)


## OS X setup instructions
First, install dependencies:
* `brew install elasticsearch`
* `brew install kibana`
* `brew install logstash`
* `logstash-plugin install logstash-input-twitter`

This has been tested with elasticsearch 6.5, kibana 6.5, and logstash 6.6.

Second, copy `config/twitter.conf.example` to `config/twitter.conf`, editing in your local values.

A good `keywords` value for testing is `["kittens"]`, which is guaranteed to have fast results.

## Running
* `brew services start elasticsearch`
* `brew services start kibana`
* `logstash -f config/twitter.conf`

http://localhost:9200 should now show that elasticsearch is alive. http://localhost:5601 should now show a default kibana page.

## Troubleshooting

* Special characters in the `twitter.conf` `keywords` value can cause `Twitter::Error::Unauthorized`.
