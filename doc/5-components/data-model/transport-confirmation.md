## Data model: `TransportConfirmation`

### Short description

The TransportConfirmation is the internal confirmation of the transport by the TransportingActor that triggers the sending of a TransportInvoice.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | TransportingActor | the sender of the TransportConfirmation |
| receiver | FinancingActor | the receiver of the TransportConfirmation, which is the FinancingActor of the transport firm |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| transportQuote | TransportQuote | the transport quote that dictates the mode of transport |
| shipment | Shipment | the shipment that needs to be transported |

### Further explanation

