FROM ubuntu

ENV DEBIAN_FRONTEND noninteractive
RUN sed -i 's/archive.ubuntu.com/kr.archive.ubuntu.com/g' /etc/apt/sources.list
RUN apt-get update
RUN apt-get dist-upgrade -y
RUN apt-get install -y git curl wget vim supervisor libicu-dev make build-essential
RUN curl -sL https://deb.nodesource.com/setup | bash -
RUN apt-get install -y nodejs
RUN npm update -g
RUN git clone https://github.com/leeopop/slack-irc.git

# Add configurations
ADD config.json slack-irc/config.json

# Do npm install
RUN cd slack-irc; npm install; cd ..;
RUN cd slack-irc; npm run build; cd ..;

# Add supervisor configs
ADD supervisord.conf supervisord.conf

CMD ["-n", "-c", "/supervisord.conf"]
ENTRYPOINT ["/usr/bin/supervisord"]
