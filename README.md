# MangsatGasoline Smart Contract

## Overview
The MangsatGasoline smart contract is designed to facilitate the purchase of gasoline from various pumps. It allows the owner of the contract to add pumps with different prices per liter and initial amounts of fuel. Users can then purchase fuel from these pumps by sending the appropriate amount of ether.

## Contract Features
### Pump Struct

`pumpId:` Unique identifier for each pump.

`pricePerLiter:` Price per liter of gasoline at the pump.

`availableLiters:` Amount of gasoline available at the pump.

### Functions

`constructor:` Initializes the contract owner.

`addPump:` Allows the owner to add a new pump with a specified ID, price per liter, and initial amount of fuel.

`purchaseFuel:` Enables users to purchase fuel from a specific pump by specifying the pump ID and the desired number of liters. Users must send enough ether to cover the total cost.

`withdrawExcessFunds:` Allows users to withdraw any excess funds that were not used during a fuel purchase.

### Events

### `FuelPurchased:` 
Triggered when a user successfully purchases fuel. Contains information about the buyer, pump ID, purchased liters, and total cost.

### `ExcessFundsWithdrawn:` 
Triggered when a user withdraws excess funds. Contains information about the user and the withdrawn amount.

### Modifiers

`onlyOwner:` Restricts certain functions to be called only by the owner of the contract.

## Usage

1. Deploy the MangsatGasoline contract to an Ethereum-compatible blockchain.

2. As the owner of the contract, use the addPump function to add pumps with unique IDs, prices per liter, and initial amounts of fuel.

3. Users can purchase fuel by calling the purchaseFuel function with the desired pump ID and number of liters, sending enough ether to cover the total cost.

4. Users can withdraw any excess funds using the withdrawExcessFunds function.


### License

This project is licensed under the terms of the MIT license. See the LICENSE file for more information.
