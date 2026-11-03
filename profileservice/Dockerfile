# Use Node.js base image
FROM node:22-alpine

# Set working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm ci

# Copy application files
COPY . .

# Expose application port
EXPOSE 5004

# Start application
CMD ["npm", "start"]