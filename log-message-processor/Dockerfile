#FROM python:3.10-slim

FROM python:3.6-slim

WORKDIR /app

RUN apt-get update && apt-get install -y \
    gcc g++ python3-dev libffi-dev

# Copy dependencies file
COPY requirements.txt .

RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["python", "main.py"]
