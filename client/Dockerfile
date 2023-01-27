FROM node:16.17.1-alpine3.16
WORKDIR /usr/app
COPY . /usr/app

RUN npm run build

COPY package*.json ./

# Install dependencies
RUN npm install

# Copy rest of the app to the working directory
COPY . .

RUN npm build

RUN npm install -g serve

# Expose port 3000
EXPOSE 3000

# Define entry point
CMD [ "serve", "-s", "build", "-l", "3000" ]


# FROM node:16.17.1-alpine3.16 as build
# WORKDIR /usr/app
# COPY . /usr/app

# RUN npm run build
