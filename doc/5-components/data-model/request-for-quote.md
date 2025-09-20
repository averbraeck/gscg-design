## Data model: `RequestForQuote`

### Short description

The RequestForQuote is a question to provide the receiver with a certain amount of a certain product at a certain date. It will be answered with a Quote.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | PurchasingActor | the PurchasingActor as the sender of the RFQ |
| receiver | SellingActor | the SellingActor as the receiver of the RFQ |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| demand | Demand | demand that triggered the process |
| transportPreference | TransportPreference | the preferred transport option for moving the product from sender to receiver |
| cutoffDate | Time | after what point in time will the RFQ stop collecting quotes? |

### Further explanation

