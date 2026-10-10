# Home Credit AI Voice Agent — Loan Against Property (LAP)

An AI voice agent prototype built in Retell AI to conduct an initial Loan Against Property (LAP) eligibility screening conversation. The agent gathers the required eligibility details, handles common customer scenarios, and communicates the next step without promising final loan approval.

> **Project status:** Prototype configured and tested using Retell AI simulation testing.
>
> **Testing snapshot:** 10 simulation test cases passed, 0 failed (100% pass rate), as shown in the Retell AI Batch Testing History screenshot captured on 11 October 2026. Results reflect the configured simulation success criteria and do not guarantee production readiness.

## Live demo

[Open the Retell AI voice agent](https://agent.retellai.com/orb/agent_81ee62f46f114605b5d2e2b51e?token=1a1d895b96ffb04451c5b678952be65c)

**Sharing note:** This is a shareable agent URL. Anyone with access to the link may be able to open the demo. If you do not want this URL publicly accessible, remove it from this README and share it privately with the reviewer instead.

## Project objective

Create a conversational voice agent that performs a preliminary LAP eligibility check in a clear, polite, and consistent way. It should understand answers given out of order, avoid asking for information already provided, and route special cases appropriately.

## Eligibility checklist

The agent must collect these seven items before a normal qualification handoff:

1. **Property type** — residential, commercial, or industrial property is acceptable; agricultural property is not eligible.
2. **Ownership** — sole or joint ownership is accepted.
3. **Original property documents** — originals must be available.
4. **Loan amount** — the maximum offer is ₹75 lakh. If the customer asks for more, offer ₹75 lakh as an alternative and continue only if they accept.
5. **Occupation and income mode** — salaried and self-employed customers may qualify when income is received through a bank account. Cash-only income is not eligible.
6. **Property market value** — record the customer's stated approximate market value.
7. **Requested tenure** — 3 to 15 years inclusive.

## Conversation handling

- **Out-of-order answers:** Remember information already supplied and ask only for missing checklist items.
- **No duplicate questions:** Do not ask again for an item that has already been answered clearly.
- **Disqualification:** Politely stop the standard qualification flow if the property is agricultural, original documents are unavailable, income is cash-only, or the requested tenure is outside 3–15 years.
- **Existing loan / EMI reduction:** Route the customer to a loan-transfer specialist and end the standard new-loan qualification flow.
- **Busy customer:** Ask for a suitable callback time and end the current conversation politely.
- **Maximum amount:** Never represent an amount above ₹75 lakh as available under this offer.
- **Final handoff:** Do not hand off a normally eligible customer until all seven checklist items are captured.
- **No guarantee:** Explain that this is preliminary screening and final approval is subject to lender verification and assessment.

## Repository contents

```text
home-credit-ai-voice-agent/
├── README.md
├── system-prompt.md
├── test-cases.json
├── test-results.md
└── screenshots/
    └── README.md
```

- [`system-prompt.md`](system-prompt.md) — system prompt specification for the Retell AI agent.
- [`test-cases.json`](test-cases.json) — 10 simulation scenarios and their success criteria.
- [`test-results.md`](test-results.md) — summary of the simulation run.
- `screenshots/` — place the Retell Batch Testing History screenshot here.

## Simulation testing

The Retell AI Simulation Testing run shown in the saved evidence reported:

| Metric | Result |
|---|---:|
| Test cases | 10 |
| Passed | 10 |
| Failed | 0 |
| Pass rate | 100% |

Scenarios include a normal eligible customer, agricultural property, cash-only income, existing loan/EMI reduction, amount above the maximum, callback request, unavailable original documents, invalid tenure below the minimum, invalid tenure above the maximum, and out-of-order information.

See [`test-results.md`](test-results.md) for the scenario list and evidence notes.

## Technology

- **Agent platform:** Retell AI
- **Agent design:** Single-prompt voice agent
- **Validation:** Retell AI Simulation Testing / Batch Testing History
- **Artifacts:** Markdown documentation and JSON simulation test cases

This repository documents the voice-agent configuration and testing. It does not claim to contain a separate application backend or frontend.

## Important limitations

- The agent performs preliminary screening only; it does not approve or sanction loans.
- Eligibility rules and product details in this repository reflect the assignment brief used to design the prototype. They should be verified against current official lender policy before real-world deployment.
- Simulation pass results depend on the test prompts and success criteria configured in Retell AI.
- Do not use real customer personal, financial, or property data in public test artifacts.

## How to review

1. Read [`system-prompt.md`](system-prompt.md).
2. Open the [live Retell demo](https://agent.retellai.com/orb/agent_81ee62f46f114605b5d2e2b51e?token=1a1d895b96ffb04451c5b678952be65c).
3. Review [`test-cases.json`](test-cases.json).
4. Review [`test-results.md`](test-results.md) and the screenshot saved in `screenshots/` (if uploaded).

## Author

Prepared as a voice-agent design assignment / prototype.

## License

This repository is provided for assignment review and demonstration. No production use or lender endorsement is implied.
