# Step 1: Build the React app
FROM node:16 AS build

# Create app directory
WORKDIR /21i_3151_frontend

# Copy package.json and package-lock.json
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the React app
RUN npm run build

# Step 2: Serve the React app
FROM nginx:alpine

# Copy the built files from the previous stage to the Nginx web root
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 3151 since I'm using my roll no. + 3000
EXPOSE 3151

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]
