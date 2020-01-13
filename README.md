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

```bash
curl http://localhost:8080
```

You should see something like:

```
Hello GPU!

+-----------------------------------------------------------------------------+
| NVIDIA-SMI 418.67       Driver Version: 418.67       CUDA Version: 10.1     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  Tesla K80           Off  | 00000000:00:04.0 Off |                    0 |
| N/A   37C    P8    27W / 149W |      0MiB / 11441MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID   Type   Process name                             Usage      |
|=============================================================================|
|  No running processes found                                                 |
+-----------------------------------------------------------------------------+

```
