# docker build -t backend:1.0.0 --platform linux/amd64 . 
# docker build --no-cache -t backend --platform linux/amd64 .
# docker run -it -d -p 4000:4000 backend:1.0.0

FROM node:18.12-alpine3.15

ENV DB_USER_ID=postgres \
    DB_PASSWORD='x3I3qb#/v3f0u#q~' \ 
    DB_HOST=35.193.42.30 \
    DB_PORT=5432 \
    DB_NAME=my-picz \
    BACKEND_PORT=4000 \
    JWT_SECRET=secretWord \
    FRONTEND_URL=http://34.170.175.242:3000 \
    EMAIL_USER=d4638804309754 \
    EMAIL_PASS=5ad12921351893 \
    EMAIL_HOST=smtp.mailtrap.io \
    EMAIL_PORT=2525 

COPY . /opt/app

WORKDIR /opt/app

RUN npm install

RUN npm uninstall bcrypt

RUN npm i bcrypt

EXPOSE 4000

CMD ["npm", "start"]
