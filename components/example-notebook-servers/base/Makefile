TAG ?= $(shell git describe --tags --always --dirty)
REGISTRY ?= tuxhpc

docker-build:
	docker build -t ${REGISTRY}/base:${TAG} -f Dockerfile .

docker-push: docker-build
	docker push ${REGISTRY}/base:${TAG}
