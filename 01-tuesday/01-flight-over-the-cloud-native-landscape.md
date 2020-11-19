## Meta
Sched URL: https://kccncna20.sched.com/event/ek9f/a-flight-over-the-cloud-native-landscape-carson-anderson-weave

Youtube URL:

## A Flight Over the Cloud Native Landscape - Carson Anderson, Weave

### Prometheus
Data. Logs.

### Thanos
Exists along with Prometheus. Geographic regions. Aggregate data across different clusters. Distributed prometheus. Long term storage.

### Fluentd
Log processing.

### Vitess
Relational databases in k8s clusters. Problem -- scale vertically, but vertical scaling is bad in cloud. Enter Vitess... API on top of databases.

### TiKV
Key/value store. Scales horizontally "very very well." "Huge scale." Distributed ACID compliant operations (niice).

### ETCD
Key/value store. Focus on simplicity (versus scale). Leader election. Fault tolerance. Go-to backend for k8s (although other tech is now being introduced/used).

### Dragonfly
Peer to peer file transmissions. Image transmissions available too.

### Cloud Events
Different terms for events. Standards/SDK to help interop.

### NATS
Message bus.

### SPIFFE + SPIRE
Identity in the cloud. Not just user-- node, process, etc. You will probably use the SPIRE tool instead of SPIFFE.

### Open Policy Agent
Enforce policies (e.g. what)

### Falco
Container runtime security
