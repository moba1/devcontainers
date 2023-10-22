BASE_IMAGE := ghcr.io/moba1/devcontainers/base/debian
IMAGE := ghcr.io/moba1/devcontainers/nix/debian

.PHONY: all
all: build

.PHONY: build
build:
	docker buildx build \
		--build-arg "BASE_IMAGE_VERSION=$(BASE_IMAGE_VERSION)-$(DEBIAN_VERSION)" \
		-t "$(IMAGE):$(VERSION)-$(DEBIAN_VERSION)" \
		--platform linux/amd64 \
		--push \
		.

.PHONY: build-latest
build-latest:
	docker buildx build \
		--build-arg BASE_IMAGE_VERSION=latest \
		-t "$(IMAGE):latest" \
		--platform linux/amd64 \
		--push \
		.

.PHONY: clean
clean:
	-docker buildx prune -f -a