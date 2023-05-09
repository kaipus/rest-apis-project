## use volume for local dev

```
docker build -t IMAGE_NAME .
docker run -dp 5000:5000 -w /app -v "$(pwd):/app" IMAGE_NAME
```

## replace command line in Dockerfile
```
docker run -dp 5000:5000 -w /app -v "$(pwd):/app" IMAGE_NAME sh -c "flask run"
docker run -p 5000:5000 -w /app -v "$(pwd):/app" rest-api-project sh -c "flask run --host 0.0.0.0"
```

## backgroud worker
```
docker run -w /app rest-api-email sh -c "rq worker -u rediss://red-cgsdiorh4hsgc10rm9b0:kohSNdTQzDaNjeyvi0xatnMgMxsxvrPr@oregon-redis.render.com:6379 emails"
docker run -p 5000:80 rest-api-email
```