# opensearch

This Ansible role is used to provision opensearch and opensearch-dashboards

This project is designed to operate using [**clusterverse**](https://github.com/clusterverse/clusterverse) to manage the base infrastructure.  Please see the [README.md](https://github.com/clusterverse/clusterverse/blob/master/README.md) there for detailed instructions on its usage. 

## Requirements
+ ansible-core >= 2.17.4 (pypi >= 10.4.0)
+ See [docs/EXAMPLE/Dockerfile](https://github.com/clusterverse/clusterverse/blob/master/docs/EXAMPLE/Dockerfile) for a full list of dependencies.

## Example
Please see the [EXAMPLE](https://github.com/clusterverse/opensearch/tree/master/EXAMPLE) directory in this repository for some basic configuration.  This can be copied in the root directory, and used as a starting point for your own configuration.

### Configuration
Cluster configuration is stored in `cluster_defs/**/cluster_vars[*].yml` files.
Application configuration is stored in `cluster_defs/**/app_vars.yml` files.

### Clusterverse supports three modes of operation:
+ [deploy.yml](https://github.com/clusterverse/opensearch/tree/master/EXAMPLE/deploy.yml) - Deploys a cluster from scratch, or repairs a cluster, or scales it up (note: not _down_).
  + e.g. `ansible-playbook -e buildenv=dev -e cloud_type=aws -e region=eu-west-1 deploy.yml`
+ [redeploy.yml](https://github.com/clusterverse/opensearch/blob/master/EXAMPLE/redeploy.yml) - Redeploys the cluster, replacing all the nodes entirely.
  + e.g. `ansible-playbook -e buildenv=dev -e cloud_type=aws -e region=eu-west-1 redeploy.yml`
+ [destroy.yml](https://github.com/clusterverse/opensearch/tree/master/EXAMPLE/destroy.yml) - Destroys the cluster,
  + e.g. `ansible-playbook -e buildenv=dev -e cloud_type=aws -e region=eu-west-1 destroy.yml`
