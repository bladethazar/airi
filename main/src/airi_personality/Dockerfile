# Use a minimal Python base image
FROM python:3.10-slim

# Set up working directory
WORKDIR /app

# Install dependencies
RUN pip install --no-cache-dir jsonpickle requests

# Copy personality configuration
COPY config/personality_config.json /app/personality_config.json

# Entry point for personality management script
COPY entrypoint.sh /app/entrypoint.sh
RUN chmod +x /app/entrypoint.sh

ENTRYPOINT ["./entrypoint.sh"]
