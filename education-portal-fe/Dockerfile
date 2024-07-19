# Use a Node.js image as the base
FROM node:lts-slim AS build

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Set the NODE_ENV environment variable
RUN npm run build

# Stage for production
FROM nginx:alpine

# Copy the build output to the Nginx default directory
COPY --from=build /app/dist/education-portal-fe/browser /usr/share/nginx/html
COPY default.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80
