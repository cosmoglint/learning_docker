<h3>Modes</h3>

- <h4>Bridge</h4>
docker uses bridge network using the bridge driver. this is similar to assigning a network to a virtual machine running in you computer. Containers within the same bridge network can communicate with each other. Port mapping is necessary for external communication

- <h4>Host</h4>
this is like connecting the container directly onto the network of the docker host. It will inherit the properties of the host network adapter. Here port mapping is not possible and the containers use the host  ports for communication

- <h4>None</h4>
Completely isolated container which has a self container networkstack. eg. for a computing container you dont need connection to the external network

- <h4>Overlay</h4>
These run a network on top of another, like a vpn. These are used in creating docker swarms( under docker orchestration )

- <h4>MACVLAN</h4>
Here the docker container is assigned an actual MAC address and making it appear as an actual physical device connected to the network


<br>
<h3>Commands</h3>

- <code>docker network ls </code> lists all the available networks

1. <code>docker network create [network_name]</code>
creates a bridge network which is the default network Mode

-  <code>docker network create -d bridge [network_name]</code>
also works


in order to attach a network to an image just specify the network name while running the container
<code>docker container run -dit --net [network_name] nginx</code>
