use volume for local dev

docker build -t rest-api-flask-python .
docker run -dp 5000:5000 -w /app -v "$(pwd):/app" rest-api-flask-python
