# BlockchainToolbox
Vagrant box for building, experimenting, and hacking on blockchains. Both command line and graphical (xubuntu) versions are available. Both versions are based on Ubuntu 16.04 (xenial). All tools are bleeding edge (compiled from source in most cases) for maximum hackability!

# Building:
1. Install vagrant (https://www.vagrantup.com/downloads.html) and VirtualBox (https://www.virtualbox.org/wiki/Downloads)
2. Pull submodules: `git submodule update --init --recursive`
3. `vagrant up cli` - first time takes about 15 minutes depending on hardware
4. `vagrant ssh` - to login to the vm

*Replace cli with gui above for the graphical version.*

# Updating:
1. `git pull`
2. `git submodule update --recursive --remote`
3. `vagrant provision`

# Components:
### Ethereum CLI Tools
* Go-Ethereum (`geth`, `swarm`): https://github.com/ethereum/go-ethereum
* Solidity Compiler (`solc`): https://github.com/ethereum/solidity
* Parity (`parity`): https://github.com/paritytech/parity
* Porosity (`porosity`): https://github.com/comaeio/porosity
* DappHub (`dapp`, `seth`, `hevm`, `evmdis`): https://dapp.tools/
* Mythril (`myth`): https://github.com/ConsenSys/mythril
* Solium (`solium`): https://github.com/duaraghav8/Solium
* Embark (`embark`): https://github.com/iurimatias/embark-framework
* Truffle Framework (`truffle`, `ganache-cli`, `testrpc`): http://truffleframework.com/
* Explorer: https://github.com/carsenk/explorer
* Radare2 + EVM decompiler (`r2`): https://blog.positive.com/reversing-evm-bytecode-with-radare2-ab77247e5e53

### Ethereum GUI Tools
* Ethereum Wallet / Mist: https://github.com/ethereum/mist
* Ganache GUI: https://github.com/trufflesuite/ganache
* VS Code Solidity Plugin: https://marketplace.visualstudio.com/items?itemName=JuanBlanco.solidity

### HyperLedger Frabric
* Fabric binaries: https://hyperledger-fabric.readthedocs.io/en/release/
* Fabric Samples: https://github.com/hyperledger/fabric-samples
* IBM Marbles example: https://github.com/IBM-Blockchain/marbles

### Bitcoin CLI Tools
* Bitcoin Core (`bitcoind`, `bitcoin-cli`, `bitcoin-tx`): https://github.com/bitcoin/bitcoin

# Ansible Playbooks
The vagrant image is built using ansible playbooks which can be used on a physical or virtual Ubuntu appliance. Only Ubuntu version 16.04 is supported. The following order MUST be followed when using the playbooks:
1. `core-cli.yml`
2. `core-gui.yml` *OPTIONAL*
3. `customization-cli.yml` *OPTIONAL*
4. `ethereum-cli.yml`
5. `ethereum-gui.yml` *OPTIONAL*
6. `bitcoin-cli.yml`
7. `hlfabric.yml`

See ansible documentation for more information about playbooks: http://docs.ansible.com/ansible/latest/playbooks.html

