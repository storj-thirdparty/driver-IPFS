# driver-ipfs (uplink v1.0.5)

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/f855c19791c240b6b7b930fa712bd9ed)](https://app.codacy.com/gh/storj-thirdparty/driver-ipfs?utm_source=github.com&utm_medium=referral&utm_content=storj-thirdparty/driver-ipfs&utm_campaign=Badge_Grade_Dashboard)
[![Go Report Card](https://goreportcard.com/badge/github.com/storj-thirdparty/driver-ipfs)](https://goreportcard.com/report/github.com/storj-thirdparty/driver-ipfs)
![Cloud Build](https://storage.googleapis.com/storj-utropic-services-badges/builds/driver-ipfs/branches/master.svg)


## Overview

The IPFS Driver connects to an IPFS server, takes a backup of the specified files and uploads the backup data on Storj network.

```bash
Usage:
  driver-ipfs [command] <flags>

Available Commands:
  help        Help about any command
  store       Command to upload data to a Storj V3 network.
  download    Command to download data from a Storj V3 network.
  version     Prints the version of the tool

```

`store` - Connect to the specified IPFS (default: `ipfs_property.json`). Back-up of the IPFS is generated using tooling provided by IPFS and then uploaded to the Storj network.  Connect to a Storj v3 network using the access specified in the Storj configuration file (default: `storj_config.json`).

`download` - Connect to the specified IPFS (default: `ipfs_property.json`). Connect to a Storj v3 network using the access specified in the Storj configuration file (default: `storj_config.json`). Download the data using file hash and download location specified in the Storj download configuration file (default: `storj_download.json`).

Sample configuration files are provided in the `./config` folder.

> Note: This driver can only be used for uploading and downloading files, directories are not yet supported.




## Requirements and Install

To build from scratch, [install the latest Go](https://golang.org/doc/install#install).

> Note: Ensure go modules are enabled (GO111MODULE=on)



### Option #1: clone this repo (most common)

To clone the repo

```
git clone https://github.com/storj-thirdparty/driver-ipfs.git
```

Then, build the project using the following:

```
cd driver-ipfs
go build
```



### Option #2:  ``go get`` into your gopath

To download the project inside your GOPATH use the following command:

```
go get github.com/storj-thirdparty/driver-ipfs
```


### Connect to IPFS Server

Make sure you are connected to IPFS server. If not, run the ipfs daemon in another `terminal` to join your node to the public network:

```
$ ipfs daemon
```


## Run (short version)

Once you have built the project run the following commands as per your requirement:

### Get help

```
$ ./driver-ipfs --help
```

### Check version

```
$ ./driver-ipfs --version
```

### Create backup from IPFS and upload to Storj

```
$ ./driver-ipfs store
```
