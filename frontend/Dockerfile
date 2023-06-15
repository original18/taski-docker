FROM node:18-slim

WORKDIR /app

COPY package.json package.json

COPY package-lock.json package-lock.json

RUN npm config rm proxy

RUN npm config rm https-proxy

RUN npm install

COPY . .

RUN npm run build

CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]
