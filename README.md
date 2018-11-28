# README

## OS X setup instructions
* `brew install elasticsearch@5.6` (if you don't already have it from Lumen)
* `brew install kibana@5.6`
* `brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/2ca15b6ae0701f98985a53e7b7daab5f8ee5f1d1/Formula/logstash.rb`

You need the wild formula for logstash because homebrew no longer supplies versions <6.5, but elasticsearch 5.6 is only compatible with logstash <= 6.0.x. That's the commit where the formula was updated to logstash 6.0.1 (the latest available 6.0 release).

* `brew services start elasticsearch@5.6`
* `brew services start logstash`
* `brew services start kibana@5.6`

http://localhost:9200 should now show that elasticsearch is alive. http://localhost:5601 should now show a default kibana page.
