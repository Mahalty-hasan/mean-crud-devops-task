# Use Node.js official image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy rest of backend code
COPY . .

# Expose backend port (change to your app’s port if different)
EXPOSE 3000

# Start the backend server
CMD ["npm", "start"]
