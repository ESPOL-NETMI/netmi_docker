####################################
##### Backend for the migration  ###
####################################

FROM nikolaik/python-nodejs:python3.9-nodejs14-alpine

LABEL student1="macaagui@espol.edu.ec"
LABEL student2="alealcor@espol.edu.ec"

# Install the bash to use instead 

RUN apk add --no-cache bash

WORKDIR /app

# ENV variable for the flask program

ENV FLASK_APP=./src/app.py
ENV FLASK_RUN_HOST=0.0.0.0

# Copy the dependencies and install 

COPY requirements.txt /app
COPY package.json /app

RUN npm install
RUN pip3 install -r requirements.txt

# Copy the entire project

COPY . .

# Ejecuted the project
#⚠ This command is comment because we are working in a dev stage
# CMD [ "flask", "run"]