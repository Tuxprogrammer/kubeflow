TAG ?= $(shell git describe --tags --always --dirty)
REGISTRY ?= tuxhpc

docker-build-jupyter:
	$(MAKE) docker-build -C ../jupyter TAG=${TAG} 

docker-build: docker-build-jupyter
	docker build -t ${REGISTRY}/jupyter-scipy:${TAG} --build-arg BASE_IMG=${REGISTRY}/jupyter:${TAG} -f Dockerfile . 

docker-push: docker-build
	docker push ${REGISTRY}/jupyter-scipy:${TAG}
