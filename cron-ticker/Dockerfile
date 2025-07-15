#/app /lib /user
FROM node:20-alpine

#cd app
WORKDIR /app 

#destino /app
COPY package.json ./

#instalar las dependencias
RUN npm install 

#destino /app
COPY . .

#realizar testing
RUN npm run test

#commando run de la imagen
CMD [ "node", "app.js" ]
