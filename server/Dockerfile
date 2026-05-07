FROM node:20-alpine AS builder

WORKDIR /app

COPY  package*.json ./

RUN  npm install

COPY . .
# app/dist
RUN npm run build  

FROM node:20-alpine AS runtime

WORKDIR /app

COPY  package*.json ./

RUN npm install --omit=dev

#we are copying only compiled file not the source code
COPY --from=builder /app/dist  ./dist  

EXPOSE 5000

CMD [ "node" , "dist/server.js"]