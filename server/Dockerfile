# Use the official Node.js image from Docker Hub
FROM node:23-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy the package.json and package-lock.json
COPY package*.json ./

# Install the dependencies defined in package.json
RUN npm install

# Copy the rest of the backend project files into the container
COPY . .

# Generate Prisma client
RUN npx prisma generate

# Expose the port your backend will run on
EXPOSE 5500

# Command to run the app in dev mode using nodemon
CMD npm start