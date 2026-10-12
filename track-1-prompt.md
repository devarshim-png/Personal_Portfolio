You are the product owner of an AI-assisted recruitment screening platform. Write the full contents of `roadmap.md`: how you would own this product, which decisions you would make, and why.

A review panel will grade judgment. A long feature list scores worse than a short set of decisions that name the alternative you rejected.

## The product

The platform receives job applications, screens them against role requirements, ranks candidates, and schedules interviews. The outcome that matters is less hiring-manager time before the first human conversation, without lowering the quality of who gets that conversation.

Facts you must design for:

- A job is posted with a defined set of requirements.
- Applications arrive continuously, up to 500 per day for a popular role.
- Every application is screened against that job’s requirements, scored, and ranked.
- An AI layer reads the resume and cover letter, may ask the candidate up to 5 asynchronous screening questions, and evaluates the responses.
- The AI produces a shortlist, a confidence score, and a reasoning summary per candidate.
- The hiring manager reviews the shortlist and selects who is interviewed.
- The platform sends scheduling invitations only after that selection.
- Candidates who are not shortlisted receive a status update.

Do not invent a different product, a marketplace, or an auto-hire system.

## How to own it

Write in the first person as the accountable product owner. For every major decision use this shape:

- Decision
- Alternative rejected
- Why this one, given this product
- What would change your mind

Resolve these calls. Do not leave them as open questions:

1. Who v1 is for, and which user you will not optimize yet (hiring manager, candidate, recruiter, interviewer).
2. The outcome metric for the first 90 days, and a different outcome metric by month 6. Include one candidate-side metric and one quality guardrail, not only speed.
3. What the AI may decide, and what only a human may decide. Interview selection stays with the hiring manager.
4. How requirements are captured so two candidates are screened against the same bar. Separate must-haves, nice-to-haves, and explicit knockouts. The model does not invent knockouts.
5. Fit score, rank, confidence, and reasoning summary are different objects. Define each. Confidence measures evidence quality, not how strong the candidate is.
6. When a screening question is worth asking, when it is forbidden, and how the 5-question budget is spent. Ask only if the answer can change eligibility or rank, and never ask something the resume already answers.
7. How the shortlist behaves while new applications keep arriving. A list the manager has opened must not reshuffle underneath them.
8. What a non-shortlisted candidate is told, how fast, and what you will not put in that message.
9. Scheduling starts only after an explicit manager selection. Define the smallest scheduling loop you would ship.
10. How you limit biased or unsupported screening. Do not score “culture fit” from unstructured text. Do not train the first model on historical hire/reject labels.
11. What you will cut from the first release, and the phase in which it becomes worth building.

## Constraints

- 500 applications a day on one role is a quality, fairness, and reliability problem. It is not a hyperscale problem. Do not spend the roadmap on infrastructure.
- Screening may take minutes. Losing an application, or sending a wrong status, may not happen.
- Questions are expensive for the candidate. Silence after a deadline is still a decision: score on the evidence you have and lower confidence.
- The manager must be able to see why someone is on the list, disagree, and have that disagreement kept.

## Document structure

Output only markdown for `roadmap.md`. Use these sections and no others:

1. Outcome I am accountable for
2. Users, and who waits
3. Product principles
4. Decisions
5. Experience: apply, screen, review, schedule, close
6. Roadmap in three phases (each phase: outcome, what ships, what is deliberately absent, metric that says it worked)
7. Risks and the control for each
8. What I will not build

## Quality bar

- Concrete policies, thresholds, and time boxes. If you pick a number, say why that number.
- Name failure modes: thin evidence, over-trust of the summary, adverse impact, a resume that tries to instruct the model, a manager who never closes the loop.
- No market sizing, no competitor tour, no vision paragraph, no tool brands unless the brand is the decision.
- A generic ATS vendor who had not read this brief should not have been able to write your decisions section.

Before you write the file, list the eleven decisions privately and confirm each has a rejected alternative. Then output only `roadmap.md`.
