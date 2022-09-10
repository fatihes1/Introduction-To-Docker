FROM node:18-slim
WORKDIR /opt/vue-app
COPY vue-app .
RUN npm install
RUN npm install -g live-server
RUN npm run build
EXPOSE 8080
CMD ["live-server", "dist/"]
