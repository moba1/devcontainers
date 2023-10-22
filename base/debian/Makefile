IMAGE := ghcr.io/moba1/devcontainers/base/debian

.PHONY: all
all: build

.PHONY: build
build:
	docker buildx build \
		--build-arg BASE_IMAGE_TAG=$(BASE_IMAGE_TAG) \
		-t "$(IMAGE):$(VERSION)-$(BASE_IMAGE_TAG)" \
		--platform linux/amd64 \
		--push \
		.

.PHONY: build-latest
build-latest:
	docker buildx build \
		--build-arg BASE_IMAGE_TAG=latest \
		-t "$(IMAGE):latest" \
		--platform linux/amd64 \
		--push \
		.

.PHONY: clean
clean:
	-docker buildx prune -f -a