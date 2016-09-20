# Kube-API

This interface provides the connection credentials to connect to a kubernetes
api-server.


# Provides

Kubernetes API credentials are sent in the following dict structure:

```python
{"private-address": "",
 "port": "8080",
 "tls": "false",
 "tls_key": "",
 "tls_cert": "",
 "tls_ca": ""}
```

This format may change from V1 while the interface is in heavy development. YMMV
