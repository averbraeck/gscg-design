## Data model: `SearchAnswer`

### Short description

The SearchAnswer is the answer from a Search actor to a SearchRequest. It contains a list of actors that might sell a product or service that was asked for in the SearchRequest.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | SearchingActor | the sender of the search answer |
| receiver | Actor | the receiver of the search answer |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| searchRequest | SearchRequest | the request that triggered this Search answer |
| actorList | List<Actor> | the suppliers of the requested product or service |

### Further explanation

