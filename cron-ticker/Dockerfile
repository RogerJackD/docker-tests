#/app /lib /user
# FROM --platform=linux/arm64 node:20-alpine
FROM --platform=$BUILDPLATFORM node:20-alpine 
#usa todas las plataformas que mi builx pueda proporcionarme

# FROM node:20-alpine
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

#Eliminar archivos y directorios no necesario en PROD
RUN rm -rf tests && rm -rf node_modules


#unicamente dependencias de PROD
RUN npm install  --prod


#commando run de la imagen
CMD [ "node", "app.js" ]
