# Use an official lightweight Python image
FROM python:3.10-slim

# Set working directory
RUN mkdir /app
WORKDIR /app

# Install dependencies
COPY requirements.txt /app/requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY . .
COPY ./model /app/model

# Expose Streamlit default port
EXPOSE 8502

# Streamlit configuration (optional)
ENV STREAMLIT_SERVER_HEADLESS=true \
    STREAMLIT_SERVER_ENABLE_CORS=false \
    STREAMLIT_SERVER_ENABLE_XSRF_PROTECTION=false \
    STREAMLIT_SERVER_PORT=8502

# Run Streamlit
# CMD ["streamlit", "run", "app.py"]
# Start Streamlit app
CMD ["streamlit", "run", "/app/app.py", "--server.port=8502", "--server.address=0.0.0.0"]
