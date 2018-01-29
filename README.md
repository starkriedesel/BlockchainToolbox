# BlockchainToolbox
Vagrant box for building, experimenting, and hacking on blockchains. Both command line and graphical (xubuntu) versions are available. Both versions are based on Ubuntu 16.04 (xenial). All tools are bleeding edge (compiled from source in most cases) for maximum hackability!

# Building:
1. Install vagrant (https://www.vagrantup.com/downloads.html) and VirtualBox (https://www.virtualbox.org/wiki/Downloads)
2. Pull submodules: `git submodule update --init --recursive`
3. `vagrant up cli` - first time takes about 15 minutes depending on hardware
4. `vagrant ssh` - to login to the vm

# Updating:
1. `git pull`
2. `git submodule update --recursive --remote`
3. `vagrant provision`

Replace cli with gui above for the graphical version.

# Components:
### Ethereum CLI Tools
* Go-Ethereum (`geth`, `swarm`): https://github.com/ethereum/go-ethereum
* Solidity Compiler (`solc`): https://github.com/ethereum/solidity
* Porosity (`porosity`): https://github.com/comaeio/porosity
* DappHub (`dapp`, `seth`, `hevm`, `evmdis`): https://dapp.tools/
* Explorer: https://github.com/carsenk/explorer
* Truffle Framework (`truffle`, `ganache-cli`, `testrpc`): http://truffleframework.com/
* Radare2 + EVM decompiler (`r2`): https://blog.positive.com/reversing-evm-bytecode-with-radare2-ab77247e5e53

### Ethereum GUI Tools
* Ethereum Wallet / Mist: https://github.com/ethereum/mist
* Ganache GUI: https://github.com/trufflesuite/ganache
* VS Code Solidity Plugin: https://marketplace.visualstudio.com/items?itemName=JuanBlanco.solidity

### HyperLedger Frabric
* Fabric binaries: https://hyperledger-fabric.readthedocs.io/en/release/
* Fabric Samples: https://github.com/hyperledger/fabric-samples
* IBM Marbles example: https://github.com/IBM-Blockchain/marbles

# Ansible Playbooks
The vagrant image is built using ansible playbooks which can be used on a physical or virtual Ubuntu appliance. Only Ubuntu version 16.04 is supported. The following order MUST be followed when using the playbooks:
1. core-cli.yml
2. OPTIONAL: core-gui.yml
3. OPTIONAL: customization-cli.yml
4. ethereum-cli.yml
5. OPTIONAL: ethereum-gui.yml
6. hlfabric.yml

See ansible documentation for more information about playbooks: http://docs.ansible.com/ansible/latest/playbooks.html

