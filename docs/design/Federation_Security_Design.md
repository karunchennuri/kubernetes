<!-- BEGIN MUNGE: UNVERSIONED_WARNING -->

<!-- BEGIN STRIP_FOR_RELEASE -->

<img src="http://kubernetes.io/kubernetes/img/warning.png" alt="WARNING"
     width="25" height="25">
<img src="http://kubernetes.io/kubernetes/img/warning.png" alt="WARNING"
     width="25" height="25">
<img src="http://kubernetes.io/kubernetes/img/warning.png" alt="WARNING"
     width="25" height="25">
<img src="http://kubernetes.io/kubernetes/img/warning.png" alt="WARNING"
     width="25" height="25">
<img src="http://kubernetes.io/kubernetes/img/warning.png" alt="WARNING"
     width="25" height="25">

<h2>PLEASE NOTE: This document applies to the HEAD of the source tree</h2>

If you are using a released version of Kubernetes, you should
refer to the docs that go with that version.

<!-- TAG RELEASE_LINK, added by the munger automatically -->
<strong>
The latest release of this document can be found
[here](http://releases.k8s.io/release-1.4/docs/design/federation-phase-1.md).

Documentation for other releases can be found at
[releases.k8s.io](http://releases.k8s.io).
</strong>
--

<!-- END STRIP_FOR_RELEASE -->

<!-- END MUNGE: UNVERSIONED_WARNING -->

# Ubernetes Federation Security

Author: Karun Chennuri (karun.chennuri@huawei.com)

## INTRODUCTION

In this document we propose a design for the “Security at Ubernetes level (Federation Control Plane)”. For background of the federation please refer to [this proposal] (../../docs/proposals/federation.md) & [this design] (../../docs/design/federation-phase-1.md). 

This document outlines -

* List of scenarios and use cases that motivate ubernetes security.
* Usecases that drive the design and also verifies the design.
* List of functional requirements derived from the use cases.
* Proposed architecture, API and building blocks.
* Various activity flows how the build blocks work together to support use cases.

## REQUIREMENTS

+ **Ubernetes Authentication:** Authenticate users using certificate, token files or against identity stores running external to the Ubernetes.
+ **Ubernetes Authorization:** Role Based Access Control (RBAC) user operations using 
+ **Cluster-level Authentication:** Per user based authentication on the underlying cluster. User of FCP should be uniquely identifiable in the cluster level.
+ **Cluster-level Authorization:** Per user based authorization on the underlying cluster. User of FCP should be authorized at the cluster level before allowing user to perform an operation.
+ **Federation of user identities:** 
+ **Federation of Role mapping:** Roles of ubernetes level should be mapped to roles of cluster level, before authorization takes place at the cluster level.
+ **Sensitive workloads:** Some workloads can only run on a particular cluster. They cannot be scheduled to or migrated to other clusters. 

## ASSUMPTIONS

Following assumptions have been made for the design. Any challenge to the below assumptions would affect the design and to be reworked.
So it's importat to understand whether they are safe assumptions or not.
* Clusters running on different cloud providers
* Underlying kubernetes cluster that are geographically seperated has authorization mechanism based on RBAC.
* (for only certain design approaches) Cluster level authentication is based on Keystone.


## USE CASES

## SCOPE

## ARCHITECTURE

### APPROACH 1
In approach 1 we have a separate identity store at the FCP level. 

![Federation Security Architecture](FCP_authn_authz_flow.png)

![FCP security flow](FCP_Design_1.png)

### APPROACH 2


Some design principles we are following in this approach:



