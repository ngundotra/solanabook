# Chapter 5

## Transactions and Instructions

Transactions are the user-facing interface for interacting with the blockchain. They are the smallest unit of work that can be executed on the blockchain. Transactions are executed in a single step, and are atomic, meaning that they either succeed or fail as a whole.

Instructions are the basic building blocks of Solana programs. These are instructions that are executed by the virtual machine, and are the smallest unit of work that can be performed on the blockchain.

Together, transactions and instructions form the basis of Solana's programmability.

### Transactions

Transactions are an atomic list of instructions that can be executed on the blockchain. Transactions are composed of instructions, and are the smallest unit of work that can be executed on the blockchain. Transactions are executed in a single step, and are atomic, meaning that they either succeed or fail as a whole.

Changes to the blockchain are only made through successful transactions. Transactions are executed by validators. Transaction execution is proposed by the leader node, and is voted on by the network. Transactions are grouped into "blocks" of transactions, which are voted on by the network.

Once a transaction's block achieves 8 votes, it is considered "confirmed" status.

Once a transaction's block achieves 32 votes, it is considered "finalized" status.

Finalized status means that the transaction is immutable, and has been committed to the blockchain's ledger. However, most applications consider "confirmed" status with same meaning as "finalized" because it is cheaper, and just has historically been as secure as "finalized". This is because there has never been a case where a transaction's block was confirmed, but later reverted. In other words, every block that has achieved 8 votes has been finalized.

Transactions are usually composed by applications and surfaced to users via browser extension wallets for the user's signature.

### Instructions

Instructions are the smallest unit of work that can be performed on the blockchain. They are the basic building blocks of Solana programs. Instructions are composed of a program ID, an unsized array of bytes, and an unsized array of Account Metas.
Account Metas are used to specify which accounts are being read from or written to by the instruction. Account Metas are a tuple of (pubkey, is_signer, is_writable).
Each account meta has a pubkey which refers to an account to load, `is_signer` which indicates if the account must be a signer, and `is_writable` which indicates if the account must be writable.

The program ID is the ID of the program that will be given execution authority over the accounts specified in the instruction, with only the instruction data as input.

Programs can arbitrarily define the semantics of their instructions, and can be used to implement arbitrary logic. This means that there is no universal instruction data format, as each program can define its own serialization and deserialization logic.

Basics of writing programs will be covered in Chapter 6.

However there are commonly accepted standards and patterns for interpreting the instruction data. We will touch on these existing standards for interpreting the instruction data in Chapter 11.
