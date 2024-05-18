# Boilerplate Gateway nginx with Let’s Encrypt on docker-compose

`init-letsencrypt.sh` fetches and ensures the renewal of a Let’s
Encrypt certificate for one or multiple domains in a docker-compose
setup with nginx.
This is useful when you need to set up nginx as a reverse proxy for an
application.

## Installation
1. [Install docker-compose](https://docs.docker.com/compose/install/#install-compose).

2. Modify configuration:
- Add domains in data/nginx/conf.d/app.conf and init-letsencrypt.sh
- Replace all occurrences of example.org with primary domain (the first one you added to init-letsencrypt.sh) in data/nginx/conf.d/app.conf

3. Run the init script:
```
./init-letsencrypt.sh
```
4. Uncommand part in data/nginx/conf.d/app.conf for 443 port and run the server:
```
docker-compose up
```
5. if you have problem and issue after edit proxy pass you can run:
```        
docker-compose restart nginx
```

## Usage VSCOde Online

Access your VSCode environment by navigating to `http://<ip-or-localhost>:8308` in a web browser. Replace `<ip-or-localhost>` with the actual IP address or `localhost` if running on your local machine. Enter the password defined in the `PASSWORD` environment variable when prompted.

## License
All code in this repository is licensed under the terms of the `MIT License`. For further information please refer to the `LICENSE` file.
