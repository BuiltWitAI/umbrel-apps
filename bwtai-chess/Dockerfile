# Static file server for Chess vs Bot
FROM nginx:alpine

# Copy static files
COPY index.html /usr/share/nginx/html/

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]