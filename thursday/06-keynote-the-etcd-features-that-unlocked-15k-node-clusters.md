## Meta
Sched URL(s): https://kccncna20.sched.com/event/eoFN/keynote-kubernetes-and-etcd-features-that-unlocked-15k-node-clusters-wojciech-tyczynski-staff-software-engineer-google

Youtube URL(s):

## Keynote: Kubernetes and etcd Features That Unlocked 15k Node Clusters - Wojciech Tyczyński, Staff Software Engineer, Google

### 15k node clusters are a thing
Twitter
Bayer CropScience

### Scalability Envelope
- Namespaces
- Nodes
- Ingresses
- Pod Churn
- Pods
- Backends
- Services
- Secrets
- etc...

### Scalability principle

### Should I care?
Two extreme users, is that important to MY cluster?

### ETCD
Main improvement is concurrent reads. No longer are reads a blocking operation.

### Networking
5Gigabytes of data to change across all nodes.
25Terrabytes of data for endpoints.

Improvement is to "slice" up endpoints into endpoint slices.

### Storage (of secrets/configmaps)
Improvement is configmaps and secrets can be tagged immutable, thus kubernetes control plane no longer needs to watch.

### Ecosystem (golang)
Memory pointer issues were discovered for golang.

### Anything else needed?
SLO (service level objectives) - once achieved, improvements will probably not be sought after. At this time, SLOs may be reevaluated.

### Reliability & performance
