FROM node:16

# Create app directory
WORKDIR /app

# Bundle app source
COPY . .

# Install app dependencies
RUN npm install

EXPOSE 3001
CMD [ "node", "index.js" ]