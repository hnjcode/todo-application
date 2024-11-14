# Step 1: Build the Angular app
# Use a Node.js image to build the app
FROM node:16 AS build

# Set the working directory
WORKDIR /app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Install dependencies
RUN npm install --legacy-peer-deps

# Copy the rest of the app's files
COPY . .

# Build the Angular app in production mode
RUN npm run build --prod

# Step 2: Set up Nginx to serve the Angular app
FROM nginx:alpine

# Copy the build output to the Nginx HTML directory
COPY --from=build /app/dist/todo-service-ui /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose the default port
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]