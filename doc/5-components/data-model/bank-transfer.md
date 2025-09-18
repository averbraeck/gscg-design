## Data model: bank-transfer

### Short description

The bank-transfer is a request to the BankingActor to transfer money between the account of the sender and the account of a payee.


### Content of the message:

| field     | type           | short explanation |
| -----     | ----           | ----------------- |
| sender    | FinancingActor | the sender of the payment |
| receiver  | BankingActor   | the receiver of the payment |
| timestamp | Time           | the absolute time when the message was created |
| uniqueId  | long           | the unique id of the message |
| payee     | FinancingActor | the beneficiary of the bank transfer | 
| money     | Money          | the amount of money being transfered |


### Further explanation

Note that the payee is not the receiver of the message. The message it to the bank, to transfer the money between sender and payee.
