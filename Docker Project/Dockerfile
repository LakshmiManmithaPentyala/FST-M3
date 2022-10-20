# Build Phase
FROM node:alpine as builder
WORKDIR /usr/app
COPY . .
RUN npm install
CMD ["npm", "run", "build"]

# Run Phase
FROM node:alpine
WORKDIR /usr/app
COPY package.json ./
RUN npm install
COPY --from=builder /app/dist .
CMD ["node", "server.js"]