## Meta
Sched URL(s): https://kccncna20.sched.com/event/ekA3/a-high-schoolers-guide-to-kubernetes-network-observability-drew-ripberger-nirmata

Youtube URL(s):

## A High-Schooler’s Guide to Kubernetes Network Observability - Drew Ripberger, Nirmata

kube-netc is a eBPF toolchain deployed as a daemonset.

### The goal
- All emcompassing networking statistics at TCP layer
- Easily interpretable statistics to be visualized or processed upstream

### Agenda
1. What is eBPF?
1. Tracking stats with prometheus
1. Daemonsets with k8s
1. kube-netc tying it all together
1. Demo

### What is eBPF
Monitoring using eBPF.

- eBPF: extended berkeley packet filter
- it is bytecode running inside the linux kernel
- Sandboxed VM
- Implications in networking, observability, security, and more!

### eBPF crash course
- There is C and GO sdks for writing eBPF.
- `bcc` lets you write eBPF byte code as a subset of C using LLVM as a backend

### Implementing Prometheus
Great interoperability with grafana! That is good news for visualizing prometheus data.

PromQL queries for quick processing.
