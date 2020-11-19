## Meta
Sched URL: https://kccncna20.sched.com/event/ek9i/clean-up-your-room-what-does-it-mean-to-delete-something-in-k8s-aaron-alpar-kasten

Youtube URL:

## Clean Up Your Room! What Does It Mean to Delete Something in K8s - Aaron Alpar, Kasten

Talking everything k8s delete.

Finalizers. Owner references.

### Finalizers
- Keys on resources that signal pre-delete operations
- "dead" finalizers can prevent deletion. Finalizer strings that the controller does not understand or deal with.
- Knowledge of finalizers is useful

### Live Finalizer Demo
When deleting, a finalizer will add metadata.

Once manually created finalizer key is deleted, the delete successfully completes.

Common finalizers include finalizers for PV and PVCs.

### Owner References
- Child resource objects can be reference parents
- Trees of resources may be deleted
- Finalizer rules are followed
- `ownerReference` fields
- Parent/child relationship
- If child is deleted, just the child is deleted.
- If parent is deleted, child AND parent is deleted (even though k8s CLI may JUST say that the parent is deleted).

### Owner References - Cascade
- `--cascade=false` option available for `kubectl delete` operation. Orphans children.

### Owner References - propagationPolicy
1. Foreground: children deleted before parent (postorder)
1. Background: parent is deleted before children (preorder)
1. Orphan: parent is deleted

### Summary
- Finalizers will prevent deletion of resources
- Generally a reason for finalizer
- Owner reference establishes tree relation

### Q&A
Finalizer needs a controller to validate the finalizer. If you want to create a custom finalizer, you also need to also create a custom controller.
