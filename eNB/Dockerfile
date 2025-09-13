# Use a lightweight Python base image
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

# Install necessary tools and libraries
RUN apt-get update && apt-get install -y \
    git build-essential python3-dev libssl-dev libsctp-dev pcscd libpcsclite-dev iproute2 net-tools iputils-ping && \
    rm -rf /var/lib/apt/lists/*

# Copy application files to the container
COPY . .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose necessary ports (adjust based on the app's requirements)
EXPOSE 5000

# Define the command to run the eNB simulator
CMD ["python", "eNB_LOCAL.py"]
