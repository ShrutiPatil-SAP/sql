# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).
![Untitled Diagram drawio](https://github.com/user-attachments/assets/3159ab46-dcef-45ca-987e-21e97c3822ac)

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.
![Untitled Diagram drawio (1)](https://github.com/user-attachments/assets/26637dfd-c679-43f4-9163-85b01f83dfce)


## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
```
Your answer...
```Type 1 : The CUSTOMER_ADDRESS table will have below columns
CUSTOMER ID
 ADDR LN 1
 ADDR LN 2
 CITY
 STATE
 ZIP CODE
 START DATE
 END DATE

The start date and end date will help to retain the changes. The start date and end date will tell us the time frame, the corresponding address was effective from.
When a a customer changes address from A to B, we can end date the Address A i.e. mark END DATE with the last 
effective date and, keep the END DATE of Address B open (add 9999/12/31 or blank).


Type 2:The CUSTOMER_ADDRESS table will have below columns
CUSTOMER ID
 ADDR LN 1
 ADDR LN 2
 CITY
 STATE
 ZIP CODE

The new address will override the old address in the above table so that, we retain the latest address in the table.


## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
Your answer.
The AdventureWorks Schema is robust and, each entity employee, order, sales, customer, and book entities has its own schema and, relevant tables.
The joins are complex than what my schema is. The architecture is designed by an database architect with proper keys (primary and foriegn).


# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `September 28, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-4-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
