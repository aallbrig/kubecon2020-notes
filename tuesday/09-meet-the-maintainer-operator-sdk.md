## Meta
Sched URL: https://kccncna20.sched.com/event/fMW6/meet-the-maintainer-operator-sdk
Youtube URL:

## Meet the Maintainer: Operator SDK
[introducing the operator framework](https://coreos.com/blog/introducing-operator-framework)

[operator-framework/operator-lifecycle-manager](https://github.com/operator-framework/operator-lifecycle-manager) (AKA OLM).

Kubebuilder is a dependency of operator SDK (interesting). Package using kustomize that is used to generate a bundle image. Can be deployed via OLM. You can pipe the output of kustomize into helm to generate helm charts.

How does one get their operator into the operator.io registry? Create an operator. Generate an operator bundle. Visit operatorhub.io where there is a "submit your operator" link. Submit your PR to https://operatorhub.io/contribute

Local testing of your operator is possible!

Recommendation for talk: being a good citizen of a multi operator world.
