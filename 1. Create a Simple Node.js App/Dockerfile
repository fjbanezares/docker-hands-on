# Use the official Node.js 14 image as base
FROM node:14

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install the app dependencies inside the container
RUN npm install

# Copy the content of the local src directory to the working directory
COPY . .

# Declare the port number the container should expose
EXPOSE 8080

# Command to run when the container starts
CMD ["node", "app.js"]
