### Requirements

 - docker
 - golang
 - python3
   - numpy
   - Pillow
 
### Steps

 - Download the cifar-10 and cifar-100 data and after preprocessing them in the `['data': [...], 'label': [...]]` format, run `python scripts/datasampling.py <dataset_name> <# clients>` to get a sampling of data among multiple clients.
 - Set up a docker swarm network among multiple physical machines.
 - Create a docker network `attachable-fl` if not created.
 - Run `./server.sh attachable-fl` to get the fl server running.
 - Run `./client.sh attachable-fl <# clients>` on different physical machines.


To transfer assets, there is a need to run another blockchain network (`test-network-2`) and then execute `go run blockchain/asset-transfer-basic/application-go-net2/cross-chain-application-go` and `python blockchain/asset-transfer-basic/application-go-net2/sign.py` to keep the network clients running and finally `go run blockchain/asset-transfer-basic/application-go-net2/Controller.go` to initiate the transfer process.
