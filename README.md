0x36c2120b78c5dea0

* Table of Contents
  * [Chapter 1, Day 1](#chapter-1-day-1)
  * [Chapter 1, Day 2](#chapter-1-day-2)
  * [Chapter 2, Day 1](#chapter-2-day-1)
  * [Chapter 2, Day 2](#chapter-2-day-2)
  * [Chapter 2, Day 3](#chapter-2-day-3)
  * [Chapter 2, Day 4](#chapter-2-day-4)
  * [Chapter 3, Day 1](#chapter-3-day-1)

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

## Chapter 2, Day 3
<strong>1. In a script, initialize an array (that has length == 3) of your favourite people, represented as Strings, and log it.</strong>
> <img src="c2-d3-1.png" alt="Script executed" />

<strong>2. In a script, initialize a dictionary that maps the Strings Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a UInt64 that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0!</strong>
> <img src="c2-d3-2.png" alt="Script executed" />

<strong>3. Explain what the force unwrap operator ! does, with an example different from the one I showed you (you can just change the type).</strong>
> If a variable is an optional (i.e. the value can be whatever is assigned to it OR nil) and we want the actual type value out of it, cadence requires us to use the force-unwrap operator "!" to achieve this. When using the force-unwrap operator "!" and the optional value is nil, the result panics and execution is aborted.
> <img src="c2-d3-3.png" alt="Script executed" />

<strong>4a. What does the error message mean?</strong>
> When using dictionaries in cadence, elements in the dictionary are optionals by default, so the return type should be String? instead of String.

<strong>4b. Why we're getting this error?</strong>
> Because the script is trying to get the value out of the dictionary by key (which is an optional), the return type needs to be changed to String? or we need to use the force-unwrap operator.

<strong>4c. How to fix it?</strong>
> Add the force-unwrap operator to the return statement (return thing[0x03]!) or change the return type to String?.

## Chapter 2, Day 4
<strong>1,2,3. Deploy a new contract that has a Struct of your choosing inside of it (must be different than Profile). Create a dictionary or array that contains the Struct you defined. Create a function to add to that array/dictionary.</strong>
> <img src="c2-d4-1.png" alt="Contract deployed" />

<strong>4. Add a transaction to call that function in step 3.</strong>
> <img src="c2-d4-2.png" alt="Transaction executed" />

<strong>5. Add a script to read the Struct you defined.</strong>
> <img src="c2-d4-3.png" alt="Script executed" />

## Chapter 3, Day 1
<strong>1. In words, list 3 reasons why structs are different from resources.</strong>
> a. Structs can be copied or overwritten, resources cannot, they can be created exactly once, and must be moved or destroyed.
b. Structs can be created outside of a contract, resources can only be created in a contract.
c. Structs are containers of data, resources are very secure, well-kept containers of data that cannot be lost.

<strong>2. Describe a situation where a resource might be better to use than a struct.</strong>
> Since cadence makes losing a resource extremely difficult, resources are ideal for NFTs (whether super expensive or not) because unless you explicitly tell it to destroy, you can be very, very sure the NFT won't be lost and handled the way you as the developer intend it to.

<strong>3. What is the keyword to make a new resource?</strong>
> create

<strong>4. Can a resource be created in a script or transaction (assuming there isn't a public function to create one)?</strong>
> No, a resource can only be created in a contract.

<strong>5. What is the type of the resource below?</strong>
> @Jacob

<strong>6. I Spy 4 things wrong with this code. Please fix them.</strong>
> <img src="c3-d1-1.png" alt="Contract" />
