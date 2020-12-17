---------------------------
Representing Transactions
---------------------------

In this lesson, we’ll build a small blockchain of your own in Python! This lesson assumes a familiarity with Python syntax, functions, loops, importing libraries, and constructing classes, but there are some hints along the way to help out. If you’ve never used Python before, you might want to learn some with Codecademy.

The blockchain is a new way of storing and moving data securely. The data mostly consists of transactions which include messages exchanged between two parties. Before we start creating our blockchain, let’s think of a way to store a transaction like the one shown below:

amount: 30
sender: Alice
receiver: Bob

In this example, Alice is trying to transfer 30 units of some currency to Bob. Can you think of a Python data type to best represent the above transaction?

This transaction is best represented in the form of a Python dictionary, with keys for the required fields and values specific to the transaction.

These transactions are all stored inside the mempool, a pool of transactions that miners reference when selecting the set of transactions they want to verify.

----------------
Creating Blocks
----------------

Now let’s think of a way to represent a block in Python. We could create a bigger dictionary and store our data inside this dictionary. But since blocks can be represented as objects, let’s create a Block Class which we can easily use to create new blocks.

Recall that a Block contains the following properties:

    Timestamp
    Transaction
    Hash
    Previous Hash
    Nonce

In this exercise, we will be creating the default constructor for the Block class in our Mini-Blockchain.

-------------------
Hashing and SHA-256
-------------------

Before we create a more dynamic blockchain, let’s learn how to use a hash function in Python. Specifically, we will be using the SHA-256 hash function which can be easily imported in Python.

We will use the SHA-256 as a regular function that takes in a random string as its argument. To properly use this function in Python 3, our string must be encoded before being passed as an argument. To encode the string, we use the .encode() method.

-----------------------
Generating Block Hashes
-----------------------

Block hashes are used to uniquely identify and maintain the integrity of each block. The SHA-256 algorithm is used to generate the hash of the block using the timestamp, data, and previous hash — the three properties of our Block class!

Let’s create the .generate_hash() method for the Block class.

-----------------------------
Creating the Blockchain Class
-----------------------------

Each computer participant has their own copy of the blockchain. Ideally, each copy of the blockchain should have the same properties and functionality to add and validate blocks.

We can represent the blockchain as an object. We are using objects for our implementation, because they offer the flexibility to create specific attributes and methods. Representing it as an object also allows us to create blockchain instances for each computer participant.

To review, our blockchain contains the following:

    Chain: A list that that holds all the blocks inside the blockchain.
    Unverified Transactions: A list that represents all the unverified transactions before being passed into a block.
    Genesis Block: A block automatically generated when the blockchain is initialized. (I mean first block in the chain)

