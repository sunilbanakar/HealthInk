# UI Dockerfile for Streamlit deployment

FROM python:3.12-slim

# Environment variables for optimal Python behavior
ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    PORT=8080 \
    STREAMLIT_SERVER_HEADLESS=true

WORKDIR /app

# Copy the main requirements (including Streamlit if not already present)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Ensure Streamlit is installed (if not in requirements)
RUN pip install --no-cache-dir streamlit

# Copy UI source code
COPY ui/ ./ui/

# Expose the port that Cloud Run expects
EXPOSE 8080

# Default command to run Streamlit app, using the PORT env variable
CMD ["sh", "-c", "streamlit run ui/streamlit_app.py --server.port $PORT --server.address 0.0.0.0"]

