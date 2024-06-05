# Step 1: Specify the base image
FROM node:14

# Step 2: Set the working directory
# I'm using my roll no. + 3000
WORKDIR /21i_4151_backend_auth

# Step 3: Copy package.json and package-lock.json
COPY package*.json ./

# Step 4: Install dependencies
RUN npm install

# Step 5: Copy the rest of the code
COPY . .

# Step 6: Expose the port the app runs on
# I'm running the app on port 4151 (My roll no. + 3000)
EXPOSE 4151

# Step 7: Start the service
CMD [ "node", "index.js" ]