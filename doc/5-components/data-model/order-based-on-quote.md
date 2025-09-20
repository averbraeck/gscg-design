## Data model: `OrderBasedOnQuote`

### Short description

This implementation of an Order contains a link to a Quote on which the order is based. The Order contains a link to the Quote on which it was based.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | PurchasingActor | the sender of the quote-based order, a PurchasingActor |
| receiver | SellingActor | the receiver of the quote-based order, a SellingActor |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| quote | Quote | the quote on which the order is based |
| deliveryDate | Time | the delivery date as ordered |

### Further explanation

