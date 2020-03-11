FROM openjdk:15

WORKDIR /app

# Download Minecraft server 1.15
RUN wget https://launcher.mojang.com/v1/objects/bb2b6b1aefcd70dfd1892149ac3a215f6c636b07/server.jar

# Agree to EULA
RUN echo 'eula=true' > eula.txt

EXPOSE 25565
ENTRYPOINT ["java", "-Xmx1024M", "-Xms1024M", "-jar", "server.jar", "nogui"]
