Functions and Errors Smart Contract
This Solidity smart contract demonstrates basic functionality related to deposits, withdrawals, and balance checks. It includes the following features:
Deposit Function:
•	The deposit function allows users to send Ether (ETH) to the contract.
•	It ensures that the deposited amount is greater than zero.
•	The deposited amount is added to the contract’s balance.
Withdraw Function:
•	The withdraw function allows the contract owner to withdraw funds.
•	It checks if the withdrawal amount is valid (greater than zero and not exceeding the contract balance).
•	If successful, the specified amount is subtracted from the balance.
•	The function also includes a custom error message.
Balance Check Function:
•	The checkBalance function allows the contract owner to view the current balance.
•	Only the contract owner can invoke this function.
Usage
•	Deploy this contract to an Ethereum-compatible blockchain.
•	Interact with the contract using an Ethereum wallet or a DApp.
•	Use the deposit function to add funds.
•	Use the withdraw function to withdraw funds (only available to the contract owner).
•	Use the checkBalance function to view the current balance.
License
This code is released under the MIT license, which permits anyone to use, modify, and distribute the code according to the terms specified in the license.
