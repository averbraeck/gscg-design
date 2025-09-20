## Data model: `TransportQuote`

### Short description

The TransportQuote is the answer to a question to provide a quote to transport a certain amount of goods.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | TransportingActor | the transport firm as the sender of the TransportQuote |
| receiver | Actor | the receiver of the TransportQuote; both a buying actor and a receiving actor can reserve transport |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| transportQuoteRequest | TransportQuoteRequest | the InventoryQuoteRequest from the selling role |
| transportOption | TransportOption | a single transport option that matches the transport request best |
| price | Money | the price for this transport option |

### Further explanation

