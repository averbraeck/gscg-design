## Data model: `InventoryReservationRequest`

### Short description

The InventoryReservationRequest is a question to the warehouse to definitively reserve the inventory to fulfill the demand for a certain amount of product at a certain date. It will be answered with an InventoryReservation.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | SellingActor | the sender of the InventoryReservationRequest |
| receiver | WarehousingActor | the receiver of the InventoryReservationRequest |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| order | Order | the Order from the purchaser, which contains the product, amount and due date |

### Further explanation

