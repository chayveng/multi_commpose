FROM python:3.9-slim

# Install Node.js and npm
RUN apt-get update && apt-get install -y \
    nodejs \
    npm \
    && rm -rf /var/lib/apt/lists/*

# Install nodemon globally
RUN npm install -g nodemon

WORKDIR /app

COPY . .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose port if needed
# EXPOSE 8000

# Start both Python and Node.js servers
CMD ["nodemon", "--exec", "python main.py"]
