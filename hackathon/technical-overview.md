# Why Antelope
Antelope is amazing because it is fast, it scales, and it has the functionality you need to develop distributed applications. Antelope is a proven technology with over 4 years of continuous uptime.

As a blockchain, Antelope is a distributed ledger, and smart contracts. It also supports tables, which allows create-update-and-delete of records. Tables also support multiple indexes so you can look up data fast. One note, smart contracts can not reach outside of the blockchain, and you can’t make a call to an external service.

Antelope support accounts with multiple permissions. This allows for fine grained access control and enables your application to lock and unlock sets of features, levels of play, events, or anything else.  

## What does this mean for me?
### Scale and Speed
Let's put some numbers around speed and scale. Blocks are often finalized in 0.5 secs. This isn’t a guarantee because finalization time can vary; however it gives you a sense for what types of interactions may be supported by Antelope. In my opinion, this makes it possible to have user interaction read and write directly to the blockchain.

Scale is also pretty good. Antelope can support thousands of transactions per second. Test networks have run up to 17,000 transactions per second. This is not a guarantee. It does give you a sense for how big you can scale, and how wide you can go. In my opinion, this scale makes it possible to handle Internet of Things (IoT) scenarios with lots of devices interacting with Antelope.

### Smart Contracts
Rich set of commands to build up contracts, tokens, ledgers and execute a defined set of logic. Smart Contracts can do many things, in fact one of the few things Smart Contract can not do is reach outside the blockchain or send data outside the blockchain.
### Cross Cutting Power of Permissions
One of the neat things about Antelope is the permission structure. New permissions can be created and granted to accounts. As an application developer this can be turned into a cross cutting function to unlock account features. You don’t need to code everything all your logic into smart contracts, instead consider using permission as the basis for allowing actions. You can update or remove permissions on accounts instead of changing your smart contracts.

Take the following as an example.

**Unlock new level3 in a game, for gamers who beat level2** Once the gamer beats level two, call a smart contract to grant level3 permissions. Check for level3 permission when attempting to play level3. If you want to change the logic for level progression to include a speed-run element you can add that to the logic to the smart contract granting permissions. This logic change will only apply to new players, previous players will continue to keep their entitlements. This is nice because checking permissions is easy.

**Open up events to VIP members** Again opening up limited events to VIP members is a common scenario. You can write a smart contract to grant permissions to a particular event. If the event is open for a limited time you can go back and remove permissions. If you want to make exceptions to allow certain accounts, simply add permission to specific accounts.

**Change the moderator of a social network every week** Create a “moderator” permission every week, run a smart contract to move the permission to another account. The smart contract could work off of votes from other members.

### Persisting Data
Antelope has the ability to persist data in tables. This provides two powerful capabilities. First you can run a lookup on a table to get state. No need to sift through historical transactions. Second, you can update data, and change state. Let's walk through examples of each of these capabilities.

**User Profiles Stored with Antelope.** You can create a user table with all the relevant information, username, avatar icon, last login time. Antelope scales and updates quickly, and you can look up data using the login credentials.. That makes the Antelope table the only datastore you will need.

**Storing telemetry from IoT devices.**  With Antelope’s scale you can store data from lots of devices, and quickly lookup data by device id. Antelope supports multiple indexes so you lookup data by location as well.

**Track state of play.**  Use the tables to track moves by players, location of pieces, or player stats. As the game progresses, update the table to reflect the current state. Multiple indexes allow lookup by player, by board, or by event.

**Track multiple metrics for granting tokens.** You may want to track multiple metrics for granting tokens. For example you may want to grant a participation token based on multiple criteria. You could look at in-person participation, many hours of online participation, or for helping out during an event as the basis for granting a token. You can store all of this data in a table then run your custom algorithm to grant participation tokens.

**Suspend a license not a business.** Governmental bodies often have public licensing records, and businesses may have multiple licenses. For example a pest control company may have two licenses one for application of hazardous chemicals, and another for general pest control. Antelope will allow you to create a table containing the business, their license key, their license status, and their location. With a multi-index table you can do lookups by business, by license, or by location.  

## Recap
You can build on Antelope without additional infrastructure.
- Speed and scale eliminates need for intermediate caching layers
- Fine grained permissions make accounts useful and keeps things simple
- Multi Index tables bring the power of queries to your application
- Updates to tables eliminate the need to listen for events and store them in a separate DB

## Advanced Examples
### Lambda Architecture/ Data Warehousing
#### `Description`
Data Warehouses write a lot of data to be analyzed later. There may be one or two key metrics that are known in advance, and these metrics are used frequently for decision making. These frequently used metrics should be available in real time.  
#### `Example`
Web access logs. We need the number of active users, the number of clicks per session, and the number of errors per period of time. Anything else will require specific log analysis.
#### `Application Design`
Web logs would be sent to a smart contract. The smart contract would build a table indexed by time containing the values. You don’t need to write records to the blockchain. The transaction sent to call the contract would contain your weblog and would be written to the blockchain.  

The smart contract would collect the data and write new values every 1 minute. To save space, same ram and save $$
- Use an uint32 for the time, and store as seconds since start date
- Use the fewest number of bytes each for number of active users, number of clicks and number of errors
- You may want to reserve a byte in your table for the table schema version. This additional byte will enable your contract to add forward and backward compatibility logic when your schema changes.

Later processing an analysis of the logs may be done by looking through past blocks pulling out the transactions submitted to your smart contract.

### Order Books
#### `Description`
Order Books match producers and consumers, often by a criterial like price. Sometimes it takes multiple orders to fulfill a desired quantity.  
#### `Example`
Order Books are commonly found in financial transactions to match buyers and sellers. For example matching sellers and buyers by amount and price. A party wants to sell 1 unit for $100/unit. There is a buyer who will buy 0.2 units for $100/unit. That leaves a remaining 0.8 units unsold. A process can walk down an order book looking for the next buyer at $100/unit until the open quantity is zero.
#### `Application Design`
Antelope has ordered indexes, and multiple indexes. To support this scenario create a table consisting of
- Order Id
- Type (Buy or Sell)
- Quantity
- Price per Unit
Create an index on Price per Unit ordered by OrderId. When the price hits $100 select all the matching orders, and walk through them in sequential order by order id. This sequential order supports first in first out order flow.
