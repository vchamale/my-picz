 
 #   docker build --no-cache -t frontend:amd --platform linux/amd64 .
 #   docker build --no-cache -t frontend:arm .
 #   docker run -d -p 3000:3000 frontend:arm


# FROM node:16-alpine3.15

# ENV REACT_APP_BACKEND_URL=http://34.132.237.50:4000

# COPY . /opt/app

# WORKDIR /opt/app

# RUN npm install

# CMD ["npm", "start"]


   FROM node:17-alpine as builder

   ENV REACT_APP_BACKEND_URL=http://34.70.53.151:4000

   WORKDIR /app
   COPY package.json .
   RUN npm install
   COPY . .
   RUN npm run build
   FROM nginx:1.21.3-alpine
   COPY --from=builder /app/build /usr/share/nginx/html
   EXPOSE 80
   CMD ["nginx", "-g", "daemon off;"]