## Data model: `TransportDelivery`

### Short description

The TransportDelivery is the confirmation from the transport actor to the ReceivingRole of the purchaser that the ordered goods have arrived.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | TransportingActor | the sender of the TransportDelivery, the transport firm |
| receiver | WarehousingActor | the receiver of the TransportDelivery, which is the warehouse of the purchaser |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| order | Order | the order that is fulfilled with delivering the shipment with the goods |
| shipment | Shipment | the goods that have been transported and are now delivered at the destination |

### Further explanation

