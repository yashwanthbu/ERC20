# ERC20 Token Standard(Hardhat)

This project is a starting point for beginners in understanding the creation of a token called 'yashwanth' using ERC20 Token Standard contract.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. In this contract we have created a token with symbol 'YBU' which can perform multiple functions like mint(only by owner), burn, transfer, approve, checking balance,etc. We have used openzeppelin to import all the library functions which makes it easier.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., ERC20.sol). Copy and paste the following code into the file:

```javascript
pragma solidity ^0.8.9;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract Yashwanth is ERC20, ERC20Burnable, Ownable {
    constructor() ERC20("Yashwanth", "YBU") {
        _mint(msg.sender, 1000 * 10 ** decimals());
    }

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.9" (or another compatible version), and then click on the "Compile ERC20.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "ERC20" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with the respective functions that you want to perform.

This contract is then deployed to the hardhat network, we have used the previous project setup(module 2 project) to deploy this contract to the hardhat network by running :

```shell
npx hardhat run scripts/deploy.js
```



## Authors

Yashwanth BU
[@yashwanthbuu@gmail.com]


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
