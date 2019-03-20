FROM debian
EXPOSE 25565
RUN apt-get update -y
RUN apt-get -y install wget
RUN apt-get -y install apt-utils
RUN apt-get -y install openjdk-8-jre-headless
ARG MC_JAR_SHA1=3737db93722a9e39eeada7c27e7aca28b144ffa7
ARG JAR_URL=https://launcher.mojang.com/v1/objects/${MC_JAR_SHA1}/server.jar
RUN mkdir /etc/minecraft
WORKDIR /etc/minecraft
RUN wget -O /etc/minecraft/minecraft_server.jar ${JAR_URL}
RUN chmod +x minecraft_server.jar
COPY files/eula.txt .
CMD java -Xms1024M -Xmx1536M -jar /etc/minecraft/minecraft_server.jar -o true
