FROM judge0/compilers:1.4.0-slim

# Python for ML
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip3 install \
        mlxtend \
        numpy \
        pandas \
        scikit-learn \
        pytest \
        scipy \
        torch==1.7.1 \
        statsmodels==0.12.2 \
        git+https://github.com/Onion-Team-VN/onion-lib.git \
        matplotlib==3.1.0 \
        seaborn \
        && \
    rm -rf /var/lib/apt/lists/*

# MPI for C, C++ and Python
RUN set -xe && \
    apt-get update && \
    apt-get install -y --no-install-recommends libopenmpi-dev python3-mpi4py && \
    rm -rf /var/lib/apt/lists/*

COPY docker-entrypoint.sh /
ENTRYPOINT ["/docker-entrypoint.sh"]

LABEL maintainer="Herman Zvonimir Došilović <hermanz.dosilovic@gmail.com>"
LABEL version="1.6.1-extra"
