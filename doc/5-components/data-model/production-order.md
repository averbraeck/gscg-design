## Data model: `ProductionOrder`

### Short description

A ProductionOrder indicates: I want to produce a certain amount of products on a certain date. The attributes "product", "amount", and "date" make up the production order.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | Actor | the sender of the production order |
| receiver | Actor | the receiver of the production order |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| demand | Demand | the demand that triggers this production order |
| product | Product | the ordered product |
| amount | double | the amount of the product, in units for that product |
| dateReady | Time | the intended date when the products should be ready |

### Further explanation

