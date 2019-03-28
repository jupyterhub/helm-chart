# [helm-chart](https://github.com/jupyterhub/helm-chart)

[![Join the chat at https://gitter.im/jupyterhub/binder](https://badges.gitter.im/jupyterhub/binder.svg)](https://gitter.im/jupyterhub/binder?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

This repository stores Helm chart tarballs for BinderHub and JupyterHub. While
this repo is a store of Helm chart tarballs, **actual development** of the Helm
charts takes place in the [BinderHub][] and [Zero to JupyterHub][] repos. These
[Helm][] charts are used with [Kubernetes][] deployments of [BinderHub][] and
[JupyterHub][].

## Charts

The [`gh-pages` branch of this repo](https://github.com/jupyterhub/helm-chart/tree/gh-pages)
contains the latest helm charts for BinderHub and JupyterHub. It also contains
historical charts as well.

[Website with an index of all charts](https://jupyterhub.github.io/helm-chart/)

## Versions coupled to each chart release

Each JupyterHub Helm chart release utilizes a specific version of JupyterHub and
requires at least a certain Kubernetes version and Helm version to function
properly.

For detailed information about what libraries are available alongside JupyterHub
in the hub pod, see the associated `Dockerfile` or `requirements.txt`.

| Helm Chart v. | JupyterHub v. | Req. Kubernetes v. | Req. Helm v. | Associated files
| ------ | ------ | ------ | ------- | ------ |
| 0.8.1  | 0.9.5  | 1.11+  | 2.11.0+ | [0.8.1](https://github.com/jupyterhub/zero-to-jupyterhub-k8s/blob/0.8.1/images/hub) |
| 0.7.0  | 0.9.2  | 1.8+   | 2.9.0+  | [0.7.0](https://github.com/jupyterhub/zero-to-jupyterhub-k8s/blob/0.7.0/images/hub) |
| v0.6   | 0.8.1  | ?      | ?       | [v0.6](https://github.com/jupyterhub/zero-to-jupyterhub-k8s/blob/v0.6/images/hub) |
| v0.5   | 0.8.1  | ?      | ?       | [v0.5](https://github.com/jupyterhub/zero-to-jupyterhub-k8s/blob/v0.5/images/hub) |
| v0.4   | 0.7.2  | ?      | ?       | [v0.4](https://github.com/jupyterhub/zero-to-jupyterhub-k8s/blob/v0.4/images/hub) |
| v0.3.1 | 0.7.2  | ?      | ?       | [v0.3.1](https://github.com/jupyterhub/zero-to-jupyterhub-k8s/blob/v0.3.1/images/hub) |
| v0.3   | 0.7.2  | ?      | ?       | [v0.3](https://github.com/jupyterhub/zero-to-jupyterhub-k8s/blob/v0.3/images/hub) |

## Usage

Please refer to the following documentation for instructions on the
use of these helm charts:

- [BinderHub documentation](https://binderhub.readthedocs.io)
- [Zero to JupyterHub documentation **v0.4-doc**](http://zero-to-jupyterhub.readthedocs.io/en/v0.4-doc/)


## Links to related repos

- [BinderHub][]
- [Zero to JupyterHub][]
- [JupyterHub][]
- [repo2docker](https://github.com/jupyter/repo2docker)

## Questions

Visit us to
[![Join the chat at https://gitter.im/jupyterhub/binder](https://badges.gitter.im/jupyterhub/binder.svg)](https://gitter.im/jupyterhub/binder?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge).

[Kubernetes]: https://kubernetes.io
[Helm]: https://helm.sh
[BinderHub]: https://github.com/jupyterhub/binderhub
[JupyterHub]: https://github.com/jupyterhub/jupyterhub
[Zero to JupyterHub]: https://github.com/jupyterhub/zero-to-jupyterhub-k8s
