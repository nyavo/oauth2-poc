Oauth2 POC
========================
POC oauth2 server with Symfony 3.4 and FOS Oauth2 associated with FOS User Bundle

# Installation
- docker-compose -f .docker/docker-compose.yml up -d
- docker exec -ti docker_web_1 /bin/bash -c "composer install"
- docker exec -ti docker_web_1 /bin/bash -c "php bin/console doctrine:schema:update --dump-sql --force"

# Create a client
Please refer to the documentation of FOS Oauth2 : https://github.com/FriendsOfSymfony/FOSOAuthServerBundle/blob/master/Resources/doc/index.md#creating-a-client

## Available grant type for fos oauth2
`authorization_code`, `password`, `refresh_token`, `token`, `client_credentials`

## More article about oauth2 process
https://aaronparecki.com/oauth-2-simplified