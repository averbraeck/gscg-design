## Data model: `Fulfillment`

### Short description

The `Fulfillment` message indicates that product delivery for a demand has taken place. It is typically the last message in the entire process from ordering products till accepting the delivery of the products. The message is sent to the FinancingActor, to possibly indicate that the bill can be paid.

 
### Content of the message:

| field      | type             | short explanation |
| -----      | ----             | ----------------- |
| sender     | WarehousingActor | the sender of the Fulfillment; indicates that the shipment has arrived in the warehouse  |
| receiver   | FinancingActor   | the receiver of the message, e.g., to indicate payment can take place |
| timestamp  | Time             | the absolute time when the message was created |
| uniqueId   | long             | the unique id of the message |
| groupingId | long             | the id used to group all messages, relating back to the original order or demand |
| transportDelivery | TransportDelivery | pointer to the document of the receipt of the goods in the warehouse, when they were transferred from the TransportingActor to the WarehouseActor |


### Further explanation

Details about the Fulfillment (e.g., what product and amount) can be found in
- the order relating to the groupingId: what has originally been ordered?
- the `TransportDelivery`: what has actually been delivered?

When the product and amount are the same, and the order has been delivered within the time window that has been agreed in the order or order confirmation, the bill can be paid. When there are discrepancies, a fine may apply.
