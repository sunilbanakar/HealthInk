# UI Dockerfile for Streamlit deployment\n\nFROM python:3.12-slim\n\n# Environment variables for optimal Python behavior\nENV PYTHONUNBUFFERED=1 \\
    PYTHONDONTWRITEBYTECODE=1\n\nWORKDIR /app\n\n# Copy the main requirements (including Streamlit if not already present)\nCOPY requirements.txt .\nRUN pip install --no-cache-dir -r requirements.txt\n\n# Ensure Streamlit is installed (if not in requirements)\nRUN pip install --no-cache-dir streamlit\n\n# Copy UI source code\nCOPY ui/ ./ui/\n\nEXPOSE 8501\n\n# Default command to run Streamlit app\nCMD ["streamlit", "run", "ui/streamlit_app.py", "--server.port", "8501", "--server.address", "0.0.0.0"]\n
ENV PYTHONUNBUFFERED=1
ENV PYTHONDONTWRITEBYTECODE=1
