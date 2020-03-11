FROM openjdk:15-slim

WORKDIR /app

# Download Minecraft server 1.15
RUN apt-get update -q -y && \
  apt-get install wget -q -y && \
  wget -q https://launcher.mojang.com/v1/objects/bb2b6b1aefcd70dfd1892149ac3a215f6c636b07/server.jar

# Agree to EULA
RUN echo 'eula=true' > eula.txt

# Creating user minecraft
RUN useradd -md /home/minecraft minecraft && \
  chown minecraft:minecraft -R /app && \
  chmod 774 -R /app

# Running as minecraft user
USER minecraft

EXPOSE 25565
ENTRYPOINT ["java", "-Xmx1024M", "-Xms1024M", "-jar", "server.jar", "nogui"]
