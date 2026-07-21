NoSQL -> store 
key/value and document db

Row -> Item
cell -> attr
primary key = part key + sort key

data is inconsistent if reading from a copy that has yet to be updated

eventual consistent reads (DEFAULT):
- copies are being updates its possible for you to read and be returned an inconsisten copy
- fast reads no consistent guarantee

Strongly Consistent Reads:
- stronger consistenty
- second diff in latency (worse)