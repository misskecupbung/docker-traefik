FROM nginx:alpine
RUN echo Hello from $HOSTNAME > /usr/share/nginx/html/index.html
CMD ["nginx", "-g", "daemon off;"]
