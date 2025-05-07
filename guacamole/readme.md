## SETUP GUACAMOLE VIA Docker compose

=> mv .env.exemple .env

Editez le fichier .env

=> docker compose -f compose.yaml up -d

(La stack peut mettre plusieurs minutes à démarrer, attendez 10 minutes avant d'essayer de déboguer.)


## Idéalement, il faut configurer un reverse proxy comme Nginx Proxy Manager en frontal.
