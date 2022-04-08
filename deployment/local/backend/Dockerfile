FROM node:alpine

WORKDIR /app/backend

RUN npm install -g nodemon

COPY package.json .
RUN npm install

# Add docker-compose-wait tool -------------------
ENV WAIT_VERSION 2.7.2
ADD https://github.com/ufoscout/docker-compose-wait/releases/download/$WAIT_VERSION/wait /wait
RUN chmod +x /wait

ENTRYPOINT [ "/bin/sh", "-c", "/wait && nodemon src/" ]
