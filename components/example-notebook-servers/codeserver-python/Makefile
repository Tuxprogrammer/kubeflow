TAG ?= $(shell git describe --tags --always --dirty)
REGISTRY ?= tuxhpc-notebook

docker-build-codeserver:
	$(MAKE) docker-push -C ../codeserver TAG=${TAG}

docker-build: docker-build-codeserver
	docker build -t ${REGISTRY}/codeserver-python:${TAG} --build-arg BASE_IMG=${REGISTRY}/codeserver:${TAG} -f Dockerfile . 

docker-push: docker-build
	docker push ${REGISTRY}/codeserver-python:${TAG}
