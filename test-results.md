# Simulation Test Results

## Summary

The Retell AI Batch Testing History screenshot captured on **11 October 2026** showed the following result for the selected batch:

| Metric | Result |
|---|---:|
| Test cases | 10 |
| Passed | 10 |
| Failed | 0 |
| Pass rate | 100% |

**Interpretation:** All 10 test cases passed their configured simulation success criteria. This is evidence of the tested scenarios, not a guarantee that every possible conversation is correct or that the agent is production-ready.

## Scenarios covered

1. Eligible customer — all seven checklist items collected before preliminary handoff.
2. Agricultural property — polite immediate disqualification.
3. Cash-only income — polite disqualification.
4. Existing loan / EMI reduction — loan-transfer specialist route.
5. Requested amount above ₹75 lakh — offer the ₹75 lakh maximum and continue only if accepted.
6. Busy customer — callback time request and end current conversation.
7. Original property documents unavailable — disqualification.
8. Requested tenure below minimum — 2 years is outside the 3–15 year range.
9. Requested tenure above maximum — 16 years is outside the 3–15 year range.
10. Out-of-order information — retain supplied answers and avoid duplicate questions.

## Evidence

Save the screenshot from Retell AI's **Simulation → Batch Testing History** page as:

` screenshots/batch-testing-results.png `

The screenshot should show the batch totals and a few visible test-case results. Do not include real customer personal or financial information.

## Retest recommendations

Before final submission, manually inspect at least:
- the eligible conversation to ensure all seven checklist items were captured before handoff;
- the ₹75 lakh alternative flow, including what happens if the customer declines;
- the callback flow to ensure the agent does not claim a callback is scheduled without confirmation;
- the public demo link in a private/incognito browser window.

## Platform

Retell AI — Single-Prompt Agent, Simulation Testing / Batch Testing History.
