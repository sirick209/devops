FROM amd64/node:20
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY app.js ./
EXPOSE 3000
CMD ["node", "app.js"]
