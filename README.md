# Project Title - Joint Savings

## Introduction
The primary goal of our team is to build a Solidity smart contract for joint savings accounts.  As an Ethereum blockchain developer of a fintech startup company, our team will be tasked with creating a smart contract that will enable users to provide addresses for the joint savings accounts and provide functions for deposits, withdrawals and checking balances.   

## Technologies
`Remix IDE`


## Installation Guide

[Install Anaconda](https://www.anaconda.com/download/)

[Install Git](https://git-scm.com/downloads) 


To clone and run this application, you'll need Git installed on your computer.
From your command line:
```
# Create a new conda environment
conda create -n whatever_your_name python=3.7 anaconda

# Activate the new environment with the following command
conda activate whatever_your_name

# Iniitlaize git (skip if git is installed)
git init

# Browse to your directory and clone the repository below on your local machine
git clone https://github.com/AlexanderValenzuela/joint_savings

# In the conda environment, launch Remix IDE and then browse to your directory
https://remix.ethereum.org/


```

## Usage
Step 1: Create a Joint Savings Account Contract in Solidity

1. Open the Solidity file named `joint_savings.sol` in the Remix IDE.

2. Define a new contract named `JointSavings`.

3. Define the following variables in the new contract:

* Two variables of type `address payable` named `accountOne` and `accountTwo`
* A variable of type `address public` named `lastToWithdraw`
* Two variables of type `uint public` named `lastWithdrawAmount` and `contractBalance`

4. Define a function named `withdraw` that accepts two arguments: `amount` of type `uint` and `recipient` of type `payable address`. In this function, code the following:

* Define a `require` statement that checks if `recipient` is equal to either `accountOne` or `accountTwo`. If it isn’t, the require statement returns the “You don't own this account!” text.
* Define a `require` statement that checks if `balance` is sufficient for accomplishing the withdrawal operation. If there are insufficient funds, it returns the “Insufficient funds!” text.
* Add an `if` statement to check if `lastToWithdraw` is not equal `(!=)` to `recipient`. If it’s not equal, set it to the current value of `recipient`.
* Call the `transfer` function of the `recipient`, and pass it the `amount` to transfer as an argument.
* Set lastWithdrawAmount equal to amount.
* Set the `contractBalance` variable equal to the balance of the contract by using `address(this).balance` to reflect the new balance of the contract.

5. Define a `public payable` function named `deposit`. In this function, code the following:

* Set the contractBalance variable equal to the balance of the contract by using `address(this).balance`.

6. Define a `public` function named `setAccounts` that takes two `address payable` arguments, named `account1` and `account2`. In the body of the function, set the values of `accountOne` and `accountTwo` to `account1` and `account2`, respectively.

7. Add a fallback function so that your contract can store ether that’s sent from outside the deposit function.


Step 2: Compile and Deploy Your Contract in the JavaScript VM<br>
* Compile your smart contract. If an error occurs, review your code, and make the necessary changes for a successful compilation.
* In the Remix IDE, navigate to the “Deploy & Run Transactions” pane, and then make sure that “JavaScript VM” is selected as the environment.
* Click the Deploy button to deploy your smart contract, and then confirm that it successfully deployed.

Step 3: Interact with Your Deployed Smart Contract<br>
Now that your contract is deployed, it’s time to test its functionality! 
To interact with your deployed smart contract, complete the following steps:
1. Use the `setAccounts` function to define the authorized Ethereum address that will be able to withdraw funds from your contract.<br>
You can either use the following Ethereum addresses or create new, dummy addresses on the [Vanity-ETHLinks](https://vanity-eth.tk/) to an external site. website, which includes an Ethereum vanity address generator.

```
Dummy account1 address: 0x0c0669Cd5e60a6F4b8ce437E4a4A007093D368Cb
Dummy account2 address: 0x7A1f3dFAa0a4a19844B606CD6e91d693083B12c0
```
3. Test the deposit functionality of your smart contract by sending the following amounts of ether. After each transaction, use the `contractBalance` function to verify that the funds were added to your contract:

    - Transaction 1: Send 1 ether as wei.
    - Transaction 2: Send 10 ether as wei.
    - Transaction 3: Send 5 ether.

4. Once you’ve successfully deposited funds into your contract, test the contract’s withdrawal functionality by withdrawing 5 ether into `accountOne` and 10 ether into `accountTwo`. After each transaction, use the `contractBalance` function to verify that the funds were withdrawn from your contract. Also, use the `lastToWithdraw` and `lastWithdrawAmount` functions to verify that the address and amount were correct.

## Contributors
- Firas Obeid, UC Berkeley FinTech Instructor
[GitHub](<https://github.com/firobeid>)

- Hasan Mehommod, Central Tutor Support

- Alexander Valenzuela<br>
[LinkedIn Profile](<https://www.linkedin.com/in/alex-valenzuela-97826842/>)


## License
Licensed under the MIT License

