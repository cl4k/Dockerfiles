FROM debian
RUN apt-get update
RUN apt-get -y install wget
RUN apt-get -y install bzip2
RUN adduser teamspeak
WORKDIR /home/teamspeak
RUN wget https://files.teamspeak-services.com/releases/server/3.6.1/teamspeak3-server_linux_amd64-3.6.1.tar.bz2
EXPOSE 9987/udp
EXPOSE 10011
EXPOSE 30033
RUN tar xjf teamspeak3-server_linux_amd64-3.6.1.tar.bz2
WORKDIR teamspeak3-server_linux_amd64
RUN touch .ts3server_license_accepted
CMD ["sh","ts3server_minimal_runscript.sh"]
