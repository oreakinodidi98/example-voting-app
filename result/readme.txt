# this is a node.js application 
# base image: node:8.9-alpine
# work directory : /app
# build instructions : 
npm install -g nodemon
npm config set registry https://registry.npmjs.org

npm install \
 && npm ls\
 && npm cache clean --force \
 && mv /app/node_modules /node_modules

# ports: 80
# launch command: node server.js

############################instructions########################
# first build the image manually 
# docker run -idt -p 80 node:8.9-alpine sh 
# docker ps -l to see if container is running
# copy source code from specific directory to container
# docker cp . 0f09e05bb143:/app
# get into container
# docker exec -it 0f09e05bb143 sh
# cd /app
# ls -> to list all files copied
npm install -g nodemon
npm config set registry https://registry.npmjs.org

npm install \
 && npm ls\
 && npm cache clean --force \
 && mv /app/node_modules /node_modules
# export PORT=80 -> to set the port to 80
# node server.js
# check ports the app is listening on
# open localhost:port(60616) in browser
# exit container (CTRL + c) to stop app
# docker commit 0f09e05bb143 oreakinodidi/resultapp-pynodejsthon:v0.1.0
# docker push oreakinodidi/resultapp-pynodejsthon:v0.1.0
# docker run -idt -p 80 oreakinodidi/resultapp-pynodejsthon:v0.1.0
# docker ps -l to see if container is running

############ build dockerfile ######################## 
# enter directory where dockerfile is located -> so result
# docker image build -t oreakinodidi/resultapp-pynodejsthon:v1 .
# docker run -idtP oreakinodidi/resultapp-pynodejsthon:v1
# docker ps -l to see if container is running
# docker logs -f <ID>
# docker commit 0f09e05bb143 oreakinodidi/resultapp-pynodejsthon:v0.1.0
# docker push oreakinodidi/resultapp-pynodejsthon:v0.1.0