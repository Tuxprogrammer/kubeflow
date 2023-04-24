TAG ?= $(shell git describe --tags --always --dirty)
REGISTRY ?= tuxhpc

docker-build-base:
	$(MAKE) docker-push -C ../base TAG=${TAG}

docker-build: docker-build-base
	docker build -t ${REGISTRY}/codeserver:${TAG} --build-arg BASE_IMG=${REGISTRY}/base:${TAG} -f Dockerfile . 

docker-push: docker-build
	docker push ${REGISTRY}/codeserver:${TAG}
