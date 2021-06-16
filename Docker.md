# Docker

## Image

### Show all images

```
docker image list
```

### Build image

```
docker image -t image_name:tag dockerfile_location

ex: docker image -t website:1.0 .
```

### Remove image

```
docker image rm image_name
```

## Container

### Show all containers

```
docker container list
```

### Remove container

```
docker container stop container_name
docker container rm container_name
```

## Network

### Show all networks

```
docker network ls
```

### Get network information (Container IP address)

```
docker network inspect network_name

ex: docker network inspect bridge                                                           127 ⨯
[
    {
        "Name": "bridge",
        "Id": "8702b64bf0161e912bee2017e4535258d0bcd90d5922632a0453600a91a44e60",
        "Created": "2021-06-16T14:30:51.22600236+08:00",
        "Scope": "local",
        "Driver": "bridge",
        "EnableIPv6": false,
        "IPAM": {
            "Driver": "default",
            "Options": null,
            "Config": [
                {
                    "Subnet": "172.17.0.0/16"
                }
            ]
        },
        "Internal": false,
        "Attachable": false,
        "Ingress": false,
        "ConfigFrom": {
            "Network": ""
        },
        "ConfigOnly": false,
        "Containers": {
            "7e1da3923c6fbcb6fb27c618a3154bb589cdbb9b10bc933519d9fe366d484261": {
                "Name": "website-mysql",
                "EndpointID": "64d9d63ba856715d76975fbda0f62e7b5ba0bb1e1dabb5aff059447b505c5017",
                "MacAddress": "02:42:ac:11:00:02",
                "IPv4Address": "172.17.0.2/16",
                "IPv6Address": ""
            }
        },
        "Options": {
            "com.docker.network.bridge.default_bridge": "true",
            "com.docker.network.bridge.enable_icc": "true",
            "com.docker.network.bridge.enable_ip_masquerade": "true",
            "com.docker.network.bridge.host_binding_ipv4": "0.0.0.0",
            "com.docker.network.bridge.name": "docker0",
            "com.docker.network.driver.mtu": "1500"
        },
        "Labels": {}
    }
]
```

## Website MySQL server

```
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag

ex: docker run --name website-mysql -e MYSQL_ROOT_PASSWORD=django107721 -d mysql
```

