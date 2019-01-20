Bootstrap: docker
From: nvidia/cuda:9.0-cudnn7-runtime-ubuntu16.04

%labels

%environment
	export PATH=/bin:/usr/bin:/usr/local/bin:/usr/local/cuda/bin:
	export LC_ALL=C

%post
	apt-get update
	apt-get install -y libhdf5-dev graphviz locales python3-dev python3-pip
	apt-get clean

	pip3 install tensorflow-gpu==1.8.0
	pip3 install keras==2.1.6
	pip3 install numpy Pillow scikit-learn pandas matplotlib notebook ipython liac-afiff openpyxl xlsxwriter

	mkdir -p /net/jost/home
	mkdir -p /d/hpc/session
	mkdir -p /d/hpc/cache
	mkdir -p /var/spool/slurm
