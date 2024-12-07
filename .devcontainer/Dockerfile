# Use the base Jupyter image
FROM jupyter/scipy-notebook:latest

# Switch to root user to install additional packages
USER root

# Install additional system packages
RUN apt-get update && apt-get install -y \
    graphviz \
    libgraphviz-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Switch back to jovyan user to install Python packages
USER jovyan

RUN echo 'jovyan ALL=(ALL) NOPASSWD: ALL' | tee /etc/sudoers.d/jovyan

# Install additional Python packages
RUN pip install --no-cache-dir \
    pandas-profiling[notebook] \
    seaborn \
    networkx

