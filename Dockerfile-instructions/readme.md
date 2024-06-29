# Dockerfile
A Dockerfile is a text file that contains a series of instructions on how to build a Docker image. These instructions are executed sequentially, and each instruction creates a new layer in the Docker image

FROM           ## Sets the base image for the subsequent instructions.
LABEL          ## Adds metadata to an image in the form of key-value pairs. EX: LABEL maintainer="you@example.com"
RUN            ## Executes commands while creating an image
COPY           ## Copies files or directories from the host machine to the image.
ADD            ## Similar to COPY but with additional features such as extracting tar files and fetching files from URLs.
ENV            ## Sets environment variables ex: ENV APP_ENV=production
ARG            ## Defines a build-time variable.  ex: ARG VERSION=1.0.0
WORKDIR        ## Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, and ADD instructions that follow.
EXPOSE         ## Informs Docker that the container listens on the specified network ports at runtime
USER           ## Sets the user name or UID to use when running the image and for any RUN, CMD, and ENTRYPOINT instructions that follow.
CMD           ## Specifies the default command to run when a container is started from the image. This instruction can be overridden by passing a command to docker run.
ENTRYPOINT    ## Configures a container that will run as an executable.
SHELL         ## Allows the default shell used for the shell form of commands to be overridden.
HEALTHCHECK   ## Tells Docker how to test the container to check that it is still working. ex: HEALTHCHECK --interval=5m --timeout=3s CMD curl -f http://localhost/ || exit 1
ONBUILD       ## Adds a trigger instruction to the image that will be executed when the image is used as the base for another build.ex: ONBUILD ADD . /app/src
VOLUME        ## Creates a mount point with the specified path and marks it as holding externally mounted volumes from the host or other containers.

