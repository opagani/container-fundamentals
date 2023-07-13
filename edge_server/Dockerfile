# Start with a small base layer
FROM alpine:3.18

# Add labels
LABEL org.opencontainers.image.authors="paganio@yahoo.com"
LABEL org.opencontainers.image.source=https://github.com/opagani/container-fundamentals
LABEL org.opencontainers.image.description="Containter Fundamentals - Static Website Image"
LABEL org.opencontainers.image.licenses=APACHE2

# Add the --no-cache flag to avoid caching indices
RUN apk update --no-cache \
    && apk add --no-cache nginx \
    && rm -rf /tmp/* /var/tmp/* /var/lib/apt/archive/* /var/lib/apt/lists/*

# Copy the necessary files and expose port 80  
COPY config/nginx.conf /etc/nginx/
COPY web_content/ /var/www
RUN rm -rf web_content/
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
