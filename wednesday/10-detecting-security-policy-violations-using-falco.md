## Meta
Sched URL(s): https://kccncna20.sched.com/event/ekGI/detecting-security-policies-violation-using-falco-a-practical-introduction-leonardo-grasso-sysdig

Youtube URL(s):

Falco Website: https://falco.org/

## Detecting Security Policies Violation Using Falco: A Practical Introduction - Leonardo Grasso, Sysdig

### Cloud Native Runtime Security
Intercepts and analyzes system calls...
Application uses system calls as API to kernel.

- Kernal Events (as source of truth)
- Enriched (with metadata)

    e.g. from container technologies, kubernetes meta, and kubernetes logs
- Assert against rules (at runtime)
- Alert (during violation events) 

### Why Falco?
- Protect against unexpected changes in system

### How it works

Falco uses eBPF! eBPF allows falco to tap into linux kernel to see syscalls.

Inputs: Kernel events, k8s audit log, container meta, k8s meta.

Engine + Rules

Outputs: Alerts, stdout, syslog, file, program, http, grpc

Can be consumed by language specific SDKs!

### The Rules

A rule defines conditions and message.

### Rule Examples
```bash
# A shell is run in a container
cocntainer.id != host and proc.name = bash

# Write below binary dir
open_write and fd.directory in (/bin, /sbin, /usr/bin, /usr/sbin)

# Container namespace change
evt.type = setns and not proc.name in (docker, sysdig)

# Non-device files written in /dev
(evt.type = create or evt.arg.flags contains O_CREATE) and proc.name != blkid and fd.directory = /dev and fd.name != /dev/null
```

### Demo

