## Meta
Sched URL: https://kccncna20.sched.com/event/ek9x/build-your-own-envoy-control-plane-steve-sloka-vmware
Youtube URL:

## Build Your Own Envoy Control Plane - Steve Sloka, VMware

### What is envoy
Designed for cloud native applications. Service proxy and edge. Open source. Used almost everywhere.

### Core concepts
1. Upstream/downstream

   Downstream (outside) -> envoy -> upstream (inside)

1. Listeners

    Named network location (port, unix socket) that can be connected to by downstream clients
    
    TCP/UDP. Filter chain. Filters. L7.
    
1. Routes

    L7 model. Virtual hosts. HTTP header modifications. Route entry per vhost.
    
1. Clusters

    Route to... clusters!
    
    A group of logically similar upstream hosts. Members are discovered vis service discovery.

1. Cluster Service Discovery

    Static. Strict/logical DNS (must resolve DNS entry). Original destination. Endpoint discovery service (EDS). Custom.
    
### Configuring Envoy
Ways to configure envoy...
1. Static file (like nginx).
1. Filesystem (like a hosting a static site).
1. REST endpoints
1. Management servers
    - gRPC-SotW (state of the world)
    - gRPC-Delta

### xDS
1. LDS Listener Discovery Service
1. RDS Route Discovery Service
1. CDS Cluster Discovery Service
1. EDS Endpoint Discovery Service

xDS comes from dropping the first letter.

### Four Variants
1. Separate gRPC streams per resource type (simple)
1. Aggregated gRPC stream for all resource types (complex, as you have to filter)

Read more at [envoy's documentation](https://www.envoyproxy.io/docs/envoy/latest/api-docs/xds_protocol) for xDS.
