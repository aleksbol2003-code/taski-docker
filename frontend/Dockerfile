FROM node:18-alpine
WORKDIR /app

COPY package.json package.json
COPY package-lock.json package-lock.json

RUN npm install

COPY . .
RUN npm run build

# Эта команда запустит встроенный сервер на Node.js, который будет раздавать
# содержимое директории /app/build на порте 8000
# CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]

# Этап 2: раздача статики + проксирование (Nginx)
# FROM nginx:alpine

# Копируем конфиг Nginx (он должен лежать рядом с Dockerfile в папке frontend)
# COPY nginx.conf /etc/nginx/conf.d/default.conf

# Копируем собранную статику из первого этапа в папку Nginx
# COPY --from=build /app/build /usr/share/nginx/html
