# [JupyterHub Helm Chart](https://github.com/jupyterhub/helm-chart)

[![Documentation Status](https://readthedocs.org/projects/zero-to-jupyterhub/badge/?version=latest)](http://zero-to-jupyterhub.readthedocs.io/en/latest/?badge=latest)

A [helm][] [chart][] for deploying [JupyterHub] instances on [Kubernetes].

**[Zero to JupyterHub with Kubernetes]** provides detailed instructions for using this project within a JupyerHub deployment.

## Overview of [Kubernetes] terminology

### What is [helm]?

[helm] is the Kubernetes package manager. [Helm] streamlines  installing and managing Kubernetes applications. *Reference: [helm repo]*

### What is a [chart]?

Charts are Helm packages that contain at least two things:

- A description of the package (`Chart.yaml`)
- One or more **templates**, which contain Kubernetes manifest files

*Reference: [Kubernetes Introduction to charts]*

## Contents of this repository
### `jupyterhub` folder

Fundamental elements of a chart including:

- `templates` folder
- `Chart.yaml.template`
- `values.yaml`

### `images` folder

Docker images for applications including:

- `builder`
- `hub`
- `proxy`
- `singleuser-sample`

### `Makefile`

Useful for compiling custom charts.

## Usage

To build and push Docker images in the `images` directory:

    make images

To create chart metadata and package chart for use:

    make chart


## History and inspiration

Much of the intial groundwork for this is information learned from
the successful use of JupyterHub and Kubernetes at UC Berkeley in their
[Data 8](http://data8.org/) program.

## Documentation hosting

We will host the documentation on Read The Docs as we move forward and may also
host a mirror at a the corresponding
website (see the link at the top of our github repo page).
The [JupyterHub project documentation](https://jupyterhub.readthedocs.io) as well
as documentation about authenticators, spawners, and services can be found on
ReadTheDocs.

## Contributors

Thank you to the following contributors:

- Aaron Culich
- Carol Willing
- Chris Holdgraf
- Min RK
- Ryan Lovett
- Yuvi Panda

Future contributors are encouraged to add themselves to this README file too.
[JupyterHub]: https://jupyterhub.readthedocs.io/en/latest/
[Kubernetes]: https://kubernetes.io
[helm]: https://helm.sh/
[helm repo]: https://github.com/kubernetes/helm
[chart]: https://github.com/kubernetes/helm/blob/master/docs/charts.md
[Kubernetes Introduction to charts]: https://github.com/kubernetes/helm/blob/master/docs/charts.md
[Zero to JupyterHub with Kubernetes]: https://zero-to-jupyterhub.readthedocs.io/en/latest/
