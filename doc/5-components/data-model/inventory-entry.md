## Data model: `InventoryEntry`

### Short description

The `InventoryEntry` message is the trigger to the warehouse to store the goods from a shipment.

 
### Content of the message:

| field      | type             | short explanation |
| -----      | ----             | ----------------- |
| sender     | WarehousingActor | the sender of the InventoryEntry; indicates that the shipment has arrived in the warehouse  |
| receiver   | FinancingActor   | the receiver of the message, e.g., to indicate payment can take place |
| timestamp  | Time             | the absolute time when the message was created |
| uniqueId   | long             | the id used to group multiple messages, such as the demandId or the orderId |
| groupingId | long             | the id used to group all messages, relating back to the original order or demand |
| order      | Order            | the order for which this is the set of delivered goods |
| shipment   | Shipment         | the set of delivered goods |
 
### Further explanation

The order is included to see for which order this is the delivery. Especially in an MRP system, it is important for the bookkeeping to know to which order the delivery is related. The shipment contains the products. This could be the agreed products and amount (typically that is the case), but it can also be a replacement product or a different amount (in case of a problem). 
