## SETUP GUACAMOLE VIA Docker compose

Basé sur la documentation officielle : [Guacamole Documentation](https://guacamole.apache.org/doc/gug/guacamole-docker.html)

=> mv .env.exemple .env

Editez le fichier .env

=> docker compose -f compose.yaml up -d

(La stack peut mettre plusieurs minutes à démarrer, attendez 10 minutes avant d'essayer de déboguer.)


## Idéalement, il faut configurer un reverse proxy comme Nginx Proxy Manager en frontal.

## TOTP

Pour configurer une 2FA avec le TOTP, j'ai mappé un volume dans le conteneur guacamole pour charger les extensions en .jar de manière persitente.

=> Pour télécharger des extensions : ex 1.6.0 : https://guacamole.apache.org/releases/1.6.0/      /!\ Attention, la version du conteneur doit parfaitement match la version de l'extension.

=> wget "https://apache.org/dyn/closer.lua/guacamole/1.6.0/binary/guacamole-auth-totp-1.6.0.tar.gz?action=download" -O guacamole-auth-totp-1.6.0.tar.gz      => Télécharger l'archive avec le .jar

=> tar -xzf guacamole-auth-totp-1.6.0.tar.gz

=> mv guacamole-auth-totp-1.6.0/guacamole-auth-totp-1.6.0.jar /var/lib/docker/volumes/guacamole_guacamole_extensions/_data/                                  => Déplacer le .jar dans le volume du conteneur guacamole pour la persistance.

=> docker restart guacamole

=> Documentation sur le TOTP : [Configuré le TOTP sur guacamole](https://guacamole.apache.org/doc/gug/totp-auth.html)
