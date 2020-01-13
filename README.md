# nvidiasmi-http

A simple HTTP API that just returns the output of `nvidia-smi` using Flask.

# Run locally

Requirements:

- [nvidia-docker](#)
- An Nvidia GPU compatible with CUDA

### 1 - Build the Docker image:

```bash
docker build nvidiasmi-http .
```

### 2 - Start the server:

```bash
docker --runtime=nvidia-docker -p 8080:80 --rm run nvidiasmi-http
```

### 3 - Test the API, for example using cURL:

```
curl http://localhost:8080
```
