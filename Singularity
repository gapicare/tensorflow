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
		libnccl2=2.2.13-1+cuda9.0 \
		libfreetype6-dev \
		libhdf5-serial-dev \
		libpng12-dev \
		libzmq3-dev \
		pkg-config \
		python \
		python-dev \
		python3 \
		python3-dev \
		rsync \
		software-properties-common \
		unzip \
		&& \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/*

	apt-get update && \
	apt-get install nvinfer-runtime-trt-repo-ubuntu1604-4.0.1-ga-cuda9.0 && \
	apt-get update && \
	apt-get install -y libnvinfer4=4.1.2-1+cuda9.0

	apt-get install -y python3-pip

	pip3 --no-cache-dir install \
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
		sklearn

	pip3 install tensorflow-gpu==1.10.1
	pip3 install keras==2.1.6

	
