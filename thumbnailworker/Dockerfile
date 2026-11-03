# Use Python base image
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Copy requirements file
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy worker files
COPY . .

# Start thumbnail worker
CMD ["python", "worker.py"]