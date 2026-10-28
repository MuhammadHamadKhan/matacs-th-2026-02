 Write-up

 1. AI vs. rules

In my system, AI does the reading job. It goes through each proposal and picks out the main points, like the price, the number of weeks, the warranty, and whether the licence is mentioned. It also helps judge the team and approach, because that part needs understanding of the text and can't be done with simple rules.

Once the data is extracted, normal code takes over. Code follows fixed rules: if a proposal passes the must-have checks, it moves forward, and if it fails, it is marked ineligible. For example, Proposal B would fail the licence check, so code would mark it ineligible. Code also does the maths for the scores and weights, sorts the final list, and saves the log.

I drew the line here because AI is good at reading messy writing, but it can give slightly different answers each time. Code gives the same answer every time. So AI is used to read and understand, and code is used for anything that must be exact and repeatable.

 2. Consistency and explainability

AI can give slightly different wording each time it reads a proposal. But the decision is not made by the AI. It is made by code. The AI only pulls out facts into a fixed form, like price, weeks, licence yes or no. Code looks at those facts, not at the AI's wording. So no matter how the AI phrases something, the pass or fail result stays the same, because code follows the same rules every time.

If the same proposals were ranked twice, the result would almost always be the same. The maths and the checks are always identical. The only small risk is if the AI reads a fact differently the second time, for example misreading a number. To avoid this, I save the facts the AI extracted, so the ranking is based on saved facts and doesn't change unless someone deliberately re-runs the extraction.

To explain the result, the reviewer sees a table for each proposal. It lists every criterion, the score, its weight, and a short reason. Next to each fact there is a short quote from the proposal as proof, so the reviewer can check it. If a proposal failed a check or was flagged, that reason is shown at the top.
