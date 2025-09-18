## Data model: `Demand`

### Short description

The `Demand` message represents content for an demand of a supply chain actor. The demand triggers purchasing or manufacturing of products, and is usually the first in a long chain of messages that are exchanged between actors.

 
### Content of the message:

| field      | type           | short explanation |
| -----      | ----           | ----------------- |
| sender     | Actor          | the sender of the `Demand`. It is not specified further, since it can be, e.g., a ConsumingActor or WarehousingActor that sends the request |
| receiver   | Actor          | the receiver of the `Demand` (same actor). This is also not specified since the sender is not specified. Yet, it will be typically handled by the PurchasingActor role |
| timestamp  | Time           | the absolute time when the message was created |
| uniqueId   | long           | the unique id of the message |
| groupingId | long           | the id used to group multiple messages, such as the demandId or the orderId |
| product    | Product        | the product which is demanded |
| amount     | double         | the amount of the product expressed in the product's SKU |
| earliestDeliveryDate | Time | the earliest delivery date |
| latestDeliveryDate   | Time | the latest delivery date |


### Further explanation

This request is produced as the result of an internal demand process. The process is often modeled by the following parameters:

- Product to buy
- Minimal quality to buy
- Quantity to buy at a time
- Interval between orders

The quantity to buy and the interval between orders could be drawn from a statistical distribution (random generator). There could be multiple demand generators in place for multiple products and/or qualities and/or quantities. 
