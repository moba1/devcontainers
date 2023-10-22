BASE_IMAGE := ghcr.io/moba1/devcontainers/base/ubuntu

.PHONY: all
all: build

.PHONY: build
build:
	docker buildx build \
		--build-arg "BASE_IMAGE_VERSION=$(BASE_IMAGE_VERSION)-$(UBUNTU_VERSION)" \
		-t "$(BASE_IMAGE):$(VERSION)-$(UBUNTU_VERSION)" \
		--platform linux/amd64,linux/arm64 \
		--push \
		.

.PHONY: build-latest
build-latest:
	docker buildx build \
		--build-arg BASE_IMAGE_VERSION=latest \
		-t "$(BASE_IMAGE):latest" \
		--platform linux/amd64 \
		--push \
		.

.PHONY: clean
clean:
	-docker buildx prune -f -a