# Use an official Python runtime as a base image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /workspace

# Install Git and packages necessary for building Python projects
RUN apt-get update && apt-get install -y \
    git \
    build-essential \
    libssl-dev \
    libffi-dev \
    python3-dev \
    python3-venv && \
    rm -rf /var/lib/apt/lists/*

# Create a virtual environment and activate it
RUN python3 -m venv venv
ENV PATH="/workspace/venv/bin:$PATH"

# Install Python packages in the virtual environment
RUN pip install --no-cache-dir notebook qiskit matplotlib pylatexenc qiskit_ibm_runtime

# Make port 8888 available for Jupyter
EXPOSE 8888

# Run Jupyter notebook when the container launches
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
