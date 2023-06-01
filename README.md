# [helm-chart](https://github.com/jupyterhub/helm-chart)

[![GitHub](https://img.shields.io/badge/issue_tracking-github-blue?logo=github)](https://github.com/jupyterhub/helm-chart/issues)
[![Discourse](https://img.shields.io/badge/help_forum-discourse-blue?logo=discourse)](https://discourse.jupyter.org/c/jupyterhub/z2jh-k8s)
[![Gitter](https://img.shields.io/badge/social_chat-gitter-blue?logo=gitter)](https://gitter.im/jupyterhub/jupyterhub)

This repository stores in its [`gh-pages`
branch](https://github.com/jupyterhub/helm-chart/tree/gh-pages) _packaged_ Helm
charts for [BinderHub][] and [Zero to JupyterHub K8s][]. These packaged Helm
charts are made available as a valid [Helm chart
repository](https://helm.sh/docs/chart_repository/) on [an automatically updated
website](https://hub.jupyter.org/helm-chart/) thanks to [GitHub Pages][].
We use [chartpress][] to add package and add Helm charts to this Helm chart
repository.


## Usage

This Helm chart repository enables you to install a JupyterHub and BinderHub
Helm chart directly from it into your Kubernetes cluster. Please refer to the
[JupyterHub Helm chart documentation](https://z2jh.jupyter.org) or the
[BinderHub Helm chart documentation](https://binderhub.readthedocs.io) for all
the additional details required.

```shell
# Let helm the command line tool know about a Helm chart repository
# that we decide to name jupyterhub.
helm repo add jupyterhub https://hub.jupyter.org/helm-chart/
helm repo update

# Simplified example on how to install a Helm chart from a Helm chart repository
# named jupyterhub. See the Helm chart's documentation for additional details
# required.
helm install jupyterhub/<helm chart name> --version <helm chart version>
```


## Release notes

### The JupyterHub Helm chart

[![Latest stable release of the Helm chart](https://img.shields.io/badge/dynamic/json.svg?label=Latest%20stable%20release&url=https://hub.jupyter.org/helm-chart/info.json&query=$.jupyterhub.stable&logo=helm&logoColor=white)](https://hub.jupyter.org/helm-chart#jupyterhub)
[![Latest pre-release of the Helm chart](https://img.shields.io/badge/dynamic/json.svg?label=Latest%20pre-release&url=https://hub.jupyter.org/helm-chart/info.json&query=$.jupyterhub.pre&logo=helm&logoColor=white)](https://hub.jupyter.org/helm-chart#development-releases-jupyterhub)
[![Latest development release of the Helm chart](https://img.shields.io/badge/dynamic/json.svg?label=Latest%20dev%20release&url=https://hub.jupyter.org/helm-chart/info.json&query=$.jupyterhub.latest&logo=helm&logoColor=white)](https://hub.jupyter.org/helm-chart#development-releases-jupyterhub)

For an extensive list of the released versions, click the badge above!

Each JupyterHub Helm chart release utilizes a specific version of [JupyterHub][]
and [KubeSpawner][] and requires a minimum [Kubernetes][] version as well as a
minimum [Helm][] version to function properly.

For detailed information about what Python libraries and other packages are
available alongside JupyterHub, inspect files such as `Dockerfile` and
`requirements.txt` within the [images
folder](https://github.com/jupyterhub/zero-to-jupyterhub-k8s/tree/main/images).

### The BinderHub Helm chart

[![Latest development release of the Helm chart](https://img.shields.io/badge/dynamic/json.svg?label=Latest%20dev%20release&url=https://hub.jupyter.org/helm-chart/info.json&query=$.binderhub.latest&logo=helm&logoColor=white)](https://hub.jupyter.org/helm-chart/#development-releases-binderhub)

For an extensive list of the released versions, click the badge above!

BinderHub's Helm chart use JupyterHub's Helm chart as a dependency. That means
that each BinderHub use a specific version of JupyterHub's Helm chart, along
with BinderHub specific components like the [BinderHub Python
package](https://github.com/jupyterhub/binderhub/tree/main/binderhub) itself
and [repo2docker][].

For detailed information about what Python libraries and other packages are
available alongside BinderHub, inspect files such as `Dockerfile` and
`requirements.txt` within the [images
folder](https://github.com/jupyterhub/binderhub/tree/main/helm-chart/images).

Currently, the BinderHub Helm chart does not tag releases though, so making a
similar comparison to the one above is hard.

## Local development of GitHub page

### Background knowledge

To locally development the GitHub page for this repostiory, some background
understanding can be useful. A good start is to read [Helm's documentation about
Helm chart repositories](https://helm.sh/docs/chart_repository). After that,
keep this in mind.

- [GitHub Pages][] relies on [Jekyll][] that in turn use the [Liquid][] templating
  language (with some [additions](https://jekyllrb.com/docs/liquid/)) to
  generate and host static web pages.
- Everything that is to be used to generate [the GitHub
  Page](https://hub.jupyter.org/helm-chart/) is required to reside at the
  [`gh-pages` branch](https://github.com/jupyterhub/helm-chart/tree/gh-pages).
- Templates get data from a [Jekyll Data
  Folder](https://jekyllrb.com/docs/datafiles/#the-data-folder) that you can
  [inspect here](https://github.com/jupyterhub/helm-chart/tree/gh-pages/_data).
  This folder only contains a symlink file that in turn points to
  [index.yaml](https://github.com/jupyterhub/helm-chart/blob/gh-pages/index.yaml)
  which is a [important file for a Helm chart
  repository](https://helm.sh/docs/chart_repository/#the-index-file).
- [index.md](https://github.com/jupyterhub/helm-chart/blob/gh-pages/index.md)
  file will be converted to index.html by Jekyll and act as a Human readable
  page.
- [_config.yml](https://github.com/jupyterhub/helm-chart/blob/gh-pages/_config.yml)
  is a [Jekyll configuration file](https://jekyllrb.com/docs/configuration/).
- [Gemfile](https://github.com/jupyterhub/helm-chart/blob/gh-pages/Gemfile) acts
  like a `doc-requirements.txt` but for Ruby, allowing us to work with Jekyll
  locally a bit easier.
- [info.json](https://github.com/jupyterhub/helm-chart/blob/gh-pages/info.json)
  is a way for us to provide easy access to information from the templates
  underlying data source, the
  [index.yaml](https://github.com/jupyterhub/helm-chart/blob/gh-pages/index.yaml)
  file. We are for example using the rendered info.json to create the badges you
  find in this readme about the latest stable/pre/dev release.

### Setting up for local development

There are probably different ways to go about this, but sometimes what matters
is to have one at all. Doing the following was tested by @consideRatio
2019-10-19 on Ubuntu 19.04.

1. Install Ruby, Gem, and Bundler.

   1. Install [`rbenv`](https://github.com/rbenv/rbenv#installation).
   1. Install the [rbenv-build plugin](https://github.com/rbenv/ruby-build#installation) to allows you to use `rbenv install`.
   1. Run `rbenv install <version>` with the [latest stable version](https://www.ruby-lang.org/en/downloads/).
   1. Run `rbenv global <version>`.
   1. Verify you can run `ruby -v` and `gem -v`.
   1. Run `gem install bundler` to work with Gemfiles etc.

1. Install Jekyll.

   1. Checkout the `gh-pages` branch with `git checkout gh-pages`.
   1. Run `bundle install`

1. Start a local webserver.

   1. Run `bundle exec jekyll serve`.
   1. Visit http://localhost:4000.

[Kubernetes]: https://kubernetes.io
[Helm]: https://helm.sh
[Chartpress]: https://github.com/jupyterhub/chartpress
[JupyterHub]: https://github.com/jupyterhub/jupyterhub
[Zero to JupyterHub K8s]: https://github.com/jupyterhub/zero-to-jupyterhub-k8s
[KubeSpawner]: https://github.com/jupyterhub/kubespawner
[BinderHub]: https://github.com/jupyterhub/binderhub
[repo2docker]: https://github.com/jupyter/repo2docker
[GitHub Pages]: https://pages.github.com/
[Jekyll]: https://jekyllrb.com
[Liquid]: https://shopify.github.io/liquid/
