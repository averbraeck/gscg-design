## Data model: `InventoryQuote`

### Short description

The `InventoryQuote` message is the answer to a question to the warehouse to check whether there is inventory to fulfill the demand for a certain amount of product at a certain date. Note that the warehouse can decide to look at buying this product on the market, producing it on time, or just looking in the inventory.

 
### Content of the message:

| field      | type             | short explanation |
| -----      | ----             | ----------------- |
| sender     | WarehousingActor | the sender of the InventoryQuote  |
| receiver   | SellingActor     | the receiver of the InventoryQuote, as an answer to the InventoryQuoteRequest |
| timestamp  | Time             | the absolute time when the message was created |
| uniqueId   | long             | the id used to group multiple messages, such as the demandId or the orderId |
| groupingId | long             | the id used to group all messages, relating back to the original order or demand |
| inventoryQuoteRequest | InventoryQuoteRequest | the InventoryQuoteRequest from the selling role
| possible              | boolean               | if false, the product cannot be released in time
| priceWithoutProfit    | Money                 | the price of the goods without a profit margin, or null if possible is false
| earliestReleaseDate   | Time                  | the earliest date that the products can be released, or null if possible is false 
 
### Further explanation

An `InventoryQuoteRequest` is the answer to an `InventoryQuote`.
