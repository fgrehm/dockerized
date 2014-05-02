FROM fgrehm/devstep-standalone:0.0.1

# Heroku toolbelt
RUN wget -qO- https://toolbelt.heroku.com/install-ubuntu.sh | sh

# Rebuild project based on this Dockerfile
ONBUILD ADD . /workspace
ONBUILD WORKDIR /workspace
ONBUILD RUN CLEANUP=1 /.devstep/bin/devstep-build /workspace
