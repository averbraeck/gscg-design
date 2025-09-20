## Data model: `TransportOrder`

### Short description

The TransportOrder is the request from the ShippingRole to the transport actor to pickup the goods for transport.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | WarehousingActor | the sender of the TransportOrder, which is the Shipping department (role) of the SellingActor |
| receiver | TransportingActor | the receiver of the TransportOrder, which is the TransportingActor |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| transportQuote | TransportQuote | the transport quote that dictates the mode of transport |
| shipment | Shipment | the shipment that needs to be transported |
| order | Order | the order to which the transport belongs |

### Further explanation

