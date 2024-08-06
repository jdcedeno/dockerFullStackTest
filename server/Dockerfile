# Use the official Node.js image as the base image
FROM node:20-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json (if available) to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of your application code to the working directory
COPY . .

# Build the TypeScript code
RUN npm run build

# List the contents of the /app directory
RUN echo "Contents of /app directory:" && ls -la /app

# List the contents of the /app/dist directory to verify build output
RUN echo "Contents of /app/dist directory:" && ls -la /app/dist

# Expose the port the app runs on
EXPOSE 3000

# Command to run the application
CMD ["node", "dist/server.js"]