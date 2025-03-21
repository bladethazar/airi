FROM ollama/ollama:latest

# Copy script to start Ollama
COPY start_ollama.sh /start_ollama.sh
RUN chmod +x /start_ollama.sh

# Expose required port
EXPOSE 11434

ENTRYPOINT ["/start_ollama.sh"]
