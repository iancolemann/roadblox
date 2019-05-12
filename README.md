# RoadBlox
Roadblox Miner v0.4.2.0 - AMD Dual GPU Miner | ETH + BTM

## Roadblox Miner v0.4.2.0

Hello, I would like to announce the release of Roadblox Miner. The first stable version of Roadblox Miner is v0.4.2.0 

Roadblox miner can dual mine Bytom and Ethereum on AMD GPUs.


## Performance Estimates Coming Soon!

## Features 

Support Windows & Linux.
Support for AMD GPUs
Configuration for backup pool and more
SSL Connection Support

Dev Fee is 2% on dualmine or 1.5% on single mine


Requirements are as follows:

BTM : 1GB
ETH : 4GB
BTM + ETH : 4GB


## Sample Usages

### BTM

f2pool:        nbminer -a tensority -o stratum+tcp://btm.f2pool.com:9221 -u bm1xxxxxxxxxx.worker
antpool:      nbminer -a tensority -o stratum+tcp://stratum-btm.antpool.com:6666 -u username.worker
matpool.io: nbminer -a tensority -o stratum+tcp://btm.matpool.io:8118 -u bm1xxxxxxxxxxx.worker

ETH

ethermine:  nbminer -a ethash -o ethproxy+tcp://asia1.ethermine.org -u 0x12343bdgf.worker
sparkpool:   nbminer -a ethash -o ethproxy+tcp://cn.sparkpool.com:3333 -u 0x12343bdgf.worker
f2pool:        nbminer -a ethash -o ethproxy+tcp://eth.f2pool.com:8008 -u 0x12343bdgf.worker
nanopool:   nbminer -a ethash -o ethproxy+tcp://eth-asia1.nanopool.org:9999 -u 0x12343bdgf.worker
nicehash:    nbminer -a ethash -o ethnh+tcp://daggerhashimoto.eu.nicehash.com:3353 -u btc_address.worker

BTM+ETH

f2pool:        nbminer -a tensority_ethash -o stratum+tcp://btm.f2pool.com:9221 -u btm_address.btm_worker -do ethproxy+tcp://eth.f2pool.com:8008 -du eth_address.eth_worker


CMD options

 -h, --help    Displays this help.
 -v, --version    Displays version information.
 -c, --config <config file path>    Use json format config file rather than cmd line options.
 -a, --algo <algo>    Select mining algorithm
                      BTM: tensority
                      ETH: ethash
                      BTM+ETH: tensority_ethash[
 --api  <host:port>    The endpoint for serving REST API.
 -o, --url <url>    Mining pool url.
                    BTM: stratum+tcp://btm.f2pool.com:9221]
                    BTM with SSL: stratum+ssl://btm.f2pool.com:9443
                    ETH: ethproxy+tcp://eth.f2pool.com:8008
 -u, --user <user>    User used in Mining pool, wallet address or username.
 -o1, --url1 <url> url for backup mining pool 1.
 -u1, --user1 <user> username for backup mining pool 1.
 -o2, --url2 <url> url for backup mining pool 2.
 -u2, --user2 <user> username for backup mining pool 2.
 -di, --secondary-intensity <intensity>    The relative intensity for ETH when dual mining. recommend: 8 - 24, default to 16.
 -do, --secondary-url <url>    ETH mining pool when dual mining.
 -du, --secondary-user <user>    ETH username when dual mining.
 -do1, --secondary-url1 <url>    Backup 1 ETH mining pool when dual mining.
 -du1, --secondary-user1 <user>    Backup 1 ETH username when dual mining.
 -do2, --secondary-url2 <url>    Backup 2 ETH mining pool when dual mining.
 -du2, --secondary-user2 <user>    Backup 2 ETH username when dual mining.
 -d, --devices <devices>    Specify GPU list to use. Format: "-d 0,1,2,3" to use first 4 GPU.
 -strict-ssl    Check validity of certificate when use SSL connection.
 --cuckoo-intensity <intensity>    Set intensity of cuckoo, cuckaroo, cuckatoo, [1, 12]. Set to 0 means autumatically adapt. Default: 0.
 -log    Generate log file named `log_<timestamp>.txt`.
 -long-format    Use 'yyyy-MM-dd HH:mm:ss,zzz' for log time format.
 --device-info Print device cuda information.


## GPU Tuning

BTM + ETH
Suitable `secondary intensity` depends on the ratio of `core performance / memory bandwidth`
GPU with relative low memory bandwidth, eg. 1070ti, could tune down the `di`. Otherwise tune up.
The ratio changes with different `core`, `tdp`, `memory`  settings when overclock GPU.

BTM
Bytom mining performance depend heavily on GPU core, instead of GPU memory.
Miner can gain beffer hashrate if tuning down GPU memory frequency.
For example, using MSI Afterburner to turn down GPU memory to -500.


