# multi-stage-build
- Multi-stage builds in Docker are a way to use multiple FROM statements in your Dockerfile. This allows you to create intermediate images that can be discarded, keeping the final image lightweight. Multi-stage builds are particularly useful for optimizing the build process by separating the build environment from the runtime environment.

## Advantages of Multi-Stage Builds
- Smaller Final Images: By using multi-stage builds, you can discard unnecessary build dependencies and files, resulting in a smaller final image.
- Improved Security: Reducing the number of components in the final image minimizes the attack surface.
- Cleaner Separation: Separating the build and runtime environments allows for cleaner and more maintainable Dockerfiles.
