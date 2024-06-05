# Step 1: Specify the base image
FROM node:14

# Step 2: Set the working directory
# I'm using my roll no. + 3001
WORKDIR /21i_4152_backend_classrooms

# Step 3: Copy package.json and package-lock.json
COPY package*.json ./

# Step 4: Install dependencies
RUN npm install

# Step 5: Copy the rest of the code
COPY . .

# Step 6: Expose the port the app runs on
# I'm running the app on port 4152 (My roll no. + 3001)
EXPOSE 4152

# Step 7: Start the service
CMD [ "node", "index.js" ]