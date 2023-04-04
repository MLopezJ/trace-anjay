# Trace Anjay
> Download Anjay, update example and trace their packets with WireShark

[Anjay](https://github.com/AVSystem/Anjay) is a LwM2M Client develop by AV System and [WireShark](https://www.wireshark.org/) is a packet analyzer. The idea is to use WireShark to trace the comunication between the LwM2M Client (Anjay) and the LwM2M Server (Coiote), and in this way undertand the behavior of Coiote and how to show and update LwM2M Objects in its web application. 


## Install Anjay

### Check dependencies

```
// cmake
sudo apt  install cmake  # version 3.22.1-1ubuntu1.22.04.1

// Python 3
python3 --version

// OpenSSL
sudo apt install libssl-dev

//avs_commons
git clone https://github.com/AVSystem/avs_commons.git
cd avs_commons

// /Anjay/avs_commons
sudo apt install zlib1g-dev

cmake . &&
make &&
sudo make install
cd ..
```

### Update Submodules
```
// /Anjay
git submodule update --init

cmake .  -DDTLS_BACKEND="openssl"  && make && sudo make install
```
### Test Anjay

* cd `examples/tutorial/BC-Initialization`
* `cmake . && make`
* `./anjay-bc-initialization urn:imei:000000000000004`
* Expected result: `INFO [anjay] [/home/ubuntu/Anjay/src/core/anjay_core.c:292]: Initializing Anjay 3.3.1`

## Update example

// Uses nosec mode
// TODO

## WireShark result

// TODO
