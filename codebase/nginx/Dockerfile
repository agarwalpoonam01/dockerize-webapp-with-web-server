FROM nginx:1.21-alpine

# Copy the Nginx configuration file
COPY nginx.conf /etc/nginx/nginx.conf

# Copy the static files to the Nginx server root
#COPY static /usr/share/nginx/html

# Expose the Nginx port
EXPOSE 80

# Start the Nginx server
CMD ["nginx", "-g", "daemon off;"]


