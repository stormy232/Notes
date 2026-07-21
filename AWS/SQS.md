Queueing
- Generally will delete messages once they have been consumed simple comm. they have to pull to recieve

Streaming:
- multiple consumers can react ot events
- events live in stream for long time

SQS -> application integration

pull based -> good for microservices
256KB to 2GB
Message Retention
- default 4 days
- can be adjusted from 60seconds to 14days

Standard Queues -> more than onc copy can be delievered out of order
-> unlimited transactions

FIFO Queues
- first in first out

visibility time out is period of time that messages are invisible in queue after reader picks up message

Messages deleted after job has processed
if job is not processed in this time-out frame message becomes visible again

