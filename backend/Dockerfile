FROM node:21 AS backend-builder

WORKDIR /app

COPY . .

RUN npm i

RUN  npm run test 

WORKDIR /app

COPY --from=backend-builder /app .

COPY .env.docker .env

EXPOSE 5000

CMD ["npm","start"]
