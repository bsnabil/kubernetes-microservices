FROM node:8-alpine



WORKDIR /usr/src/app

COPY . .

COPY frontend/package.json ./
RUN npm cache clear --force
RUN npm install

EXPOSE 8080
CMD ["sh", "-c", "npm start" ]
