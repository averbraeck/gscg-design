## Data model: `QuoteNo`

### Short description

A Quote is an answer to a RequestForQuote (or RFQ) and indicates how many items of a certain product could be sold for a certain price at a certain date. The QuoteNo indicates that the requested product is not available. Note that the default option is not to send a negative response, but no response at all.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | SellingActor | the sender of the information that the SellingActor does not quote on the RFQ |
| receiver | PurchasingActor | the receiver of the information that the SellingActor does not quote on the RFQ |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| rfq | RequestForQuote | the RFQ for which this is the quote denial |

### Further explanation

