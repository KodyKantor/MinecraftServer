MinecraftServer
===============

Minecraft server docker container

This container is managed by supervisor. Supervisor will monitor the java process, and restart it if it
goes down for some reason. The server startup command will generate the world in the /world directory.
You must sign the EULA that Mojang provides, and place it in the directory you will mount in the container,
otherwise the server will fail to run.

For example:  

    $ mkdir /home/username/world  
    $ echo "eula=true" > /home/username/world/eula.txt

Recommended run configuration: 

    $ docker run -d --name minecraft -v /home/username/world:/world -p 25565:25565 kodykantor/minecraftserver  
This will run the server in the background, and your world files will be located at /home/username/world.  
  
The server can be accessed through the default port on the host.

