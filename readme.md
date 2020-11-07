# Workato PM Take-home test (katas)

#### Kata (1): Build an action that creates a ticket in Zendesk and describe how it works
---
**Context:**
How might we go about product testing of `app.workato.com`?

***Observed bugs:***
When user is establishing trigger during recipe creation involving Zendesk, _Triggers_ seen misspelt as _Tiggers_:

![Trigger spelt wrongly](imgs/tigger-spelling.png)

When user is defining actions from Zendesk, _Update_ seen misspelt as _Upsert_:

![Update spelt wrongly](imgs/upsert-spelling.png)

<br />

#### Proposed recipe with create Zendesk ticket action(s): ####
---
1. As a Quality Assurance (QA) tester, I want to quickly file bugs without navigating through Zendesk Agent Support GUI but still have Zendesk tickets recorded for audit.
    + Created a [google form](https://forms.gle/NQ85DzwfA8TdJjxJ6) to capture QA's test data
    + Linked that [google form's data](https://forms.gle/NQ85DzwfA8TdJjxJ6) to [google sheets](https://docs.google.com/spreadsheets/d/1k8cHik1LTvskKfXTE76nulNHzDGWx7YaTdkbcEqwJvU/edit?usp=sharing) as Workato's connectors does not support google forms.
        - This is the `Trigger`; upon addition of google sheets row, a Zendesk ticket is created.
<br />
2. As a product owner, I want to extract relevant data for appropriate action by engineers and transform data meaningfully when I map it over to Zendesk.
    + Created `relevant party to escalate to` form field and map as `tags` in Zendesk
    + Created `URL path of bug` form field and map as `bug URL path` in Zendesk
    + Further segregrate bugs into `bug category` form field to map as `subject` in Zendesk