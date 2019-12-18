FROM node:alpine
WORKDIR /usr/app/complex-worker
COPY ./package.json ./
RUN npm install
COPY . .
CMD ["npm",  "run", "start"]