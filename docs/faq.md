# Frequently Asked Questions (FAQ)

## What is the difference between Open Application Model and Scylla?

*Open Application Model* is a specification for describing applications.
*Scylla* is an implementation of the Open Application Model specification. Scylla runs on Kubernetes, though Open Application Model can be implemented on non-Kubernetes platforms.

## What do Open Application Model and Scylla add to the cloud native landscape?

Open Application Model is designed to introduce separation of concerns (SoC) into Kubernetes.

In Kubernetes today, developer information is freely intermingled with operator information. We wanted to create a way to distinguish between these two rolls so that developers could deliver an artifact that describes their microservice, and operators could apply another artifact that configures and instantiates that microservice.

In the hydra model, a `ComponentSchematic` describes a developer's view of a microservice, and an `ApplicationConfiguration` describes an application operator's view of how a component is deployed into the cluster.

## How does this compare to Knative?

We do not believe we are trying to solve the same problem as Knative.

## Can I use Open Application Model/Scylla to deploy existing applications?

You can describe existing applications as Open Application Model applications. See our [migration guide](migrating.md).

## How does this compare to Helm or Kompose?

Helm is a package manager for Kubernetes, and provides a way to package and distribute Kubernetes applications.

Open Application Model is just an application model that, thanks to Scylla, runs on Kubernetes. You can bundle your Open Application Model applications as Helm charts and deploy them using Helm.

Kompose is a tool for manipulating Kubernetes YAML documents. It is also compatible with Open Application Model/Scylla.

## Can I write my own traits?

Currently, all traits are built into Scylla. However, our plan is to make it possible for custom traits to be written and deployed into a Scylla cluster.

If you write a custom trait and integrate it with Scylla, consider opening a pull request. We are interested in adding more traits.

## Can I write my own scopes?

Currently, no. Scopes are fixed according to the Open Application Model spec.

## Does Scylla support "extended workload types" as described in the Open Application Model specification

No. That section of the specification is a draft, and we are not yet supporting it.