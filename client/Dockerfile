#Build phase
FROM node:alpine as builder

#Copy current working directory to container (when built). First set working directory
WORKDIR /usr/app/complex-client

COPY ./package.json ./
# Install dependencies
RUN npm install

# When make changes dependencies will not be installed again (will use previous image from cache)
COPY ./ ./

RUN npm run build

#Run phase
FROM nginx as runner
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder  /usr/app/complex-client/build /usr/share/nginx/html
#default command is starting nginx. so no need to give a command





