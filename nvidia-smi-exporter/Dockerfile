FROM nvidia/dcgm-exporter

RUN echo "deb [by-hash=no] http://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64 /" > /etc/apt/sources.list.d/cuda.list
RUN apt-get update \
    && apt-get install wget -y \
    && wget -qO- https://get.docker.com | sh \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY nvidia-smi-ps /usr/local/bin
COPY nvidia-smi-exporter /usr/local/bin

RUN chmod +x /usr/local/bin/nvidia-smi-*

ENTRYPOINT [ "nvidia-smi-exporter" ]
