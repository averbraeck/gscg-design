## Data model: `ShippingOrder`

### Short description

The ShippingOrder is the request from the WarehousingRole to the ShippingRole to ready the goods from the warehouse for transport. Both the WarehousingRole and the ShippingRole are typically part of the WarehousingActor.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | WarehousingActor | the WarehousingActor as the sender of the ShippingOrder |
| receiver | WarehousingActor | the receiver of the ShippingOrder, which is the ShippingRole of the WarehousingActor |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| inventoryRelease | InventoryRelease | the inventory release on which the shipment will be based |

### Further explanation

