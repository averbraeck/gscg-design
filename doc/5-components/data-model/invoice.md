## Data model: `Invoice`

### Short description

The invoice represents a document that asks for payment for a product or service. It contains a pointer to an Order to see for which exact order the actor is invoiced.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | FinancingActor | the sender of the invoice, always the FinancingActor of the sending organization |
| receiver | FinancingActor | the receiver of the invoice, always the FinancingActor of the receiving organization |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| order | Order | the order to which this invoice belongs |
| finalPaymentDate | Time | the simulation time for final payment |

### Further explanation

