# Use an official Python runtime as a base image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /workspace

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir notebook qiskit

# Make port 8888 available for jupyter
EXPOSE 8888

# Run jupyter notebook when the container launches
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]

