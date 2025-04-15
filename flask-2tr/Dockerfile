FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Install system dependencies + MySQL dev libs
RUN apt-get update && \
    apt-get install -y gcc default-libmysqlclient-dev curl && \
    rm -rf /var/lib/apt/lists/*

# Copy requirements file & install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY . .

# Expose port
EXPOSE 5000

# Run app
CMD ["python", "app.py"]
