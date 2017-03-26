##Feedr
A simple logstash-elasticsearch hack to keep up with your RSS feeds

##One time setup
Download logstash-5.1.2.zip and extract directory and install rss-input and elasticsearch-output plugins.

Download elasticsearch-2.4.1.zip and extract directory.

A map of RSS aliases and feed url is maintained at feedmap.json . It has a 4 feed entries for a start.
You can alter them (don't screw up the json syntax).

config file for logstash : readerapp.conf

#Shoot up elasticsearch

Open a new terminal window. Navigate to elasticsearch-2.4.1 directory.

$ bin/elasticsearch

check if elasticsearch is running on port 9200.

$ curl -XPUT 'http://localhost:9200/reader

this will create 'reader' index for our app.


#Shoot up logstash

Open a terminal window. Navigate to feedr directory.

$ path-to-logstashdir/bin/logstash -f readerapp.conf -r  ( -r flag is important )


#Start the app

Open a terminal window. Navigate to feedr directory.

$ npm install
$ gulp

Open up http://localhost:3000 in your browser. Enjoy.