 MATACS Technical Assessment: AI Proposal Triage Design

Name: Muhammad Hamad Khan
Reference: MATACS-TH-2026-02
Role: Associate Software Developer
Time actually spent:About 50 minutes

 What is in this repository

- [WRITEUP.md](./WRITEUP.md): my answers to the five questions
- [PROMPTS.md](./PROMPTS.md): the AI prompts I would use for extraction and scoring
- [ranking.json](./ranking.json): my expected ranking of proposals A to E
- [diagram/](./diagram/): my process-flow diagram, from upload to ranked output

 How I used AI tools

I used Claude to help me understand the brief, plan the design, and draft the wording of my answers. I explained my ideas in my own words, and then read, checked and adjusted the text myself.

One place where I disagreed with the AI: the AI suggested that it would both extract the facts from the proposals and make the decision. I disagreed because AI can give different answers each time, and a decision like pass or fail has to be exact and repeatable. So I changed the design: the AI only extracts facts, and plain code makes every decision.
