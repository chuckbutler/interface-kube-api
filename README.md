# Kube-API

This interface provides the connection credentials to connect to a kubernetes
api-server.


# Provides

Kubernetes API credentials are sent in the following dict structure:

```python
{"private-address": "",
 "port": "8080",
}
```

This format may grow over time as the kube-apiserver becomes more robust. If
your consumer depends on TLS credentials, a relation with the requisit CA will
need to be established before you can consume the information emitted from
this interface.

### Example

```python

@when('{relation_name}.connected')
def send_api_details():
    credentials = {'port': port}
    conv = self.conversation()
    conv.set_remote(data=credentials)
```

# Requires

```python
@when('{relation_name}.available')
def get_api_details(api):
    data = api.get_data()
    print(data['private-address'])
    print(data['port'])
```

