# Track 1: Where does the data come from? 

## What 3–5 source tables would you expect a real company to use for customer churn? For each source, what does one row represent, for example one customer, one month, one event.

**Customer Information**
- contains information for one customer
- column types would include name, id, DOB, plan type(s), tenure, churn or not and churn reason if churn
- primary key: `customer_id`

**Plan Information (separate table for each service provided: phone, internet, etc.)**
- contains information about a plan that is offered to a customer
- column types would include plan type, cost (per tier if tiered), benefits/services provided by this plan
- primary key: `phone_plan_id`, `internet_plan_id`, etc.

**Service Provided**
- contains information about one specific service provided as a part of one or more plans
- column types would include service type, cost, and description
- primary key: `service_id`

**Customer Ledger**
- contains information about transactions between a customer and the company, where each row is a transaction
- column types would include transaction time, transaction type (invoice, bill, refund, etc.), payment type (check, card, etc.), invoice and bill numbers
- primary key: `transaction_id`

**Payment Information**
- contains all used payment types for each customer
- column types wound include what kind of payment, as well as the relevant details (credit card number/type, bank account number, etc.). Also, customers can choose to save a specific payment type for future use, which could be indicated by a binary column
- primary key: `payment_info`

## What keys would you use to connect the data, for example customer_id, account_id, date, etc?

**Customer Information + Plan Information** <br>
For each type of plan (phone, internet, etc.) a string or integer column would exist in the `Customer Information` table that contained the ID (`phone_plan_id`, `internet_plan_id`, etc.) of the plan that specific customer uses.

**Plan Information + Service Provided** <br>
In the `Plan Information` table, a string or integer column would exist that contains a list of the IDs of the services that that plan includes

**Customer Information + Customer Ledger** <br>
In the `Customer Ledger` table, the primary key `customer_id` would exist for each transaction.

**Customer Ledger + Payment Information** <br>
In the `Customer Ledger` table, the primary key `payment_info` would exist for each transaction.

**Customer Information + Payment Information** <br>
In the `Payment Information` table, the primary key `customer_id` would exist for each payment method.


## What are two risks and how would you reduce them? Examples of risks are duplicates, missing IDs, using information that only exists after churn happens, and definitions changing over time.

- Because plans change somewhat frequently and services could be purchased separately from a plan's included services, duplicate charges could exist for a customer if a plan is updated to include a service that a customer is paying extra for already. To reduce this, service types would need to be categorized to allow only one of a service type to be charged for at once, and service types would need to be directly connected to
plan information without being charged for outside of a plan.

- If a customer has not churned, the column indicating churn reason would be *NA* for that customer. Consider creating a separate table for churn information (churn time, reason, customer id) to prevent *NA* values in the **Customer Information** table.








