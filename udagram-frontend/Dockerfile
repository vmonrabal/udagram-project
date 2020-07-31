# Use NodeJS base image
FROM node:13 AS build

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./

# Install ionic globaly
# Install project dependencies
RUN npm install -g ionic
RUN npm install

# Bundle project
COPY . .
RUN ionic build

# Run application
FROM nginx:alpine
RUN rm -rf /usr/share/nginx/html/*
COPY --from=build /usr/src/app/www /usr/share/nginx/html/