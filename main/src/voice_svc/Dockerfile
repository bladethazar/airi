FROM python:3.10-slim

# Install dependencies
RUN pip install --no-cache-dir torch transformers pyaudio

# Copy the script that handles voice commands
COPY start_voice_service.sh /start_voice_service.sh
RUN chmod +x /start_voice_service.sh

EXPOSE 5000

ENTRYPOINT ["/start_voice_service.sh"]
