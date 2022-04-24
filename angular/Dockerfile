FROM node:alpine As builder

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install -g npm@8.7.0

RUN npm install

COPY . .

RUN npm run build --prod

FROM nginx:alpine

COPY --from=builder /usr/src/app/dist/SampleApp/ /usr/share/nginx/html
