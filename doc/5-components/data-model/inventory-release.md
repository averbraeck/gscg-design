## Data model: `InventoryRelease`

### Short description

The InventoryRelease is the statement to finance that products are about to be sent to a purchaser, and that an invoice can be sent.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | WarehousingActor | the WarehousingActor that sends the message |
| receiver | FinancingActor | the FinancingActor that receives the message |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| inventoryReleaseRequest | InventoryReleaseRequest | the request to release goods from the inventory that was made earlier |

### Further explanation

