## Data model: `TransportPayment`

### Short description

The TrasnportPayment follows on a TransportInvoice, and it contains a pointer to the TransportInvoice for which it is the payment. The TransportPayment leads to a BankTransfer.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | FinancingActor | the sender of the payment of the transport |
| receiver | FinancingActor | the receiver of the payment of the transport |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| invoice | TransportInvoice | the transport invoice to which this payment belongs |

### Further explanation

