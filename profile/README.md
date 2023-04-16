# Infrastructure Made Easy

As a group of engineers focusing on creating developer platforms, we found ourselves consistently
asking the same question: _how do we make the creation and management of infrastructure simple and
efficient?_

Simple question, not so simple to answer! When we first began talking amongst ourselves, we always
hoped that someone would have a concrete answer, but the only thing we found was that we all had
difficulty coming up with one. Our experience convinced us that this was a problem worth considering
and exploring.

This GitHub organization is our attempt to publicize our experiments and thoughts around this
question. We have no answer, but we hope you'll follow along as we stumble through.

## Tenets

### Define Infrastructure as Code

There is a reason that [the Infrastructure as Code
movement](https://www.hashicorp.com/resources/what-is-infrastructure-as-code) has gained so much
popularity in recent years. Ensuring that we define infrastructure in code has many advantages, such
as:

- It ensures consistency when we provision infrastructure across many environments and regions.
- It allows the construction of reusable components that define small, single-use pieces of
  infrastructure, which can then be composed into larger units, much like using libraries in
  application code.
- It enables infrastructure provisioning and ongoing management to be automated in the same way as
  we build and release software.
- It allows for versioning the definition of your infrastructure, potentially in
  concert/coordination with the software running on the infrastructure.

For these reasons, we reject any solution that does not allow us to generate, export, or write the
definition of infrastructure in a form compatible with version-controlled storage.

### Do Not Force Provider Choice

We do not consider solutions that are inherently proprietary or useful only in the context of a
single cloud provider since this limits their usefulness and leads to the necessity of learning
multiple languages/frameworks.

### Favor Declarative Over Imperative

We favor tools that follow a declarative versus an imperative approach. Imperative tools require
users to consider _how to achieve a desired state_, whereas declarative tools only require users to
_describe the desired result_. For example, imperative tooling requires users to consider factors
such as idempotence, in-place mutation, and ongoing state management. By contrast, declarative tools
manage this for you.

### Do Not Require Developers to Learn New Languages

One of our goals is to not force developers into learning new languages or frameworks that may not
benefit them in their day-to-day work. For example, consider a developer the organization asks to
focus much time and effort on writing highly scalable and efficient (Golang | Java | Typescript |
etc.). To force them, by way of having no better alternative, to also learn a framework such as
Terraform may well detract from their ability to perform their primary job function. As such, we
favor approaches that enable developers to provision and manage their infrastructure either in a
language of their choice or using ubiquitously available and used languages or formats, such as JSON
or YAML.

**Note:** We are not explicitly suggesting that developers whose primary role is writing application
layer code _must not_ or _should not_ also work on the skills required to write high-performance
infrastructure as code. Neither are the two skill sets inherently incompatible. Based on our own
experience working with teams, adding the expectation of managing infrastructure using lower-level
primitives _on top of_ the pressures and demands of being a high-performing application developer
contributes to unhealthy levels of stress and burnout.

### Abstract Away Complexity

Managing infrastructure at scale with global redundancy and high availability is a specialized and
time-consuming skill to achieve and maintain. We seek to offload this task onto technical engineers
who focus on these problems while allowing developers to instead focus on achieving their
applications' maximum performance and availability. As such, we favor solutions enabling the
complexity of redundant and highly performant infrastructure behind a simple interface that
developers can understand without knowledge of the underlying infrastructure.