######################################################################################
##### Stage 1, "build-stage", based on Node.js, to build and compile the frontend  ###
######################################################################################

FROM node:14-alpine as build-stage

LABEL student1="macaagui@espol.edu.ec"
LABEL student2="alealcor@espol.edu.ec"

WORKDIR /home/node/app

# Copy the dependencies and install 

COPY package*.json /home/node/app

RUN npm install

# Copy the entire project and build it

COPY . /home/node/app

RUN npm run build

######################################################################################
##### Stage 2, based on Nginx, to have only the compiled app, ready for production ###
######################################################################################

FROM nginx:1.21.0-alpine

# Install the bash to use instead 

RUN apk add --no-cache bash

# Copy the compiled app and the conf to the new stage

COPY --from=build-stage /home/node/app/dist /usr/share/nginx/html

COPY --from=build-stage /home/node/app/nginx.conf /etc/nginx/conf.d/default.conf

# Start the app

CMD ["nginx", "-g", "daemon off;"]
