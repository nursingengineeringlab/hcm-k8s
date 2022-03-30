# hcm-k8s


```
docker run -d     --net test.net     --name proxy.test.net     -p 9999:9999  my-haproxy
```


TLS ingress
```

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -out frontend-tls.crt -keyout frontend-tls.key -subj "/CN=nelab.ddns.umass.edu/O=frontend-tls"


kubectl create secret tls frontend-secret --key ./frontend-tls.key --cert frontend-tls.crt



```