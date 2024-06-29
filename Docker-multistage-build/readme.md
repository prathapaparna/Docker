# multi-stage-build
- Multi-stage builds in Docker are a way to use multiple FROM statements in your Dockerfile. This allows you to create intermediate images that can be discarded, keeping the final image lightweight. Multi-stage builds are particularly useful for optimizing the build process by separating the build environment from the runtime environment.

## Dockerfile stages
### Stage 1: Builder Stage
```
- FROM golang:1.18 as builder:  Use the official Go image as the base for the build stage and name it builder.
- WORKDIR /app:  Set the working directory inside the container to /app.
- COPY main.go .:  Copy the main.go file from the host to the container.
- RUN go build -o main .:  Compile the Go application and produce a binary named main.
```
### Stage 2: Runtime Stage
```
- FROM alpine:latest: Use the official Alpine Linux image as the base for the final image.
- WORKDIR /app: Set the working directory inside the container to /app.
- COPY --from=builder /app/main .: Copy the binary from the builder stage to the current stage.
- CMD ["./main"]: Define the command to run the application when the container starts.
```
- ![image](https://github.com/prathapaparna/Docker/assets/99127429/3dd1aab6-8dc9-440f-9f7c-5ea42c42beb1)
- you can see the image size difference in image


## Advantages of Multi-Stage Builds
- Smaller Final Images: By using multi-stage builds, you can discard unnecessary build dependencies and files, resulting in a smaller final image.
- Improved Security: Reducing the number of components in the final image minimizes the attack surface.
- Cleaner Separation: Separating the build and runtime environments allows for cleaner and more maintainable Dockerfiles.
