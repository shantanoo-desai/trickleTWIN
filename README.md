### Fountain Coding Practical Application

#### Testing Devices

* Laptop with __Ubuntu 14.04 LTS__

* Raspberry Pi-2 Model B

* Using IPv6 Multicast Addressing `ff02::1`

* Code in __Python-3.x__

#### Requirements

* Use `python3-pip` on Ubuntu-14.04 LTS for installing the __PyPi__ module of *LT-Codes* by Anson Rosenthal
```
    sudo apt-get install python3-pip
    pip3 install lt-code
```

* Since no __Python-3.4__ available for Raspberry Pi-2 (still in Beta)
```
	git clone https://github.com/anrosent/LT-Code.git
	cd LT-Code/
	sudo python3 setup.py install
```
#### Files

1. __Fountain.py__: Server(Laptop)

    * File to be sent: a File.tar file which consists of `config.json` and other `.ihex` files

2. __Bucket.py__ : Receiver (Raspberry Pi 2)

	* Files received from Fountain will be stored on a designated folder on Pis

3. __twinSocket.py__ : Socket Wrapper for UDP Datagrams

4. __trickle.py__ : *Trickle Algorithm (RFC 6206)* from [Tony Cheneau](https://github.com/tcheneau/simpleRPL/blob/master/RPL/trickle.py)

#### Added Features (v2.1-beta)

* Controlled dissemination of __Fountain__ in order to not flood the shared network of WiFi

* Added Version Check using Trickle Algorithm

* Optimized Trickle Parameters according to Environment

* ~~`socket.timeout()`~~

* added __mDNS__ name for received messages

