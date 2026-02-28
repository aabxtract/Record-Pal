# 🔢 Counter Smart Contract

A minimal, gas-efficient counter smart contract built with [Foundry](https://book.getfoundry.sh/). This contract provides basic increment and set functionality for an on-chain counter, serving as a clean starting point for Solidity development.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Contract Details](#contract-details)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Testing](#testing)
- [Deployment](#deployment)
- [License](#license)

---

## Overview

The **Counter** contract is a straightforward Solidity smart contract that manages a single `uint256` state variable. It supports two operations:

- **Set** — assign an arbitrary value to the counter.
- **Increment** — increase the counter by 1.

> **Solidity Version:** `^0.8.13`  
> **License:** UNLICENSED

---

## Contract Details

### State Variables

| Name     | Type      | Visibility | Description                    |
| -------- | --------- | ---------- | ------------------------------ |
| `number` | `uint256` | `public`   | The current value of the counter |

### Functions

| Function                            | Visibility | Description                                 |
| ----------------------------------- | ---------- | ------------------------------------------- |
| `setNumber(uint256 newNumber)`      | `public`   | Sets the counter to the provided value      |
| `increment()`                       | `public`   | Increments the counter by 1                 |

---

## Getting Started

### Prerequisites

- [Foundry](https://book.getfoundry.sh/getting-started/installation) installed on your machine.

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd games

# Install dependencies
forge install
```

---

## Usage

### Build

Compile the smart contracts:

```bash
forge build
```

### Format

Format the Solidity source files:

```bash
forge fmt
```

### Gas Snapshots

Generate a gas usage report:

```bash
forge snapshot
```

### Local Node

Spin up a local Ethereum node with Anvil:

```bash
anvil
```

---

## Testing

The project includes both unit tests and fuzz tests located in `test/Counter.t.sol`.

### Test Suite

| Test                        | Type     | Description                                         |
| --------------------------- | -------- | --------------------------------------------------- |
| `test_Increment()`          | Unit     | Verifies that `increment()` increases the counter by 1 |
| `testFuzz_SetNumber(uint256 x)` | Fuzz | Verifies that `setNumber()` correctly stores any `uint256` value |

### Run Tests

```bash
# Run all tests
forge test

# Run tests with verbose output
forge test -vvvv

# Run a specific test
forge test --match-test test_Increment
```

---

## Deployment

Deploy the contract using the included deployment script at `script/Counter.s.sol`:

```bash
forge script script/Counter.s.sol:CounterScript \
  --rpc-url <your_rpc_url> \
  --private-key <your_private_key> \
  --broadcast
```

> ⚠️ **Security Note:** Never commit your private key to version control. Use environment variables or a `.env` file (added to `.gitignore`) to manage sensitive credentials.

---

## Project Structure

```
.
├── src/
│   └── Counter.sol          # Main counter contract
├── test/
│   └── Counter.t.sol        # Unit & fuzz tests
├── script/
│   └── Counter.s.sol        # Deployment script
├── lib/                     # Dependencies (forge-std)
├── foundry.toml             # Foundry configuration
└── README.md
```

---

## License

This project is **UNLICENSED**.
