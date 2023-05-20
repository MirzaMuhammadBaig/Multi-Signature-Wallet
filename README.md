# Multi-Signature-Wallet

The MultiSig contract is a Solidity smart contract that implements a multi-signature wallet functionality. It allows multiple owners to jointly control the funds held in the contract, requiring a specified number of confirmations from the owners to execute a transaction.

### The contract has the following main components:

- **Owners**: An array of addresses representing the owners of the multi-signature wallet. The contract requires at least two owners.

- **numConfirmationsRequired**: An integer indicating the number of confirmations required from the owners to execute a transaction.

- **Transaction struct**: A structure defining the details of a transaction, including the recipient address, the value to be transferred, and flags to indicate whether the transaction has been executed or rejected.

- **Mappings**: Several mappings are used to keep track of transaction confirmations, owners of transactions, transaction amounts, and rejection status of transactions.

- **Transactions array**: An array that stores the submitted transactions.

### The contract provides the following functions:

- **constructor**: Initializes the contract by setting the owners and the required number of confirmations.

- **isOwner**: Checks if an address is one of the owners of the contract.

- **submitTransaction**: Allows an owner to submit a transaction by providing the recipient's address and the amount to be transferred. The transaction is added to the transactions array.

- **confirmTransaction**: Allows an owner to confirm a transaction by providing the transaction ID. Only owners can call this function. Once the required number of confirmations is reached, the transaction can be executed.

- **executeTransaction**: Executes a confirmed transaction by transferring the specified amount to the recipient's address.

- **isTransactionConfirmed**: Checks if a transaction has received the required number of confirmations from the owners.

- **RejectTransaction**: Allows the owner who submitted the transaction to reject it before it is executed. The transaction amount is refunded to the owner, and the transaction is marked as rejected.

The contract also emits events to provide information about transaction submissions, confirmations, and executions.
