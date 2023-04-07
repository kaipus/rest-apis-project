## use volume for local dev

```
docker build -t IMAGE_NAME .
docker run -dp 5000:5000 -w /app -v "$(pwd):/app" IMAGE_NAME
```

## replace command line in Dockerfile
```
docker run -dp 5000:5000 -w /app -v "$(pwd):/app" IMAGE_NAME sh -c "flask run"
```