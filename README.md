![CB Logo](https://www.couchbase.com/webfiles/1552355627964/images/couchbase_logo.svg)

# Couchbase NoSQL Summit Workshop Setup
#### Couchbase Autonomous Operator Deployment Script 

This script deploys the Couchbase Autonomous Operator into an existing Kubernetes Cluster.

The script is comprised of the following components:

* eks_script.py 	-- Main Script
* parameters.py  -- Parameter File
* resources		-- Yaml files used to deploy CB Operator

## Prerequisites

This script requires that you have an existing Kubernetes Cluster.  This can be either OpenShift, EKS, AKS, GKE, Minishift, Minikube.  For information on setting up a kubernetes cluster please refer to the following:

#### EKS
<https://github.com/couchbaselabs/cbsummit-create-eks-cluster.git>

#### OpenShift
<https://docs.openshift.com/container-platform/4.1/welcome/index.html>

<https://try.openshift.com>

## Usage

The script can be run as follows:

```
python eks_script.py [--create-crd] [--create-cb-cluster] [--no-couchmart] [-h|--help]
version: 1.0.0

	--create-crd  		== Create the cluster level resources such as CRD and ClusterRole
	--create-cb-cluster	== Create the couchbase cluster automatically
	--no-couchmart		== Disable creation of the Couchmart demo application pod
```

**--create-crd does require elevated privileges  as this will deploy cluster level resources**


## Parameters

The parameter file consists of the following parameters

|Parameter             | Description                                      |
|:---------------------|:------------------------------------------------:|
|COMMAND                | The command to use for execution. Either **kubectl** or **oc**|
|OPERATOR_VERSION	| The version of the Couchbase Autonmous Operator to use|
|NS_ATTEMPTS				| The amount of attempts the script will check to see if the provided namespace was already created|
|NS\_WAIT\_VARIANCE	   | The wait variance between checks on the name space.  This will be a random value between 1 and NS\_WAIT\_VARIANCE|
|CM\_WAIT\_TIME\_SEC	| The time to wait between checks to see if the Couchmart pod was succesfully created|
|CM\_RETRY\_ATTEMPTS	| The amount of checks to make to see if the Couchmart pod was succesfully created|

## Resources

Please refer to the Couchbase Autonomous Operator Documentation for more details on the Operator and corresponding yaml files.  The documentation can be found at <https://docs.couchbase.com/operator/1.1/overview.html>

## Tested Environments

The following environments have been tested

* EKS
* OpenShift 4.1



 

