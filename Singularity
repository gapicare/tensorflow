Bootstrap: docker
From: nvidia/cuda:9.0-cudnn7-runtime-ubuntu16.04

%environment
	export PATH=/bin:/usr/bin:/usr/local/bin:/usr/local/cuda/bin:
	export LC_ALL=C

%post
	apt-get update
	apt-get install -y python3-dev python3-pip
	apt-get clean

	pip3 install numpy
	pip3 install scipy matplotlib pillow ipython scikit-learn h5py liac-arff
	pip3 install tensorflow-gpu
	pip3 install keras

	mkdir -p /net/jost/home
	mkdir -p /d/hpc/session
	mkdir -p /d/hpc/cache
	mkdir -p /var/spool/slurm
