## Data model: `InventoryReleaseRequest`

### Short description

The InventoryReleaseRequest is the order fro the SellingActor to the warehouse to release the inventory that was reserved using an InventoryReservation.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | SellingActor | the SellingActor as the sender of the InventoryReleaseRequest |
| receiver | WarehousingActor | the WarehousingActor as the receiver of the message |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| inventoryReservation | InventoryReservation | the inventory reservation that was made earlier |

### Further explanation

