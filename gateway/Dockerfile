FROM nginx:1.22.1

RUN rm -f /etc/nginx/conf.d/default.conf

# Копируем наш конфиг с уникальным именем
COPY taski-gateway.conf /etc/nginx/conf.d/taski-gateway.conf

# Статика фронтенда
COPY --from=taski-docker-frontend /app/build /usr/share/nginx/html




