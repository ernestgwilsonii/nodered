# REF: https://hub.docker.com/r/nodered/node-red-docker/
# REF: https://nodered.org

####################
# First time setup #
####################
# Create bind mounted directies
# Node-RED
mkdir -p /opt/nodered
chmod a+rw /opt/nodered

##########
# Deploy #
##########
# Deploy the stack into a Docker Swarm
docker stack deploy -c docker-compose.yml nodered
# docker stack rm nodered

# Verify
docker service ls | grep nodered
docker service logs -f nodered_nodered

http://IP:1880

