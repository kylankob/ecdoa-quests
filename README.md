0x36c2120b78c5dea0

## Chapter 1, Day 1
<strong>1. Explain what the Blockchain is in your own words.</strong>
> A publicly accessible, decentralized and open network of computers that collectively store an ever increasing "list" of data records or blocks. Each new block of data is "connected" to a previous block using cryptography, with each new one added reinforcing the security to past and future blocks as the chain of blocks (blockchain) continues to grow. 

<strong>2. Explain what a Smart Contract is.</strong>
> A sort of "computer program" that defines rules and very specific functions on how any user can interact with a blockchain. If a user would like to store some piece of data in a block on a blockchain, a programmer would need to write a smart contract to accomplish this specific task.

<strong>3. Explain the difference between a script and a transaction.</strong>
> Both are snippets of code (computer program) that can interact with a smart contract that has been deployed to a blockchain. Scripts are public and don't cost any money, generally they are used to read data from the blockchain. Transactions mutate (change) something on the blockchain and are subject to a gas (transaction) cost and a user signing the transactions (i.e. the one responsible for perfomring the mutation).

## Chapter 1, Day 2
<strong>1. What are the 5 Cadence Programming Language Pillars?</strong>
> 1. Safety and Security
> 2. Clarity
> 3. Approachability
> 4. Developer Experience (DX)
> 5. Resource Oriented Programming 

<strong>2. In your opinion, even without knowing anything about the Blockchain or coding, why could the 5 Pillars be useful (you don't have to answer this for #5)?</strong>
> 1. Safety and Security - making things more difficult to actually "mess up" and avoid inherently potential catastrophes when writing smart contracts is great asset to have in a programming language.

> 2. Clarity - making the language "clearer" by design, certainly will be a helpful asset (especially to newcomers) when working with the language in the wild for the first time.

> 3. Approachability - designing the language in such a way that can seem somewhat familiar to other langauges will certainly benefit those coming from other programming backgrounds.

> 4. DX - at the end of the day, the developer role has the responsibility of creating the methods and means of what exactly users can interact with (bascially be able to actually "do" things on the blockchain). The language designers consideration of improvements to the developer environment will absolutely help the developer be as efficient as possible and ultimately produce a better product. 

## Chapter 2, Day 1
<strong>1. Deploy a contract to account 0x03 called "JacobTucker". Inside that contract, declare a constant variable named is, and make it have type String. Initialize it to "the best" when your contract gets deployed.</strong>
> <img src="c2-d1-1.png" alt="Deployed contract" />

<strong>2. Check that your variable is actually equals "the best" by executing a script to read that variable.</strong>
> <img src="c2-d1-2.png" alt="Executed script" />

## Chapter 2, Day 2
<strong>1. Explain why we wouldn't call changeGreeting in a script.</strong>
> The function changeGreeting is changing (mutating) a state variable in the smart contract on the blockchain, which requires a user as a signer and a fee (gas), so in cadence, that is done in a transaction not a script.

<strong>2. What does the AuthAccount mean in the prepare phase of the transaction?</strong>
> Allows access to the user's flow account as the signer that is responsible for sending the transaction.

<strong>3. What is the difference between the prepare phase and the execute phase in the transaction?</strong>
> The execute phase of a transaction doesn't have access to the user account, which is needed when sending a transaction. While calling a function in the prepare phase would work the same as calling it in the execute phase, the separation of logic between the 2 phases creates better code organization and readability.

<strong>4a. Add a variable named myNumber that has type Int (set it to 0 when the contract is deployed) and a function named updateMyNumber that takes in a new number named newNumber as a parameter that has type Int and updates myNumber to be newNumber.</strong>
> <img src="c2-d2-1.png" alt="Deployed contract" />

<strong>4b. Add a script that reads myNumber from the contract.</strong>
> <img src="c2-d2-2.png" alt="Script" />

<strong>4c. Add a transaction that takes in a parameter named myNewNumber and passes it into the updateMyNumber function.</strong>
> <img src="c2-d2-3.png" alt="Transaction" />

<strong>4d. Verify that your number changed by running the script again.</strong>
> <img src="c2-d2-4.png" alt="Executed script" />

