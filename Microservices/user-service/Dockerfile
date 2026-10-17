# Use the official lightweight Node.js Alpine image
FROM node:20-alpine

# Set working directory inside the container
WORKDIR /user-service

# Copy dependency definitions
COPY package*.json ./

# Install production dependencies
RUN npm install --omit=dev

# Copy the rest of the application files
COPY . .

# Expose the application port
EXPOSE 3000

# Run the app
CMD ["node", "app.js"]