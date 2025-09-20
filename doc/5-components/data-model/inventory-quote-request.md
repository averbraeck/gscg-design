## Data model: `InventoryQuote`

### Short description

The InventoryQuoteRequest is a question to the warehouse to check whether there is inventory to fulfill the demand for a certain amount of product at a certain date. It will be answered with an InventoryQuote. Note that the warehouse can decide to look at buying this produt on the market, producing it on time, or just looking in the inventory.

 
### Content of the message:

| field      | type             | short explanation |
| -----      | ----             | ----------------- |
| sender     | SellingActor     | the SellingActor that sends the InventoryQuoteRequest  |
| receiver   | WarehousingActor | the WarehousingActor that receives the message |
| timestamp  | Time             | the absolute time when the message was created |
| uniqueId   | long             | the id used to group multiple messages, such as the demandId or the orderId |
| groupingId | long             | the id used to group all messages, relating back to the original order or demand |
| rfq        | RequestForQuote  | the RequestForQuote from the purchaser, containing information about product, amount and due date |
 
### Further explanation

An `InventoryQuoteRequest` will be answered with an an `InventoryQuote`.
