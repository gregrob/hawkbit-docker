# hawkBit Docker
<img src="hawkbit.png" width="15%" height="15%"> <br />

[hawkBit](https://www.eclipse.org/hawkbit/) is a back-end framework for rolling out software updates. <br />
My container configuration is for rolling out updated to my IoT devices.

The following folder structure is used for the container:
```
    .
    └── persistent         # Persistent data
      ├── hawkbit          
      | ├── artifactrepo   # hawkBit artifact repository (i.e. binaries)
      | └── data           # hawkBit data
      ├── mysql            # MySQL database
      └── rabbitmq         # RabbitMQ data

```

## Getting Started

1. Rename <code>docker-env.sh.template</code> to <code>docker-env.sh</code> and enter your username and password details.

2. <code>./docker-start.sh</code> to bring the container and all services up.

3. <code>./docker-stop.sh</code> to bring the container and all services down.

## Service mappings

Service | Description | Port/s
--- | --- | ---
hawkBit | Update manager web interface / API. | 9090
MySQL | Database for hawkBit. | No ports exposed.
Adminer | Database viewer / editor web interface. | 9091
RabbitMQ | Message broker web interface. | 15672
Simulator | Commented out but when enabled web interface.  | 8083
