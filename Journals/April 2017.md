## Month #2
### Week #13
- - -
#### Monday April 10, 2017
* **Goals**:
* **Accomplishments**:
* **Feedback**:
	1. Writing better documentation for github PRs. More to the point and descriptive. 
 
	**What are you trying to accomplish with this PR?**  
	This PR will create a model ==gift_card_transactions__daily_rollup== that will rollup gift_card_transactions. Unlike Reportify, this model will disregard shop timezones as we want to expose UTC timezones in the data warehouse.

	**How is this accomplished?**  
This PR creates a new model, ==gift_card_transactions__daily_rollup==, which unions the following stages from gift_card_transactions, and then aggregates on a per day granularity. Dates with no transactions are filled in.

		* ==GiftCardsIssued== (gift cards that were given out by the merchant.)
		* ==GiftCardsSold== (gift cards that were bought.)
		* ==GiftCardsDisabled== (gift cards that are past the disabled_at date.)
		* ==GiftCardsRefunded== (orders that were purchased by gift cards but then refunded for any reason.)
		* ==GiftCardsRedeemed== (orders that were purchased by gift cards.)

	Tests have been added for the new stages, as well as the full pipeline.