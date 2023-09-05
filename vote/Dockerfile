# voting app is writen in python, so we need to use python base image
# Using official python runtime base image , python 2.7-alpine
FROM oreakinodidi/voteapp-python:v0.1.0

# Set the application directory
WORKDIR /app

#copy source code into container
COPY . .

# Enter Work Directory for Voting App 
WORKDIR /app/vote

# Install our requirements.txt
# ADD requirements.txt /app/requirements.txt
# use pip which is python package build command
RUN pip install -r requirements.txt

# Copy our code from the current folder to /app inside the container
# ADD . /app

# Make port 80 available for links and/or publish
EXPOSE 80

# Define our command to be run when launching the container
CMD ["gunicorn", "app:app", "-b", "0.0.0.0:80", "--log-file", "-", "--access-logfile", "-", "--workers", "4", "--keep-alive", "0"]

# first build the image manually 
# docker run -idt -p 80 python:2.7-alpine sh 
# docker ps -l to see if container is running
# copy source code from specific directory to container
# docker cp . 9a1fd38a1adc:/app
# get into container
# docker exec -it 9a1fd38a1adc sh
# cd /app
# ls -> to list all files copied
# cd/app/vote
# pip install -r requirements.txt
# gunicorn app:app -b 0.0.0.0:80 -> to start app
# check ports the app is listening on
# open localhost:port in browser
# exit container (CTRL + c) to stop app
# docker commit 9a1fd38a1adc oreakinodidi/voteapp-python:v0.1.0
# docker push oreakinodidi/voteapp-python:v0.1.0
# docker run -idt -p 80 oreakinodidi/voteapp-python:v0.1.0
# docker ps -l to see if container is running
# build dockerfile 
# enter directory where dockerfile is located
# docker image build -t oreakinodidi/voteapp-python:v1 .
# docker run -idt -p 80 oreakinodidi/voteapp-python:v0.1.0
# docker ps -l to see if container is running