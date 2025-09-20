## Data model: `Payment`

### Short description

The Payment follows on a Invoice, and it contains a pointer to the Invoice for which it is the payment.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | FinancingActor | the sender of the payment, always a FinancingActor |
| receiver | FinancingActor | the receiver of the payment, always a FinancingActor |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| invoice | Invoice | the invoice to which this payment belongs |

### Further explanation

