# Static file server for Conway's Game of Life
FROM nginx:alpine

# Copy all static files
COPY . /usr/share/nginx/html

# Remove unnecessary files
RUN rm -f /usr/share/nginx/html/Dockerfile /usr/share/nginx/html/docker-compose.yml /usr/share/nginx/html/umbrel-app.yml /usr/share/nginx/html/README.md /usr/share/nginx/html/.gitignore /usr/share/nginx/html/cc.sh

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]