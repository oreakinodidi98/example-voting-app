# node js image
#FROM node:8.9-alpine
FROM oreakinodidi/resultapp-pynodejsthon:v0.1.0
# RUN mkdir -p /app
WORKDIR /app
# copy source code into container
COPY . .
# RUN npm install -g nodemon
RUN npm config set registry https://registry.npmjs.org
# COPY package.json /app/package.json
RUN npm install && \
npm ls
RUN npm cache clean --force && \
mv /app/node_modules /app_modules

# RUN npm install --prefix /app
# COPY . /app
# COPY /app/node_modules /node_modules
# RUN npm install \
#     && npm ls\
#     && npm cache clean --force \
#     && mv /app/node_modules /node_modules
# COPY . /app

# set enviroment variable of port to 80
ENV PORT 80
# expose port 80
EXPOSE 80
# run command
CMD ["node", "server.js"]
