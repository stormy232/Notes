managed solution for collecting, processing, analyzing streaming data in "real time"

Kinesis Data Streams
- producers -> kinesis data streams which distribs to "shards" -> consumers
- you pay per running shard
- manually configure consumers
- persist from 24hours(default) to 168hours

Firehose Delivery Stream:
- one consumer from a predef list
- data immediately disappears once consumed
- pay only for data ingested

Video Streams:
- ingesting video 
- ouput video data to video processing/ml services

Data Analytics
- specify firehose/data streams as input output
- data that pass through can have custom sql queries run on them and the result give output