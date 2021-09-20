####################################
##### Backend for the migration  ###
####################################

FROM python:3.6-slim-buster

LABEL student1="macaagui@espol.edu.ec"
LABEL student2="alealcor@espol.edu.ec"

# Env & Arg variables
ARG USERNAME=pythonssh
ARG USERPASS=sshpass

# Apt update & apt install required packages
# whois: required for mkpasswd

RUN apt update && apt -y install openssh-server whois

# Add a non-root user & set password
RUN useradd -ms /bin/bash $USERNAME
# Save username on a file ¿?¿?¿?¿?¿?
#RUN echo "$USERNAME" > /.non-root-username

# Set password for non-root user
RUN usermod --password $(echo "$USERPASS" | mkpasswd -s) $USERNAME

# Remove no-needed packages
RUN apt purge -y whois && apt -y autoremove && apt -y autoclean && apt -y clean

# Change to non-root user
#USER $USERNAME
#WORKDIR /home/$USERNAME

# Create the ssh directory and authorized_keys file
USER $USERNAME
RUN mkdir /home/$USERNAME/.ssh && touch /home/$USERNAME/.ssh/authorized_keys
USER root

# Set volumes
VOLUME /home/$USERNAME/.ssh
VOLUME /etc/ssh

WORKDIR /app

# Copy the dependencies and install 

COPY *.txt /app
# COPY microservice.txt /app
# COPY requirements.txt /app

# RUN npm install
RUN pip install --upgrade pip
RUN pip3 install --upgrade setuptools
RUN pip3 install -r requirements.txt
# RUN pip3 install -r geniepyats.txt
RUN pip3 install -r microservice.txt

# Copy the entire project

COPY . .

ENV variable for the flask program
ENV FLASK_APP=/app/src/main
ENV FLASK_RUN_HOST=0.0.0.0

WORKDIR /app/src

# Ejecuted the project
#⚠ This command is comment because we are working in a dev stage
CMD [ "flask", "run"]

# CMD ["export", "FLASK_APP=main"]