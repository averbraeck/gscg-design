## Data model: `OrderConfirmation`

### Short description

The OrderConfirmation is the response when an Actor sends in an Order to another actor. The conformation can be positive or negative, and when it is negative, it contains a reason for not being able to satisfy the Order.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | SellingActor | the sender of the order confirmation |
| receiver | PurchasingActor | the receiver of the order confirmation |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| order | Order | the order for which this was the confirmation |
| confirmed | boolean | indicating whether the order was accepted or not |

### Further explanation

