# Use Node v8 as the base image.
FROM node:20-alpine AS builder

# create and set app directory
WORKDIR /app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./


#install only production dependencies
RUN npm ci --only=production  # Bundle app source

# Copy the rest of the application
COPY . .

# Build the application (if required)
RUN npm run build

# Run app
CMD ["npm", "start"]
