## Meta
Sched URL: https://kccncna20.sched.com/event/ekAC/pid-1-sig-handling-hooks-probes-managing-container-lifecycle-correctly-anmol-krishan-sachdeva-olx-group-naspers
Youtube URL:

## PID 1, SIG Handling, Hooks & Probes: Managing Container Lifecycle Correctly - Anmol Krishan Sachdeva, OLX Group, Naspers

"All stack developer" lol, nice.

Managed lifecycle (pod & container lifecycle, linux signals)

### The Big Picture
Processes, zombies, and containers.

Unix Process (PID 1 = init). All processes are subprocesses of PID 1. PID 1 is started by the kernel. A terminated process that has been deleted but is waiting on the `waitpid()` system call, waiting for "reaping."

`SIGCHILD` signal is sent to parent process, then the parent process executes `waitpid()` on child.

Orphan process occurs when the parent process is deleted. Reparenting will occur on orphaned processes.

Too many zombies may cause a resource starved state.

Should we use bash as a parent process?

### Init System to the rescue
Tini is an open source "simple and light weight" init system. Reaps zombies/orphaned processes but needs to be PID 1.

### Managed Lifecycle
Pod & container lifecycle, linux signals.

Pod lifecycle
Pending => Running (or Unknown) => Succeeded (or Failed)

Container lifecycle
Waiting => Running => Terminated

#### Terminating Gracefully
Very important if you want your process to handle cleaning up correctly (e.g. releasing DB locks)

Forced termination may cause downtime

`SIGTERM` = gentle poke

`SIGKILL` = forceful kill

#### Termination lifecycle
Set grace period, enter terminating state, stop getting traffic

Execute prestop hook, if present

After grace period ends, `SIGKILL` is sent

### Health Probe Pattern

### Self-Healing Containers
Kubelet brings up containers and keeps them running

Restarts contains if it becomes unhealthy

#### Problems
What is app stops working without its main process dying?

### Probes
Periodically performed by kubelet.

#### Readiness probe
Can tell kubelet whether the container is ready for requests or not.

#### Startup probe
Tells kubelet that a slow app is in a ready state
