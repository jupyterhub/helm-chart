FROM jupyter/base-notebook:cfddc5a3163f

# conda/pip/apt install additional packages here, if desired.

# pin jupyterhub to match the Hub verion
# set via --build-arg in Makefile
ARG JUPYTERHUB_VERSION=0.7.2
RUN pip install jupyterhub==$JUPYTERHUB_VERSION

# Set working directory to $HOME, needed for persistence
# docker-stacks default is ~/work, which won't exist if we mount $HOME as a volume
# FIXME: this becomes obsolete after https://github.com/jupyter/docker-stacks/pull/388
WORKDIR $HOME

# select single-user launch command by default for JupyterHub:
CMD /usr/local/bin/start-singleuser.sh
