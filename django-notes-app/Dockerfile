FROM python:3.9-slim

WORKDIR /app/backend

# Install system dependencies required for mysqlclient
RUN apt-get update && apt-get install -y \
    default-libmysqlclient-dev \
    build-essential \
    pkg-config \
 && rm -rf /var/lib/apt/lists/*

COPY requirements.txt /app/backend/
RUN pip install --upgrade pip \
 && pip install -r requirements.txt

COPY . /app/backend

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

