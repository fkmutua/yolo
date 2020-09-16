FROM node:latest

LABEL Felix Mutua

WORKDIR /backend

COPY backend/backend

RUN npm install

EXPOSE 5000

CMD ["npm", "start"]
