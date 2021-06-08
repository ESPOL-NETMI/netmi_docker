####################################
##### Backend for the migration  ###
####################################

FROM python:3.9.5-alpine3.13

LABEL student1="macaagui@espol.edu.ec"
LABEL student2="alealcor@espol.edu.ec"

# Install the bash to use instead 

RUN apk add --no-cache bash

WORKDIR /app

# Copy the dependencies and install 

COPY requirements.txt /app

RUN pip3 install -r requirements.txt

# Copy the entire project

COPY . .

WORKDIR /app/src
# Ejecuted the project

CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]

