
# Image URL to use for building/pushing image
IMAGE ?= aanogueira/curl
TAG ?= alpine-3.15.0

.PHONY: help
help: ## Display this help
	@awk 'BEGIN {FS = ":.*##"; printf "\nUsage:\n  make \033[36m<target>\033[0m\n"} /^[a-zA-Z_0-9-]+:.*?##/ { printf "  \033[36m%-15s\033[0m %s\n", $$1, $$2 } /^##@/ { printf "\n\033[1m%s\033[0m\n", substr($$0, 5) } ' $(MAKEFILE_LIST)

##@ Options

.PHONY: build
build: ## Build docker image
	docker build -t ${IMAGE}:${TAG} .

.PHONY: push
push: ## Push docker image
	docker push ${IMAGE}:${TAG}

.PHONY: all build push
all: build push  ## Build and push docker image
