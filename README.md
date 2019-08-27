# Airmed Foundation - Node.js Terminal 

The [Airmed Foundation](https://airmedfoundation.thechain.tech/) is an open source initiative that provides a secure channel to store and transfer medical records. It is based on the Interplanetary File System (IPFS) and Hyperledger Fabric. The conjunction of these technologies guarantees the immutability and availability of the data.

In order to achieve a reliable file management:

* We replicate all records on the IPFS network using the Bittorrent protocol. 
* We achieve secure access to records using asymmetric cryptography. 
* We protect and store access keys in the Hyperledger Fabric blockchain.

Sharing files with the Airmed Foundation platform is pretty straightforward. Depending on their desired privacy level, one may follow two different approaches: file load with or without asymmetric encryption. We have devoted [this tutorial](https://airmedfoundation.thechain.tech/tutorial) to explain both of them.

## Instalation and Usage

The following dependencies must be downloaded and installed in order to use Airmed Foundation's Node.js terminal:

**Interplanetary File System (IPFS)**

```wget https://dist.ipfs.io/go-ipfs/v0.4.19/go-ipfs_v0.4.19_linux-amd64.tar.gz
tar xvfz go-ipfs_v0.4.19_linux-amd64.tar.gz
cd go-ipfs
sudo ./install.sh
ipfs init
```

**Docker and Docker Compose**

```
install docker
install docker-compose
```

**Nodejs, NPM and NVM**

```
nvm install 8.15.0
nvm use 8.15.0
```

**Hyperledger Fabric**

```
git clone https://github.com/hyperledger/fabric-samples
cd fabric-samples
./scripts/bootstrap.sh 1.4.0 1.4.0
cd first-network
./byfn.sh generate
./byfn.sh up
```

**Download Airmed Foundation**

```
git clone https://github.com/the-chain/airmedfoundation-terminal
cd airmedfoundation-terminal
npm install 
```

**Install Chaincode to Hyperledger Network**

```
cd airmedfoundation-terminal
docker exec -it cli peer chaincode instantiate -C mychannel -l "node" -n airmed -v v1 -c '{"Args":[]}' -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem
docker exec -it cli peer chaincode instantiate -C mychannel -l "node" -n secureRec -v v1 -c '{"Args":[]}' -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem
```

## Configuration of Airmed Foundation's server

**Edit config/datastores.js**

Change values to conect to postgreSQL. In order to install postgreSQL, you can run the following command in the terminal:
docker-compose up -d


**Edit config/policies.js**
For testing purposes, remove comment from line 20. 
That is, line 
```
//'*': 'isHTTPS',
```
should now look like
```
'*': 'isHTTPS',
```

**Edit Hyperledger configuration file**
In the file fabric-api/config/configfile.yaml, you should replace the default admin certificate paths with the actual path of your project. 
Please note that you should only modify paths from adminPrivateKey in Line 44 under Org1, and in Line 56 under Org2. Everything else must remain unchanged.

As a further note, please make sure that fabric-samble and airmedfoundation-terminal are in the same directory.

**License:** This project works under the GNU Affero General Public License v3.0. 

<a href="https://airmedfoundation.thechain.tech/"><img src="https://media.licdn.com/dms/image/C4E0BAQGs_7h67j1y0w/company-logo_400_400/0?e=1574899200&v=beta&t=KLfoiPbZSGZvBHmqhxCTYC211phfpr46j4pedsZMJ8I" width="200" height="200" /></a>



