## Data model: `InventoryReservation`

### Short description

The InventoryReservation is the answer to a question to the warehouse to definitively reserve the inventory to fulfill the demand for a certain amount of product at a certain date.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | WarehousingActor | the Warehouse as the sender of the InventoryReservation |
| receiver | SellingActor | the SellingActor who receives the confirmation of the InventoryReservation |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| inventoryReservationRequest | InventoryReservationRequest | the InventoryReservationRequest from the selling role |
| reserved | boolean | if false, the product cannot be released (anymore) at the requested date |

### Further explanation

