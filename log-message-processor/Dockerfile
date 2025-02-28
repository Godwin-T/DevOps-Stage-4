FROM python:3.6-slim

WORKDIR /app

RUN apt-get update && apt-get install -y \
    gcc g++ python3-dev libffi-dev

# Copy dependencies file
COPY requirements.txt .

# Install Packages
RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# Copy application files
COPY . .

CMD ["python", "main.py"]
