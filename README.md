SmartCashLib
==========

**.NET SmartCash library**

Features
--------

- Fully compatible and up-to-date with [SmartCash Core 1.1,1](https://github.com/SmartCash/smartcash/releases/tag/v1.1.1) RPC API.
- Strongly-typed structures for complex RPC requests and responses.
- Implicit JSON casting for all RPC messages.
- Extended methods for every-day scenarios where the built-in methods fall short.
- Exposure of all [RPC API's functionality](https://en.bitcoin.it/wiki/Original_Bitcoin_client/API_calls_list) as well as the extended methods through a single interface.
- Custom RPC exceptions.
- Supports all Bitcoin clones.
- Can operate on unlimited daemons with a single library reference.
- Disconnected raw RPC connector included for quick'n'dirty debugging.
- Handles and relays RPC internal server errors along with their error code.
- Can work without a `.config` file.
- Fully compatible with [Mono](http://www.mono-project.com/).
- Fully configurable.

Instructions
------------------------

- Locate your `smartcash.conf` file (in Windows it's under: `%AppData%\Roaming\SmartCash`, if it's not there just go ahead and create it) and add these lines:
	- rpcuser = MyRpcUsername
	- rpcpassword = MyRpcPassword
	- server=1
	- txindex=1

- Edit the `app.config` file in the Console test client to best fit your needs. Make sure you also update the `smartcash.conf` file when you alter the `SmartCash_RpcUsername` and `SmartCash_RpcPassword` parameters.

- You can initialize by its interface specification:
	- `ISmartCashService BitcoinService = new SmartCashService();`

Configuration
-------------

Sample configuration:

	﻿<?xml version="1.0" encoding="utf-8"?>
	<configuration>
		<appSettings>

			<!-- SmartCashLib settings start -->

				<!-- Shared RPC settings start -->
				<add key="RpcRequestTimeoutInSeconds" value="10" />
				<!-- Shared RPC settings end -->

				<!-- SmartCash settings start -->
				<add key="SmartCash_DaemonUrl" value="http://localhost:9678" />
				<add key="SmartCash_DaemonUrl_Testnet" value="http://localhost:19678" />
				<add key="SmartCash_WalletPassword" value="MyWalletPassword" />
				<add key="SmartCash_RpcUsername" value="MyRpcUsername" />
				<add key="SmartCash_RpcPassword" value="MyRpcPassword" />
				<!-- SmartCash settings end -->

			<!-- SmartCashLib settings end -->
			
		</appSettings>
	</configuration>

