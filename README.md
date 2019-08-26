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



**Nodejs, NPM and NVM**

**Hyperledger Fabric**

**Download Airmed Foundation**

```
git clone https://github.com/the-chain/airmedfoundation-terminal
cd airmedfoundation-terminal
npm install 
```


**License:** This project works under the GNU Affero General Public License v3.0. 

