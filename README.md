# Block[Chain] Alchemy Laboratory Framework

The source code of originally based on post on [Building a Blockchain](https://medium.com/p/117428612f46) of Daniel van Flymen.

## Installation

1. Make sure [Python](https://www.python.org/downloads/) 2 or 3 is installed.


2. Install requirements (preferably inside a [virtual environment](https://docs.python.org/3/tutorial/venv.html)).  

```
$ pip install -r requirements.txt
```

5. Run the server:
    * `$ python blockchain.py -p 5001 -db pow.db -v pow`

## Parameters

    '-p', '--port', default=5000, type=int, help='port to listen on'
    '-db', '--database', default='', help='db file, if not passed, then no persistance'
    '-v', '--variant', default='pow', help='variant of blockchain "pow" or "pos"'
    '-s', '--socket', default=6001, type=int, help='p2p port to listen on'
    '-d', '--difficulty', default=2, help='initial difficulty'
    '-k', '--keystore', default='/tmp/private_key.pem', help='where the keystore is located.'

## Blockchain Mininet network
To install mininet please follow http://mininet.org/vm-setup-notes/, a fresh mininet virtual environment setup is recommended. For the VM Mininet 2.2.2 on Ubuntu 14.04 LTS - 64 bit follow these steps:
Clone the project into a directory. `cd` to cloned directory.
```
sudo python setup.py install
sudo easy_install dist/bal-xxx.egg
sudo ln -s /home/mininet/bal/bal/blockchain.py /usr/local/bin/blockchain.py
```
change `#!/bin/env python` in `blockchain.py` to `#!usr/bin/env python`.

Mininet's custom setup for BAL classes balmn.py add several types of hosts:
* pow -- bcnode.POWNode
* pos -- bcnode.POSNode

For example:
```
mn --custom=balmn.py --host=pos
```

Simulating (under bal/bal directory):
```
./bcmn_test.py
```

## More information
you may find in the project's [Wiki](https://github.com/BAlchemyLab/bal/wiki).
