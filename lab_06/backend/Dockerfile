FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . . /app/

EXPOSE 80

ENV MONGODB_USERNAME=todor
ENV MONGODB_PASSWORD=secret

CMD ["npm", "start"]