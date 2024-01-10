# Use the official Node.js 14 image as the base image
FROM node:14

# Set the working directory in the container
WORKDIR /app

# Copy files into the container
COPY .gitignore .
COPY index.js .
COPY package.json .
COPY package-lock.json .

# Install application dependencies
RUN npm install

# Command to run when the container starts
CMD ["node", "index.js"]

