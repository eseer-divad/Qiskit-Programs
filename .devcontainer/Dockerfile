# Use an official Python runtime as a base image
FROM python:3.11.9-slim

# Set the working directory in the container
WORKDIR /workspace

# Install Git and necessary packages for building Python projects
RUN apt-get update && apt-get install -y \
    git \
    build-essential \
    libssl-dev \
    libffi-dev \
    python3-dev \
    python3-venv && \
    rm -rf /var/lib/apt/lists/*

# Create a virtual environment in the workspace directory
RUN python3 -m venv venv

# Ensure commands and scripts in the virtual environment are used in preference to the system-wide ones
ENV PATH="/workspace/venv/bin:$PATH"

# Install Python packages in the virtual environment
RUN pip install --no-cache-dir notebook qiskit matplotlib pylatexenc qiskit_ibm_runtime

# Make port 8888 available for the Jupyter Notebook server
EXPOSE 8888

# Configure the container to run Jupyter Notebook on startup
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
