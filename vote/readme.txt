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