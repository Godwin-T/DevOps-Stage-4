# Use Node.js 14 base image
FROM node:14-alpine 

#AS build

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package.json package-lock.json ./
RUN npm install 

# Copy application files
COPY . .

CMD [ "npm", "run", "dev" ]
# CMD ["npm", "run", "build"]