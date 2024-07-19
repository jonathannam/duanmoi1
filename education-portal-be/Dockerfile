# Use a Node.js image as the base
FROM node:lts-slim

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Set the NODE_ENV environment variable
RUN npm run build:prod

# ENV NODE_ENV=production
# FROM node:lts-slim
# WORKDIR /app
# COPY --from=build /app/dist .

# Expose the port your app will listen on
EXPOSE 3000

# Start the app
CMD ["npm", "run", "start:prod"]