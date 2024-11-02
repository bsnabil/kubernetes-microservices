FROM node:8-alpine



WORKDIR /usr/src/app


COPY package.json ./
RUN npm cache clear --force
RUN npm install
COPY . .

EXPOSE 8080
CMD ["sh", "-c", "npm start" ]
