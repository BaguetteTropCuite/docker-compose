## SETUP GUACAMOLE VIA Docker compose

Basé sur la documentation officielle : [Guacamole Documentation](https://guacamole.apache.org/doc/gug/guacamole-docker.html)

=> mv .env.exemple .env

Editez le fichier .env

=> docker compose -f compose.yaml up -d

(La stack peut mettre plusieurs minutes à démarrer, attendez 10 minutes avant d'essayer de déboguer.)


## Idéalement, il faut configurer un reverse proxy comme Nginx Proxy Manager en frontal.

## TOTP

Pour configurer une 2FA avec le TOTP, j'ai mappé un volume dans le conteneur guacamole pour charger les extensions en .jar de manière persitente.

=> Une fois le dossier sur la machine hote, il est possible d'ajouter des .jar (modules guacamole) pour ajouter des extensions.

=> Documentation sur le TOTP : [Configuré le TOTP sur guacamole](https://guacamole.apache.org/doc/gug/totp-auth.html)
