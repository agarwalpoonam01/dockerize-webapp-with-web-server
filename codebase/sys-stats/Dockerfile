FROM node:14
LABEL maintainer="Poonam Agarwal <poonamagarwal01@outlook.com>"
WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start", "--host 0.0.0.0"]
