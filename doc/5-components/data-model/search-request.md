## Data model: `SearchRequest`

### Short description

The SearchRequest is a request to a SearchingActor to provide a list, based on some contraints, of actors who could provide a certain service or sell a certain product.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | Actor | the sender of the search request |
| receiver | SearchingActor | the receiver of the search request |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| maximumDistance | Length | the maximum distance around the 'sender' to search for suppliers |
| maximumNumber | int | the maximum number of answers to return |
| product | Product | the product we are interested in |

### Further explanation

