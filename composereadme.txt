# to format file 
docker-compose -f simple-docker-compose.yaml config
# to build images with the latest
docker-compose -f simple-docker-compose.yaml build 
# validate images been built
docker image ls 
#build entire stack
docker-compose -f simple-docker-compose.yaml up -d
# check containers runnig 
docker compose postgres