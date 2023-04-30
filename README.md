in the "conectify_users_db" folder
docker build -t conectify_users_db .

docker run -d -t -i -p 3306:3306 --name conectify_users_db conectify_users_db

in the "conectify_users_ms" folder
docker build -t conectify_users_ms .

docker run --name conectify_users_ms -p 8080:8080 -e DB_HOST=host.docker.internal -e DB_PORT=3306 -e DB_USER=conectify -e DB_PASSWORD=2023 -e DB_NAME=conectify_users_db -e URL=0.0.0.0:8080 conectify_users_ms
