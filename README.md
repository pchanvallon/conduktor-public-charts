<a name="readme-top" id="readme-top"></a>

<p align="center">
  <img src="https://avatars.githubusercontent.com/u/60062294?s=200&v=4" width="256px" />
</p>
<p align="center">
    <strong>Official repository for Conduktor Helm Charts</strong>
</p>

<p align="center">
    <a href="https://docs.conduktor.io/platform/installation/get-started/kubernetes/"><strong>Explore the docs 
»</strong></a>
    <br />
    <br />
    <a href="https://github.com/conduktor/conduktor-public-charts/issues">Report Bug</a>
    ·
    <a href="https://github.com/conduktor/conduktor-public-charts/issues">Request Feature</a>
</p>

## Prerequisites

- Kubernetes 1.19+
- [Helm](https://helm.sh/docs/intro/install/) 3.2.0+

## Charts

- console ([doc](charts/console/README.md), [values](charts/console/values.yaml))
- conduktor-gateway ([doc](charts/gateway/README.md), [values](charts/gateway/gateway/values.yaml))

## Usage

```shell
$ helm repo add conduktor https://helm.conduktor.io
$ helm repo update
```

For guides and advanced help, please refer to our
[documentation](https://docs.conduktor.io/platform/installation/get-started/kubernetes),
or to our charts `README`.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Development setup

**Requirements**:
- [k3d](https://k3d.io/v5.6.0/#installation)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [helm](https://helm.sh/docs/intro/install/)

You can have a working cluster on your local machine with docker and k3d, 
use the Makefile target `k3d-up` to start a cluster with nginx and a postgresql
database running.

```shell
$ make helm-deps
$ make k3d-up
```

*Postgresql credentials:*

```yaml
host: postgresql.conduktor
port: 5432
username: postgres
password: conduktor
name: conduktor
```

### Run chart tests
You need to have [chart-testing](https://github.com/helm/chart-testing) installed and a running kubernetes cluster.

```shell
# Update helm dependencies
make helm-deps
# Create local K3D cluster for test and local dev (require k3d, helm and kubectl)
make k3d-up
# Run Chart-testing tests on chart that contain changes (require chart-testing and helm)
make test-chart
# Delete K3D cluster
make k3d-down
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>
