Bootstrap: docker
From: nvidia/cuda:9.0-base-ubuntu16.04

%environment
	export LD_LIBRARY_PATH=/usr/local/cuda/extras/CUPTI/lib64:$LD_LIBRARY_PATH
	export PATH=/bin:/usr/bin:/usr/local/bin:/usr/local/cuda/bin:
	export LC_ALL=C

%post
	apt-get update && apt-get install -y --no-install-recommends \
		build-essential \
		cuda-command-line-tools-9-0 \
		cuda-cublas-9-0 \
		cuda-cufft-9-0 \
		cuda-curand-9-0 \
		cuda-cusolver-9-0 \
		cuda-cusparse-9-0 \
		curl \
		libcudnn7=7.2.1.38-1+cuda9.0 \
		libncc12=2.2.13-1+cuda9.0 \
		libfreetype6-dev \
		libhdf5-serial-dev \
		libpng12-dev \
		libzmq3-dev \
		pkg-config \
		python \
		python-dev \
		rsync \
		software-properties-common \
		unzip \
		&& \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/*

	apt-get update && \
	apt-get install nvinfer-runtime-trt-repo-ubuntu1604-4.0.1-ga-cuda9.0 && \
	apt-get update && \
	apt-get install libnvinfer4=4.1.2-1+cuda9.0

	curl -0 https://bootstrap.pypa.io/get-pip.py && \
	python get-pip.py && \
	rm get-pip.py

	pip --no-cache-dir install \
		Pillow \
		h5py \
		ipykernel \
		jupyter \
		keras_applications \
		keras_preprocessing \
		matplotlib \
		numpy \
		pandas \
		scipy \
		sklearn \
		&& \
	python -m ipykernel.kernelspec

	pip --no-cache-install \
	http://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-0.0.0-cp27-none-linux_x86_64.whl

