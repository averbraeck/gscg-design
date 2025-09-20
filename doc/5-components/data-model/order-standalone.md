## Data model: `OrderStandalone`

### Short description

This is a stand alone order, that is not based on an RFQ and Quote, but which is directly placed to another actor. It might be based on a Quote, but the order is not explicitly saying so. It can also be an order to a well-known supply chain partner, with whom long-term price arrangements have been made.


### Content of the message:


| field | type | short explanation |
| ----- | ---- | ----------------- |
| sender | PurchasingActor | the sender of the standalone order |
| receiver | SellingActor | the receiver of the standalone order |
| timestamp | Time | the absolute time when the message was created |
| uniqueId | long | the unique id of the message |
| groupingId | long | the id used to group multiple messages, such as the demandId or the orderId |
| deliveryDate | Time | the intended delivery date of the products |
| product | Product | the ordered product |
| amount | double | the amount of the product, in units for that product |
| price | Money | the price we want to pay for the product |
| transportQuote | TransportQuote | the transport quote that the PURCHASER has obtained (the purchaser also pays the transporter) |

### Further explanation

