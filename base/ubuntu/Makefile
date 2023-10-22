UBUNTU_VERSION := latest
VERSION := latest
IMAGE := ghcr.io/moba1/devcontainers/base

.PHONY: all
all: build

.PHONY: build
build: build-ubuntu

.PHONY: build-ubuntu
build:
	docker buildx build \
		-f Dockerfile.ubuntu \
		--build-arg UBUNTU_VERSION=$(UBUNTU_VERSION) \
		-t "$(IMAGE):$(VERSION)" \
		--platform linux/amd64,linux/arm64 \
		--push \
		.

.PHONY: clean
clean:
	-docker buildx prune -f -a