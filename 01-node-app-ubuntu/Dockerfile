FROM ubuntu:18.04
RUN apt-get update && apt-get install curl -y
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash 
RUN apt-get install nodejs -y
WORKDIR /opt/node-app
# COPY . /opt/node-app
COPY . .
ENV github_username=fatihes1
# CMD ["node", "/opt/node-app/index.js"]
CMD ["node", "index.js"]
