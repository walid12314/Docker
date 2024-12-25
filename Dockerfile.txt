# Use the official Nginx image as a base
FROM nginx:alpine

# Set the working directory
WORKDIR /usr/share/nginx/html

# Copy all HTML files to the Nginx HTML directory
COPY index.html about.html contact.html service.html ./

# Copy CSS, JS, fonts, and images directories to the Nginx HTML directory
COPY css/ css/
COPY js/ js/
COPY fonts/ fonts/
COPY images/ images/

# Expose port 80
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]
