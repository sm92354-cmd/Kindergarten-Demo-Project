# Use Node.js base image
FROM node:22-alpine

# Set working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm ci

# Copy application source code
COPY . .

# Expose React development server port
EXPOSE 3000

# Start React application
CMD ["npm", "start"]