---
title: Massive Deployments on Amazon AWS with JVM
---

## Massive Deployments on Amazon AWS with JVM

Behrooz Nobakht

[\@behruz](https://twitter.com/behruz)

## Timeline

![](images/timeline.png)

## From *On-Premise* to *Managed*

![](images/deployment-method.png)

## What does *massive* mean?

![](images/massive-scale.png)

## What is a *server*?

### Development

* Um, huh?!
* ... *pause* ...
* We ship it to Ops.
* They deploy!

### Operation

* *What* version to install?
* *What* process to start?
* *Which* data to use?
* *How* to access logs?
* *How* to monitor processes?
* *How* to sync our infra; e.g. LB servers?

## 

**Server** abstraction 

is too *low-level* 

for our *development* and *operation*

## Server as an HTTP API

<div style="float:right;">
![](images/hexa.png)
</div>

* `/install`
* `/create`
* `/process`
* `/logs`
* `/monitor`
* `/resources`

## A JVM for a JVM
**Service Provider Interfaces (SPI)**

![](images/server.png)

* A few "factory" patterns
* Generic RESTful operations: logs, monitors, resources

## *Deployment* is a development responsibility

* Does it have `//:14777/`?
* SPI implemented?
* Tested and Integrated?
* Locally Deployable?
* Deliver to Ops.
* They Deploy!

## Does it really matter what's beneath `//:14777/` ?!

##

![](images/arch.png)

## 

* Infrastructure provides servers
* Every server boots with one `//:14777/`
* Auto-register server with Controller
* Controller synchronizes servers with load balancers
* Controller manages the *state* of servers
* Controller automates *workflows*

## How we benefit?

* Orchestration becomes automatic
* Relieve from *small* operation *details*
* Disaster Recovery
* Failure Mitigation
* Monitoring
* Horizontal Scaling

##

Operating *2000+* AWS servers

with an awesome small DevOps team

![](images/massive.png)

## 

![](images/sdl_fredhopper_logo.png)

<http://labs.sdl.com/fredhopper>

<https://github.com/sdl>
