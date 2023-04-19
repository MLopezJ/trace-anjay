# Trace Anjay
> Download Anjay, update example and trace their packets with WireShark

[Anjay](https://github.com/AVSystem/Anjay) is a LwM2M Client develop by AV System and [WireShark](https://www.wireshark.org/) is a packet analyzer. The idea is to use WireShark to trace the comunication between the LwM2M Client (Anjay) and the LwM2M Server (Coiote), and in this way undertand the behavior of Coiote and how to show and update LwM2M Objects in its web application. 


## Install Anjay

```
git clone git@github.com:AVSystem/Anjay.git
```

### Install dependencies

```
// Mac OS
brew install cmake mbedtls openssl
```

### Install AVS Commons
```
// Inside Anjay folder
https://github.com/AVSystem/avs_commons/

cd avs_commons
cmake . &&
make &&
make install
```

### Update Submodules
```
// /Anjay
git submodule update --init
```
## Test Anjay: 

### Build demo client

```
cmake . -DDTLS_BACKEND="mbedtls" && make -j
```

### Start tracing with WireShark

Execute demo

```
./output/bin/demo --endpoint-name urn:imei:000000000000004 --server-uri coap://eu.iot.avsystem.cloud:5683
```

Execute Examples

```
cd examples/tutorial
// then select the example you want to execute and get into it, for example BC-Initialization
cd BC-Initialization
cmake . && make
// execute build (anjay-bc-initialization in this case) with device name as param (urn:imei:000000000000000)
./anjay-bc-initialization urn:imei:000000000000000
```

# Results

// TODO
