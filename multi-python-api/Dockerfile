FROM python:3.11-alpine AS builder

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

FROM python:3.11-alpine

WORKDIR /app

COPY --from=builder /app .

EXPOSE 8000

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]