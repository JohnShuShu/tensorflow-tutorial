## Installation instructions

- Clone this repository
- Install Docker
- (If on Windows or Mac:) Start docker shell
- Run the following commands

```bash
docker run \
    --name jupyter \
    -d \
    -v $(pwd)/notebooks:/root/notebooks \
    -v $(pwd)/logs:/root/logs \
    -p 8888:8888 \
    b.gcr.io/tensorflow/tensorflow \
    /run_jupyter.sh /root/notebooks

docker run \
   --name tensorboard \
   -d \
   -v $(pwd)/logs:/root/logs \
   -p 6006:6006 \
   b.gcr.io/tensorflow/tensorflow \
   tensorboard --logdir /root/logs
```
