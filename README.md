# hcm-k8s


```
docker run -d     --net test.net     --name proxy.test.net     -p 9999:9999  my-haproxy
```


TLS ingress
```

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -out frontend-tls.crt -keyout frontend-tls.key -subj "/CN=nelab.ddns.umass.edu/O=frontend-tls"


openssl req -x509 -nodes -days 365 -newkey rsa:2048 -out api-tls.crt -keyout api-tls.key -subj "/CN=nelab.ddns.umass.edu/O=api-tls"


kubectl create secret tls frontend-secret --key ./frontend-tls.key --cert frontend-tls.crt

kubectl create secret tls api-secret --key ./api-tls.key --cert api-tls.crt



```