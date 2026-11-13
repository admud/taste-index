# Prompt 06: Review a complete app flow with evidence

**Use when:** a mobile demo looks polished in one screenshot but needs a credible interaction review. Complements [the static critique](04-critique.md) and [the motion workflow](../playbook.md#app-ui-and-motion-workflow).

**Inputs:** the current build/commit, one named user task, device and viewport, real copy, permitted reference screenshots, and a recording of the entire flow. A screenshot alone cannot establish navigation or animation quality.

## Copy-paste prompt

```text
Review this flow, then improve only the three highest-impact gaps.

Product: {{PRODUCT}}
Audience: {{AUDIENCE}}
Task and success state: {{TASK → OBSERVABLE SUCCESS}}
Build/commit: {{BUILD}}
Platform/device: {{PLATFORM + DEVICE + VIEWPORT}}
Reference assets and what each contributes: {{ASSETS + PRINCIPLES}}
Allowed changes: {{SCOPE}}
Known limitations: {{LIMITATIONS}}

1. Inspect the supplied evidence before judging. List what you could actually
   open. If no recording or runnable build is available, mark behaviour NOT TESTED.
   Do not infer working controls from screenshots or fabricate frame timestamps.

2. Write a short visual contract: type hierarchy, spacing rhythm, colour roles,
   component states, navigation model and motion purpose. Apply principles using
   our own identity; don't copy distinctive assets or text.

3. Make a state map for the selected task. Include initial, loading, success,
   error, empty and interrupted states where relevant. Each edge needs a user
   action, expected destination and retained/cleared state.

4. Inspect the real flow and record evidence for:
   - primary action and its success state;
   - repeat taps while work is pending;
   - Back, Close and Cancel, including reopening;
   - returning after interruption;
   - slow/failing work and retry;
   - keyboard or accessible alternatives;
   - large text and reduced motion.
   Only simulate failures in an authorized local/test environment. Don't submit
   payments, messages, account changes or real destructive actions as tests.

5. Compare like-for-like screenshots: same viewport, same state and real copy.
   Cite file names or recording timestamps for each issue. Distinguish measured
   values from visual estimates. Prefer correctness and legibility over animation.

6. Rank three fixes by user impact, not novelty. For each: exact change, affected
   state, expected benefit and reproducible test. Preserve already-working flows.
   If implementation is authorized, make the changes and rerun the affected tests.
   Otherwise give a bounded patch plan, not a claim of implementation.

7. Return:
   a) observed evidence and coverage gaps;
   b) before/after findings with build IDs;
   c) PASS / FAIL / NOT TESTED for each relevant test;
   d) remaining blockers and the next specific action.
   Never label the app production-ready from this review alone.
```

## Evidence table

| Case | Action | Expected result | Observed evidence | Status |
|---|---|---|---|---|
| Main path | Complete the chosen task | Named success state, once | File/time/build | Not tested |
| Repeat input | Tap again while pending | No duplicate action | File/time/build | Not tested |
| Dismiss/reopen | Close, then reopen | Intended navigation and state | File/time/build | Not tested |
| Failure/retry | Simulate failure safely | Useful error; safe retry | File/time/build | Not tested |
| Accessibility | Large text/reduced motion | Content/action remains usable | File/time/build | Not tested |

"Not applicable" needs a reason. A failed functional case cannot be offset by a high visual score.

## Bounded completion rule

Fix at most three issues per pass, then capture new evidence. Finish this review when the selected task passes its applicable checks and no critical defects remain; report untested platforms and integrations separately. A beautiful reference does not establish conversion uplift, accessibility compliance or security.

## Source and adaptation

The owner shared [Jaimin's post](https://x.com/jaimintf/status/2120190320684179923). Its linked [Appllama repository](https://github.com/Appllama/appllama-skills) describes studying reference flows and validating native mobile screens in a simulator. The repository was read on 13 November 2026; the X post could not be reopened in this pass.

This prompt and evidence table are an original, stack-neutral adaptation, not a transcription of that post or copied skill code. The source targets Expo/React Native. Its standalone design skill does not require the paid MCP, whereas the MCP requires Pro and credits. This prompt requires neither an installation nor a subscription. No creator images or trademarks are included.
