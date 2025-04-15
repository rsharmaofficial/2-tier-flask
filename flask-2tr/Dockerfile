FROM python:3.9-slim

WORKDIR /app

# Install system dependencies + pip packages in one go
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y gcc default-libmysqlclient-dev pkg-config && \
    pip install mysqlclient && \
    pip install --no-cache-dir -r requirements.txt && \
    rm -rf /var/lib/apt/lists/*

COPY . .

# # Optional env vars
# ENV PYTHONDONTWRITEBYTECODE 1
# ENV PYTHONUNBUFFERED 1

# Optional expose
EXPOSE 5000

CMD ["python", "app.py"]
