 Write-up

 1. AI vs. rules

In my system, AI does the reading job. It goes through each proposal and picks out the main points, like the price, the number of weeks, the warranty, and whether the licence is mentioned. It also helps judge the team and approach, because that part needs understanding of the text and can't be done with simple rules.

Once the data is extracted, normal code takes over. Code follows fixed rules: if a proposal passes the must-have checks, it moves forward, and if it fails, it is marked ineligible. For example, Proposal B would fail the licence check, so code would mark it ineligible. Code also does the maths for the scores and weights, sorts the final list, and saves the log.

I drew the line here because AI is good at reading messy writing, but it can give slightly different answers each time. Code gives the same answer every time. So AI is used to read and understand, and code is used for anything that must be exact and repeatable.

 2. Consistency and explainability

AI can give slightly different wording each time it reads a proposal. But the decision is not made by the AI. It is made by code. The AI only pulls out facts into a fixed form, like price, weeks, licence yes or no. Code looks at those facts, not at the AI's wording. So no matter how the AI phrases something, the pass or fail result stays the same, because code follows the same rules every time.

If the same proposals were ranked twice, the result would almost always be the same. The maths and the checks are always identical. The only small risk is if the AI reads a fact differently the second time, for example misreading a number. To avoid this, I save the facts the AI extracted, so the ranking is based on saved facts and doesn't change unless someone deliberately re-runs the extraction.

To explain the result, the reviewer sees a table for each proposal. It lists every criterion, the score, its weight, and a short reason. Next to each fact there is a short quote from the proposal as proof, so the reviewer can check it. If a proposal failed a check or was flagged, that reason is shown at the top.
  
 3. Human in the loop
A person checks the result at several points. First, they review any proposal the system flagged or marked ineligible, for example one with missing information or suspicious text, and confirm what should happen to it. Second, they review the final ranking. They check that it follows the instructions and rules, and that nothing looks unfair or biased. If something looks wrong, they can override a score or a position, but they must write a reason. The final award decision is always made by a person, never by the AI or the code.

The system keeps a log so the result can be checked later. It saves the proposal that was uploaded, the facts the AI extracted from it, the decisions code made from those facts (pass or fail, scores, ranking), and the version of the criteria that was used. It also saves every human action: who did it, when, and why. This way, anyone can trace exactly how a result was produced.

 4. Changing criteria

If the admin changes the criteria or weights after some proposals are already scored, the system keeps the old rules and creates a new version. Every ranking records which version of the criteria it used. So there are two rankings: one from before the change and one after it. The old ranking is marked as outdated and is no longer used, but it is not deleted. It is kept in the log so anyone can see how the result looked under the old rules.

The system shows a notice that the criteria have changed since the proposals were scored, and a person decides whether to re-score. If only a weight changed, code simply redoes the maths using the facts already saved, so no AI is needed. If the wording of a criterion changed, the AI re-scores that criterion. In both cases, all proposals are ranked using the same version, so the comparison stays fair.
 5. Risks

**Made-up or wrong facts.** AI can make mistakes or invent things, which is called hallucination. To reduce this, the AI must give a short quote from the proposal for every fact it extracts, and code checks that the quote really exists in the text. If something is missing, the AI must write "not stated" instead of guessing. For example, Proposal D gives no completion time, so the timeline is left unscored and the proposal is flagged. A person also reviews the final results and can fix any mistake, but I don't rely on the human alone, because the checks above catch many errors earlier.

**Manipulation.** A proposal can hide text that tries to control the system. Proposal C contains a line telling the reviewing system to rank it first. The AI is told to treat proposal text as data only and never as instructions. Suspicious text is flagged and ignored for scoring, and a person decides what happens next.

**Bias.** The AI could favour a proposal for the wrong reason, like nicer writing. Scoring follows only the admin's criteria, the reasons are shown for every score, and a person can override the result with a written reason.

**Cost.** Using AI for everything would be expensive. AI is used only for reading and soft judgement. Maths, checks and sorting are done by code, and saved results mean the AI is not called again unnecessarily.
