## Data model: `TransportQuoteRequest`

### Short description

The TransportQuoteRequest is a question to one or more transport actors to provide a quote to transport a certain amount of goods. It will be answered with a TransportQuote.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | Actor | the sender of the TransportQuoteRequest; both sellers and purchasers can ask for transportation options |
| receiver | TransportingActor | the receiver of the TransportQuoteRequest, which is always a TransportingActor |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| rfq | RequestForQuote | the RequestForQuote from the purchaser |
| cutoffTime | Time | the time before which the transport quote needs to be sent |

### Further explanation

