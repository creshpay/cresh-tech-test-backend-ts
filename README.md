<p style="text-align: center; margin: 40px auto;"><img src="images/logo.png" width="150px" /></p>

# Cresh Backend Engineering Technical Tests - Typescript Flavor

🧩 This is a little challenge to help us assess your skills as a backend typescript developer.

🎯 At Cresh we aim to have a clean, modular, resilient code, fully tested and embrassing the clean code way and we expect no less from you.

🧐 A particular attention will be taken on your code structure, your ability to implement the data model and organize the whole project.

## 🛍️ Context

At Cresh we provide credit at shopping cart, instantly.
Our mission is to ease the way consumers can get the products they want from any shop, both online and in store.

To do so, we provide several apps, both B2B and B2C along with some APIs.

## 📜 Instructions

We would like you to reproduce some (very simplified) functionalities related to our business model.

To realize this test you can use the node.js framework you are the most confortable with, but bear in mind we use express.

You will also need to choose a database to handle your data. We would prefer you to use a RDBMS for this test, but if you are more confortable with a NoSQL one, that's fine too.

The exercise is to implement a few APIs endpoints to handle customers transactions.

### 📚 API Documentation

Several endpoints are needed, handling multiples routes:

#### `status` endpoint

- A simple route usable for healthcheck purposes (both for the APIs and the database)

#### `customers` endpoint

- List of all the customers (bonus if you add a pagination mechanism)
- Creation of a new customer
- List of all the transactions related to a given customer

#### `transactions` endpoint

- Create a transaction
- List of all the instalments related to a given transaction
- Trigger a payment of a specific transaction's instalment

### 🔷 Entities

> ⚠️ Note: Not all the fields are provided. You will need to add relevant relational model fields (if needed) and anything else useful you could think of.

#### 👤 Customer

Field | Type | Description
-|-|-
`firstname` | `string` | Self-explanatory
`lastname` | `string` | Self-explanatory
`birthdate` | `Date` | Self-explanatory

#### 💳 Transaction

Field | Type | Description
-|-|-
`store_name` | `string` | Name of the store where the transaction was made
`amount` | `number` | Transaction full amount
`split` | `3` \| `4` | Number of instalments for the transaction
`is_online` | `boolean` | Flag if the transaction was made online or in-store
`is_completed` | `boolean` | Flag when all instalments has been paid off

#### 💵 Instalment

Field | Type | Description
-|-|-
`amount` | `number` | Instalment amount
`is_paid` | `boolean` | Flag when the instalment has been paid off
`planned_date` | `Date` | Planned date of payment
`paid_date` | `Date` | Actual payment date


A few key points :

- A customer can have several transactions ;
- A transaction must have as many instalments as its `split` attribute ;
- When a transaction is created, all its instalments are also generated based on the current date and the `split` attribute. Only the first payment is paid immediately, the transaction as a whole is not done yet ;
- When calculating each instalment amount, if you can't have an exact split value, the remainder is added to the first one ;
- When all instalments of a transaction have been paid off, its `is_completed` flag must be switched to `true`.


## 📋 What's evaluated

- Cleanliness & structure of the code
- Code modularity / extensibility
- Typing, especially the data model
- Documentation
- Respect of some basic principles, like  SOLID, KISS and DRY
- TDD approach
- unicity of git commits

## 📦 Deliverable

Please **clone** (not fork) this repository and send us a zip or a link to your repo.

We expect :

- A clean files structure
- Some commands to run from the `package.json`
- A documentation on how to install, start and use this API



🚀 **Good luck and have fun !** 🚀
