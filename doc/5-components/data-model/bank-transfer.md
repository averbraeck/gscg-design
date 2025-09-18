## Data model: bank-transfer

Content of the message:

| field     | type           | short explanation |
| -----     | ----           | ----------------- |
| sender    | FinancingActor | the sender of the payment |
| receiver  | BankingActor   | the receiver of the payment |
| timestamp | Time           | the absolute time when the message was created |
| uniqueId  | long           | the unique id of the message |
| payee     | FinancingActor | the beneficiary of the bank transfer | 
| money     | Money          | the amount of money being transfered |

