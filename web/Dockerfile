FROM node:19.7-alpine
RUN mkdir /app
WORKDIR /app
COPY package.json /app/
RUN npm install  # 여기까지는 라이브러리 설치
COPY ./public /app/public
COPY ./src /app/src
EXPOSE 3000
CMD ["node", "src/server.js"]