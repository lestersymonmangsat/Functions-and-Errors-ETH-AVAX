MangsatGasoline Smart Contract
Overview
MangsatGasoline is a decentralized application (dApp) built on the Ethereum blockchain. It allows the owner to manage multiple fuel pumps, set prices, and sell fuel to users. Users can purchase fuel by sending Ether to the contract, which will be transferred to the owner.

Features
Pump Management: The owner can add new fuel pumps with a specific ID, price per liter, and initial quantity of fuel.
Fuel Purchase: Users can purchase fuel by specifying the pump ID and the desired quantity of liters. The payment is made in Ether.
Smart Contract Details
Pump Structure
The contract uses a Pump structure to represent each fuel pump:

pumpId (uint256): The unique identifier for the pump.
pricePerLiter (uint256): The price of one liter of fuel in Wei.
availableLiters (uint256): The amount of fuel available in the pump.
State Variables
pumps (mapping): A mapping from pump IDs to Pump structures.
owner (address): The address of the contract owner.
Events
FuelPurchased: Emitted when fuel is purchased, with details about the buyer, pump ID, liters purchased, and total cost.
Modifiers
onlyOwner: Restricts access to certain functions to only the contract owner.
Functions
constructor()
The constructor sets the contract deployer as the owner.

addPump(uint256 _pumpId, uint256 _pricePerLiter, uint256 _initialLiters) external onlyOwner
Adds a new pump with the given ID, price per liter, and initial quantity of fuel. This function can only be called by the owner.

purchaseFuel(uint256 _pumpId, uint256 _liters) external payable
Allows users to purchase fuel from a specified pump. It checks if the pump has enough fuel available and if the user has sent enough Ether. The Ether is transferred to the owner, and the fuel quantity is updated.

Usage
Deployment
Deploy the contract using Remix, Truffle, or any Ethereum development framework. The owner is set to the deployer's address.

Adding Pumps
The owner can add pumps using the addPump function:

solidity
Copy code
function addPump(uint256 _pumpId, uint256 _pricePerLiter, uint256 _initialLiters) external onlyOwner
Purchasing Fuel
Users can purchase fuel by calling the purchaseFuel function with the pump ID and the desired quantity of liters. The payment should be sent along with the transaction:

solidity
Copy code
function purchaseFuel(uint256 _pumpId, uint256 _liters) external payable
Example
Owner adds a pump:
solidity
Copy code
addPump(1, 1000000000000000, 1000) // Pump ID: 1, Price: 0.001 Ether per liter, Initial Quantity: 1000 liters
User purchases fuel:
solidity
Copy code
purchaseFuel(1, 10) // Purchases 10 liters from pump ID 1, costing 0.01 Ether
License
This project is licensed under the MIT License - see the LICENSE file for details.
