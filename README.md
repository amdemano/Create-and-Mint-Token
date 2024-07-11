# MyToken ERC20 Smart Contract

A simple ERC20 token implementation using Solidity and OpenZeppelin libraries.

## Description

This project implements an ERC20 token named `MyToken` (symbol: `MTK`). It includes functionalities for minting, burning, and transferring tokens. The contract leverages OpenZeppelin libraries to ensure security and standardization. 

## Getting Started

### Installing

To get started with the MyToken contract:

1. **Open Remix IDE**:

    Go to [Remix IDE](https://remix.ethereum.org/).

2. **Create a new file**:

    Create a new file named `MyToken.sol` in Remix.

3. **Copy the contract code**:

    Copy and paste the following code into `MyToken.sol`:

    ```solidity
    // SPDX-License-Identifier: MIT
    pragma solidity ^0.8.0;

    import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
    import "@openzeppelin/contracts/access/Ownable.sol";

    contract MyToken is ERC20 {
        constructor(uint256 initialSupply) ERC20("MyToken", "MTK") {
            _mint(msg.sender, initialSupply * 10**decimals());
        }

        function mint(address to, uint256 amount) public onlyOwner {
            _mint(to, amount);
        }
        
        function burn(uint256 amount) public {
            _burn(msg.sender, amount);
        }

        function transfer(address recipient, uint256 amount) public override returns (bool) {
            _transfer(msg.sender, recipient, amount);
            return true;
        }
    }
    ```

### Executing program

To deploy and interact with the MyToken contract in Remix:

1. **Compile the contract**:

    - Go to the "Solidity Compiler" tab in Remix.
    - Select the appropriate compiler version (`0.8.0` or higher).
    - Click "Compile MyToken.sol".

2. **Deploy the contract**:

    - Go to the "Deploy & Run Transactions" tab.
    - Select "Injected Web3" or "Remix VM" as the environment.
    - Ensure the contract `MyToken` is selected.
    - Provide the initial supply value (e.g., `1000`).
    - Click "Deploy".

3. **Interact with the deployed contract**:

    - Once deployed, you can interact with the contract using the provided functions.
    - Use the `mint` function to mint new tokens.
    - Use the `burn` function to burn tokens.
    - Use the `transfer` function to transfer tokens to another address.


## Help

For common issues or troubleshooting:

* Ensure you have the correct Solidity version installed.
* Check your network configuration in Hardhat.
* For any issues with OpenZeppelin, refer to their [documentation](https://docs.openzeppelin.com/).

```bash
npx hardhat help
```

## Authors
Ashley Demano

## License
This project is licensed under the MIT License - see the LICENSE.md file for details.
