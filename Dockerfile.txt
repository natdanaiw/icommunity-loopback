FROM node:15.3.0-alpine

# Create app directory
RUN mkdir -p /usr/src/demo-loopback
WORKDIR /usr/src/demo-loopback

# Install app dependencies
COPY package.json /usr/src/demo-loopback
RUN npm install

# Bundle app source
COPY . /usr/src/demo-loopback

EXPOSE 3000 50051
CMD [ "node", "." ]