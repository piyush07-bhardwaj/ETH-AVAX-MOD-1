# ETH-AVAX-MOD-1

# Calculator Contract
[![Solidity](https://img.shields.io/badge/Solidity-0.8.18-blue)](https://soliditylang.org/)
[![Metacrafter](https://img.shields.io/badge/Metacrafter-Amazing-orange)](https://www.metacrafters.io/)

This Solidity contract implements a simple Calculator that provides two mathematical operations - division and modulus (remainder). The contract ensures that division by zero is not allowed and performs necessary checks to ensure correctness of the results.

# Library Contract

The `Library` contract represents a simple library system on the Ethereum blockchain. It allows users to buy books from the library by depositing Ether into their accounts. The contract is managed by an admin who can change the book's price, add new books to the library.

 ### Variables

- `admin` (address): The Ethereum address of the contract administrator who has special privileges, such as changing the book's price and adding books to the library.

- `bookPrice` (uint): The price of a single book in Ether. Users need to have sufficient balance to purchase a book.

- `bookQuantity` (uint): The current quantity of books available in the library.

- `userBalance` (mapping): A mapping that stores the balances of users. The keys of the mapping are Ethereum addresses, and the corresponding values are the respective balances in Ether.

- ### Modifiers

- `isAdmin`: A custom modifier that restricts access to functions only to the contract's administrator. It ensures that only the admin can execute certain functions, like changing the book's price and adding new books.

- `hasMoney`: A custom modifier that checks whether a user has sufficient balance to buy a book. If the user's balance is less than the book's price, the transaction is reverted with an error message.

### Constructor

The contract constructor is executed only once during deployment and accepts two parameters: `_bookPrice` and `_bookQuantity`. These parameters set the initial book price and quantity in the library. The sender of the deployment transaction becomes the `admin` of the contract.

## Functions

### `divide(uint a, uint b)`
### `changePrice(uint newPrice)`

This function takes two unsigned integer values `a` and `b` as input parameters and returns the result of dividing `a` by `b`. It throws an error if `b` is zero, as division by zero is not allowed. The function employs the `require` statement to enforce this condition and uses the `assert` statement to ensure that the result is correct.
This function allows the contract admin to change the price of the book.

### `mod(uint a, uint b)`
### `addBook()`

This function takes two unsigned integer values `a` and `b` as input parameters and returns the modulus (remainder) of `a` divided by `b`. It throws an error if `b` is zero, as division by zero is not allowed. The function uses the `%` operator to calculate the modulus and asserts the correctness of the result using the `assert` and `revert`statements.
This function enables the contract admin to increase the quantity of books in the library by one.

## Usage
### `addMoney(address user, uint amount)`

This function allows users to add Ether to their account balance in the library.

To use this Calculator contract, you can follow these steps:
### `buyBook(address user)`

1. Open a Solidity development environment like Remix at https://remix.ethereum.org/.
Users can use this function to buy a book from the library. The function checks if the user has enough balance to afford the book before processing the transaction.

2. Create a new file and save it with a .sol extension (e.g., `Calculator.sol`).
## Usage

3. Copy and paste the provided contract code into the file.
To use the `Library` contract, follow these steps:

4. Ensure that the Solidity compiler version is set to `0.8.18` (or a compatible version).
1. Deploy the contract by providing the initial book price and quantity.

5. Compile the contract by clicking on the "Solidity Compiler" tab and then clicking "Compile Calculator.sol".
2. The deploying account becomes the contract's administrator.

6. Deploy the contract by navigating to the "Deploy & Run Transactions" tab, selecting the `Calculator` contract from the dropdown menu, and clicking "Deploy".
3. The admin can change the book price using the `changePrice` function.

7. Once the contract is deployed, you can interact with it by calling its functions.
4. The admin can add new books to the library using the `addBook` function.

### Example
5. Users can deposit Ether into their accounts using the `addMoney` function.

Assuming the contract is deployed, you can call the `divide` and `mod` functions to perform mathematical operations.
6. Users can buy a book by calling the `buyBook` function, which deducts the book price from the user's balance and decreases the book quantity.

### Author
 Piyush Bhardwaj
 www.linkedin.com/in/piyush-bhardwaj-384ba426b
