FROM ubuntu
RUN apt-get update && \
	apt-get upgrade -y && DEBIAN_frontend=noninteractive && \
	apt-get install -y ca-certificates openssh-server
RUN apt-get install -y apt-transport-https
RUN apt-get install -y postfix curl
WORKDIR ./
RUN curl -LO https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh
RUN bash script.deb.sh
RUN EXTERNAL_URL="http://gitlab.example.com" apt-get install gitlab-ce
RUN apt install -y tzdata
EXPOSE 443 80 22
CMD /opt/gitlab/embedded/bin/runsvdir-start & EXTERNAL_URL="gitlab.example.com" && \
		gitlab-ctl reconfigure && tail -f /dev/null
# docker build -t ex03 .
# docker run -it --rm -p 80:80 -p 21:22 --privileged ex03
