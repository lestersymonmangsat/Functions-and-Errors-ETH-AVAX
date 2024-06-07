# MangsatGasoline Smart Contract

## Overview
The `MangsatGasoline` smart contract is designed to simulate a simple gasoline refueling system. It allows a limited number of refuels and ensures that each address can only refuel once.
### Features
`Single Refuel Per Address:` Each address can refuel only once.

`Maximum Refuels Limit:` A maximum of 100 refuels is allowed.

`Event Logging:` Refuel events are logged for transparency.

`Utility Functions:` Additional functions to demonstrate the use of `assert` and `require` statements.

## Contract Details
### State Variables

`mapping(address => bool) private hasRefueled: ` Tracks if an address has refueled.

`uint256 private refuelCount:`  Counter for the total number of refuels.

`uint256 public constant MAX_REFUELS:` Constant representing the maximum number of refuels allowed (100).

### Functions

`refuel()`

Allows an address to refuel their vehicle if they haven't already and the maximum refuels limit hasn't been reached.

```
function refuel() public canRefuel {
    hasRefueled[msg.sender] = true;
    refuelCount++;
    emit Refuel(msg.sender);
}
```

`totalRefuelCount() `

Returns the total number of refuels.

```
function totalRefuelCount() public view returns (uint256) {
    return refuelCount;
}
```

`hasDriverRefueled(address driver)`

Checks if a specific address has refueled.

```
function hasDriverRefueled(address driver) public view returns (bool) {
    return hasRefueled[driver];
}
```
    
`assertGasoline(uint256 a, uint256 b)`

Demonstrates the use of an `assert` statement by performing a division operation

```
function assertGasoline(uint256 a, uint256 b) public pure returns (uint256) {
    assert(b != 0);
    return a / b;
}
```

`revertGasoline(uint256[] memory data)`

Demonstrates the use of a require statement and a revert statement.

```
function revertGasoline(uint256[] memory data) public pure {
    require(data.length > 0, "Data array must not be empty");
    revert("Something went wrong");
}
```

### Events
`event Refuel(address indexed driver):` Emitted when a driver refuels.

### Modifiers

`modifier canRefuel()` Ensures that an address can refuel only if it has not done so before and the maximum refuels limit has not been reached.

## Usage

1. Deploy the Contract: Deploy the `MangsatGasoline`contract to your preferred Ethereum network.

2. Refuel: Call the `refuel()` function to refuel your vehicle. Ensure you haven't refueled before and the maximum limit hasn't been reached.

3. Check Refuel Status: Use `hasDriverRefueled(address driver)` to check if a specific address has refueled.

4. View Total Refuels: Call `totalRefuelCount()` to get the current number of refuels.


### License

This project is licensed under the terms of the MIT license. See the LICENSE file for more information.
