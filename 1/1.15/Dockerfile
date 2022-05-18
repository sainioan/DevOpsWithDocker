FROM node:16-slim
WORKDIR /app
EXPOSE 3000

RUN apt-get update && apt-get install -y curl && curl https://deb.nodesource.com/setup_14.x | apt-get install -y nodejs
RUN apt-get update && apt-get install -y curl git
RUN apt install -y nodejs
RUN git clone https://github.com/sainioan/patientor.git /app
RUN npm install
CMD npm start