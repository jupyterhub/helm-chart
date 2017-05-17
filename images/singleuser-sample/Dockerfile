FROM jupyter/base-notebook:cfddc5a3163f

# conda/pip/apt install additional packages here, if desired.

# Set working directory to $HOME, needed for persistence
# docker-stacks default is ~/work, which won't exist if we mount $HOME as a volume
WORKDIR $HOME

# select single-user launch command by default for JupyterHub:
CMD /usr/local/bin/start-singleuser.sh
