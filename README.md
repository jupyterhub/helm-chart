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

## JupyterHub versions in each chart

Each JupyterHub Helm chart installs a specific version of components in the Jupyter
stack. Use the following table to determine which version of each component is
installed.

| Helm Chart version | JupyterHub version |
| ------ | ----- |
| 0.8.0  | 0.9.4 |
| 0.7.0  | 0.9.2 |
| v0.6   | 0.8.1 |
| v0.5   | 0.8.1 |
| v0.4   | 0.7.2 |
| v0.3.1 | 0.7.2 |
| v0.3   | 0.7.2 |

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
