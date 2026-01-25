# Use a lightweight Python image
FROM python:3.12-slim

# Set working dir inside container
WORKDIR /app

# Copy only requirements first (better caching)
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy project files
COPY . .

# Expose gunicorn port
EXPOSE 5000

# Start gunicorn server
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app"]

