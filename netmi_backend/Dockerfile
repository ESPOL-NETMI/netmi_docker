####################################
##### Backend for the migration  ###
####################################

FROM python:3.8.11-slim-buster

LABEL student1="macaagui@espol.edu.ec"
LABEL student2="alealcor@espol.edu.ec"

WORKDIR /app

# ENV variable for the flask program

ENV FLASK_APP=./src/main.py
ENV FLASK_RUN_HOST=0.0.0.0

# Copy the dependencies and install 

COPY requirements.txt /app

# RUN npm install
RUN pip3 install -r requirements.txt
RUN pip3 install flask
# Copy the entire project

COPY . .

# Ejecuted the project
#⚠ This command is comment because we are working in a dev stage
CMD [ "flask", "run"]