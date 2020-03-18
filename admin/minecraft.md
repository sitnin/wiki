# Minecraft server

https://github.com/nimmis/docker-spigot

https://hub.docker.com/r/nimmis/spigot










https://hub.docker.com/r/itzg/minecraft-bedrock-server

https://github.com/itzg/docker-minecraft-bedrock-server

https://minecraft.gamepedia.com/Server.properties#Bedrock_Edition_3


https://minecraft.gamepedia.com/Bedrock_Dedicated_Server



https://github.com/TapeWerm/MCscripts


docker run -d
--name minecraft
--restart unless-stopped
-e EULA=true
-e VERSION=latest
-e SERVER_PORT=9132
-v /opt/minecraft/bedrock:/data
-p 9132:9132
-p 9132:9132/udp
itzg/minecraft-bedrock-server























https://minecraft-ru.gamepedia.com/%D0%A1%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_%D0%B8_%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0_%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0#.D0.9E.D0.BF.D0.B8.D1.81.D0.B0.D0.BD.D0.B8.D0.B5_.D0.BF.D0.B0.D1.80.D0.B0.D0.BC.D0.B5.D1.82.D1.80.D0.BE.D0.B2




docker run -d --name spigot --restart unless-stopped -e EULA=true -e SPIGOT_VER=latest -e MC_MINMEM=512m -e MC_MAXMEM=2g -e SPIGOT_AUTORESTART=no -e SPIGOT_UID=1007 -v /opt/minecraft/data:/minecraft -p 15555:25565 nimmis/spigot











look at the last output from the spigot server

To get an output of the latest events from the spigot server type

docker exec spigot mc_log








using the minecraft op command

To make yourself operator in the game use mc_send command, for example give the user myuser op use the command.

docker exec spigot mc_send op myuser





starting and stopping the server

To stop the server but not the container do

docker exec spigot mc_stop

To start it after being stopped do

docker exec spigot mc_start

Finally to restart it do

docker exec spigot mc_restart
