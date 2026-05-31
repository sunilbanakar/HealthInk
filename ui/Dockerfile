# UI Dockerfile for Streamlit deployment
FROM python:3.12-slim

# Environment variables for optimal Python behavior
ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    STREAMLIT_SERVER_PORT=8080 \
    STREAMLIT_SERVER_ADDRESS=0.0.0.0

WORKDIR /app

# Copy the main requirements (including Streamlit if not already present)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Ensure Streamlit is installed (if not in requirements)
RUN pip install streamlit

# Copy application code
COPY . .
# In ui/Dockerfile, add this near the end:
ENV PORT=8080
ENV STREAMLIT_SERVER_PORT=8080
ENV STREAMLIT_SERVER_ADDRESS=0.0.0.0
EXPOSE 8080 

# Run Streamlit app with explicit configuration
CMD ["streamlit", "run", "ui/app.py", "--server.port=8080", "--server.address=0.0.0.0", "--server.headless=true"]
