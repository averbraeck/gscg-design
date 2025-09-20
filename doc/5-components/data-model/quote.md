## Data model: `Quote`

### Short description

A Quote is an answer to a RequestForQuote (or RFQ) and indicates how many items of a certain product could be sold for a certain price at a certain date. The Quote might have a limited validity.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | SellingActor | the sender of the quote |
| receiver | PurchasingActor | the receiver of the quote |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| rfq | RequestForQuote | the RFQ for which this is the quote |
| price | Money | the quotation price, including transport costs and a profit margin |
| proposedDeliveryDate | Time | the intended delivery date of the products |
| transportQuote | TransportQuote | the transport quote offered |
| validityTime | Time | the time on the simulator clock until which the quote is valid |

### Further explanation

