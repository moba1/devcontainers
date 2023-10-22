IMAGE := ghcr.io/moba1/devcontainers/base/ubuntu
VERSION := latest

.PHONY: all
all: build

.PHONY: build
build:
	docker buildx build \
		--build-arg UBUNTU_VERSION=$(UBUNTU_VERSION) \
		-t "$(IMAGE):$(VERSION)-$(UBUNTU_VERSION)" \
		--platform linux/amd64,linux/arm64 \
		--push \
		.

.PHONY: clean
clean:
	-docker buildx prune -f -a