npm install -g truffle
truffle --version
truffle init
truffle compile

migrations folder ->
	1_simpleStorage.js(FILE NAME) (numbering sequence decide which contract will deploy first)
	
	var SimpleStorage = artifacts.require("./SimpleStorage.sol");

	module.exports = function(deployer) {
    		deployer.deploy(SimpleStorage);
	}

truffle-config.js ->
	For deploymeny on GANACHE
	uncomment deployment
	change RPC server to 7545

truffle migrate
truffle migrate --reset (for better detection in changes in smart contracts)


truffle-config.js ->
	For deployment on testnet
	uncomment goerli and change its name to sepolia and change the network id to metamask's sepolia id
		require('dotenv').config();
		const { MNEMONIC, PROJECT_ID } = process.env;
		const HDWalletProvider = require('@truffle/hdwallet-provider');
	npm install dotenv (for safe deployment, hiding API key)
	create .env file and 
		MNEMONIC = lucky poverty lunch exile drift fade split armor two antique angle bench (metamask)
		PROJECT_ID = 2GM6qC2SjzxPKia7ATEZm3olibuQNMmE (Alchemy API)
	npm install @truffle/hdwallet-provider
	
truffle migrate --sepolia network --reset