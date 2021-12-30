# Specify a base image
FROM node:alpine
# specify the working dir in container
WORKDIR /usr/app
COPY ./package.json ./
# Install some depenendencies
RUN npm install
COPY ./ ./

# Default command
CMD ["npm", "start"]
