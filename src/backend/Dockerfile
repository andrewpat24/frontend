# Use base node 8 image from Docker hub
FROM node:8

WORKDIR /backend

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy rest of the application csource code
COPY . .

RUN npm run-script build

# Run app.js with debugging port when container launches
ENTRYPOINT ["node", "--inspect=9229", "--experimental-modules", "index.mjs"]

# Comment above and uncomment below to run app.js without debugger port when container launches
#ENTRYPOINT ["node", "public/dist/bundle-backend.js"]
