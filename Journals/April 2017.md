## Month #2
### Week #13
- - -
#### Monday April 10, 2017
* **Goals**:
	* ~~Finish gift cards modelling for Merchant Data Warehouse.~~
	* Start on other data projects.
* **Accomplishments**:
	* Went through a clustering and regression modelling tutorial in python.
* **Feedback**:
	1. When you expose a schema vs a report to the consumers it's very different.  
		* Reportify:  
    		You are only exposing the final product so data can't be as raw.  
            Ex. **type** column in the model can be *lowercase* but in reportify it should be *uppercase*. 
		* Merchant Data Warehouse:  
			You are exposing the raw models to the merchants, therefore you should think about how you would use these models to build the reportify reports.  
            Ex. you should keep **datetimes** in *UTC* time instead of shop timezone. This is how you would see them in the database.  
	For next time you can keep the logic in first layer (starscream) the same, but when you expose the schema in reportify or in the UI layer you can reference it differently.
	2. Writing better documentation for github PRs. More to the point and descriptive. 
 
	**What are you trying to accomplish with this PR?**  
	This PR will create a model **gift_card_transactions__daily_rollup** that will rollup gift_card_transactions. Unlike Reportify, this model will disregard shop timezones as we want to expose UTC timezones in the data warehouse.

	**How is this accomplished?**  
This PR creates a new model, **gift_card_transactions__daily_rollup**, which unions the following stages from gift_card_transactions, and then aggregates on a per day granularity. Dates with no transactions are filled in.

		* **GiftCardsIssued** (gift cards that were given out by the merchant.)
		* **GiftCardsSold** (gift cards that were bought.)
		* **GiftCardsDisabled** (gift cards that are past the disabled_at date.)
		* **GiftCardsRefunded** (orders that were purchased by gift cards but then refunded for any reason.)
		* **GiftCardsRedeemed** (orders that were purchased by gift cards.)

	Tests have been added for the new stages, as well as the full pipeline.