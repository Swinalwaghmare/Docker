# -----------------------
# Build Stage
# -----------------------
FROM python:3.12-slim AS builder

WORKDIR /app 

# Install dependecies as root
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

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
USE appuser

EXPOSE 5000

ENTRYPOINT ["python", "app.py"]
CMD ["--help"]
