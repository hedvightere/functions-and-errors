# Protein Maintenance Smart Contract

## Overview

The `proteinMaintenance` smart contract helps users manage their protein intake by tracking their initial body weight, daily protein intake, and missed protein intake days. This contract ensures that the initial body weight is above a specified minimum and that the daily protein intake meets a required threshold.

## Contract Details

### Smart Contract: `proteinMaintenance`

### SPDX-License-Identifier: MIT

### Prerequisites

- Solidity ^0.8.0
- Ethereum development environment (e.g., Remix, Truffle, Hardhat)

## Functions

### `proteinIntake(uint256 _initialWeight, uint256 _dailyProtein)`

This function records the initial body weight and daily protein intake.

**Parameters:**
- `_initialWeight` (uint256): The initial body weight in kilograms. Must be greater than 40 kg.
- `_dailyProtein` (uint256): The daily protein intake in grams. Must be more than 100 grams.

**Requirements:**
- `assert(_initialWeight > 40)`: Ensures that the initial body weight is greater than 40 kg.
- `require(_dailyProtein > 100, "Daily protein intake must be more than 100 grams")`: Ensures that the daily protein intake is more than 100 grams.

### `missedProteinDays(uint256 _daysMissed)`

This function records the number of days the user has missed their protein intake.

**Parameters:**
- `_daysMissed` (uint256): The number of missed protein intake days.

**Requirements:**
- If `_daysMissed` is greater than or equal to 5, the transaction will be reverted with the message "Missed days exceeded the limit".

## State Variables

### `initialBodyWeight`

- Type: `uint256`
- Description: Stores the initial body weight of the user.

### `currentBodyWeight`

- Type: `uint256`
- Description: Stores the current body weight of the user (not yet implemented).

### `totalMissedProteinDays`

- Type: `uint256`
- Description: Stores the total number of missed protein intake days.

## Usage

1. **Deploy the Contract:**
   Deploy the `proteinMaintenance` contract using your preferred Ethereum development environment.

2. **Record Initial Body Weight and Daily Protein Intake:**
   Call the `proteinIntake` function with appropriate values for `_initialWeight` and `_dailyProtein`.

   ```solidity
   proteinIntake(65, 120);
   ```

3. **Record Missed Protein Days:**
   Call the `missedProteinDays` function with the number of days missed.

   ```solidity
   missedProteinDays(3);
   ```

**Note:** Ensure that the values provided meet the specified requirements to avoid transaction reverts.

## License

This project is licensed under the MIT License.

