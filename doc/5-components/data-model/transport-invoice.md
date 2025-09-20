## Data model: `TransportInvoice`

### Short description

The transport invoice represents a document that asks for payment for transport. It contains a pointer to TransportQuote to see for which exact service the actor is invoiced.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | FinancingActor | the sender of the invoice, which is the FinancingRole of the TransportingActor |
| receiver | FinancingActor | the receiver of the invoice, which is the FinancingRole of the SellingActor |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| transportQuote | TransportQuote | the order to which this invoice belongs |
| shipment | Shipment | a pointer to the shipment to check that it arrived before payment |
| finalPaymentDate | Time | the simulation time for final payment |

### Further explanation

