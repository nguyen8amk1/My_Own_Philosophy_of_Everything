# WEB SERVER TECHNOLOGY 

## DEFINITION: 
    ... 

## Nginx: 
    ... 
    things to do in order to make it work: 
        + enable firewall ?? 
        + create '/var/www/your_domain/html' folder and the 'html' folder will contain the front-end 

        + create '/etc/nginx/sites-enabled/your_domain' -> configuration file for nginx to serve the frontend  
            /etc/nginx/ - contains all nginx config files 
            with this content (kinda like this):

            server {
                listen 80;
                listen [::]:80;
                root /var/www/your_domain/html;
                index index.html index.htm;

                server_name 103.162.20.157;

                location / {
                    try_files $uri $uri/ =404;
                }
            }

        + Verify the just added config actually works (without any syntax error)
            sudo nginx -t

        + Reload nginx 
            sudo service nginx reload 
