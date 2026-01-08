FROM ubuntu:22.04

WORKDIR /app

# Install Python
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Copy requirements first (layer caching)
COPY requirements.txt .

RUN pip3 install --no-cache-dir -r requirements.txt

# Copy Django project
COPY devops .

EXPOSE 8000

CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]




