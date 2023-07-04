# Specifiy a base image
FROM node:alpine

# Specify a working directory
WORKDIR /usr/app

# Make package.json available inside working directory
COPY ./package.json ./

# Install dependencies
RUN npm install

# Make all project files available inside working directory
COPY ./ ./

# Setup default command
CMD ["npm", "start"]