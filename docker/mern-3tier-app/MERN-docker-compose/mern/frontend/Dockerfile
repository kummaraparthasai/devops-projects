# Use the official image as a parent image
# Description: Dockerfile for the client side of the MERN stack application

FROM node:18

WORKDIR /app

#COPY package.json .
COPY package.json ./

RUN npm install

COPY . .

EXPOSE 5173

CMD ["npm", "run", "dev"]

