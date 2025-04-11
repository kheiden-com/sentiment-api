# sentiment-api

This is a Docker container running a Flask-based sentiment analysis API. This API can analyze text and return sentiment scores, useful for applications like customer feedback analysis or social media monitoring.

Impact: This tool provides a simple yet effective solution for quick sentiment analysis, accessible via an easy-to-use REST API, making it versatile for various applications.

https://hub.docker.com/r/kheidencom/sentiment-api

```
docker pull kheidencom/sentiment-api
docker run -p 5000:5000 sentiment-api
```

### Linux

```bash
curl -X POST "http://localhost:5000/analyze" \
     -H "Content-Type: application/json" \
     -d '{"text":"I love this product!"}'
```

### Windows

```
Invoke-RestMethod -Uri "http://localhost:5000/analyze" `
                  -Method POST `
                  -ContentType "application/json" `
                  -Body '{"text":"I love this product!"}'
```

output:
```
sentiment
---------
    0.625
```


```
Invoke-RestMethod -Uri "http://localhost:5000/analyze" `
                  -Method POST `
                  -ContentType "application/json" `
                  -Body '{"text":"This product sucks!"}'
```

output:
```
sentiment
---------
   -0.375
```


### Building

```
docker build -t kheidencom/sentiment-api . 
docker tag sentiment-api kheidencom/sentiment-api
docker push kheidencom/sentiment-api
```

### Acknowledgements

This code was built and deployed in about 30 minutes with the help of AI.