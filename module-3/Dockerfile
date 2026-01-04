# -----------------------
# Build Stage
# -----------------------
FROM python:3.12-slim AS builder

WORKDIR /app 

# Install dependecies as root
COPY requirements.txt .
RUN pip install --no-cache-dir --prefix=/install -r requirements.txt

# -----------------------
# Runtime Stage
# -----------------------
FROM python:3.12-slim

# Create non-root user
RUN useradd -m appuser

WORKDIR /app

# Copy installed dependencies from builder
COPY --from=builder /install /usr/local

# Copy application code
COPY app.py .
COPY templates ./templates

# Switch to non root user
USER appuser

EXPOSE 5000

ENTRYPOINT ["python", "app.py"]
CMD ["--help"]
