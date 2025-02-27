# Use Node.js base image
FROM node:8-alpine

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy application files
COPY . .

# Start the server
CMD ["npm",  "start"]