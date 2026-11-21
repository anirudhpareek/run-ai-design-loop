# Rendered review

## Cold read, then review against intent

1. Share the whole render and a few high-risk details with a fresh reviewer.
   Omit the intended design, suspected defects, earlier feedback, source code,
   effort, preferred variant, and expected score. Give options neutral labels
   and vary viewing order across reviewers. Before sharing evidence with another
   agent or service, remove credentials, personal and customer data, and
   confidential material. Stay within the authorized account and service.
2. Ask what looks or feels off. Start with composition and task hierarchy,
   then examine the places where neighbors or states meet. Look for doubled
   edges, uneven gaps, mismatched corners, clipping, shifting alignment, and
   details that look detached or imply a different action.
3. For first-use clarity, supply a neutral goal and record the first action and
   expected outcome before giving away the intended control, gesture, scope,
   or next state. For a row-versus-list scope check, “prepare these subscriber
   records for a teammate” is enough context.
4. Reveal the identity, intended behavior, and relevant references. Check fit,
   consistency, restraint, generic patterns, and functional confusion. For each
   priority finding, identify the element and state, the visible evidence and
   user effect, and the smallest fix worth testing. Call out what should be
   preserved. Separate a taste judgment from behavior and label predictions.
   Use a recording or live input to confirm motion and behavior. Check an
   adjacent relevant state before turning a finding into a general rule.

Report the most important findings before asking the designer for their reaction.
Use anchored criteria when ranking options. If scoring helps, define thresholds
and keep the stopping threshold out of the prompt.

## Close-up and stress check before sign-off

- Open the full render at the intended viewport. Capture and magnify relevant
  regions at 2× with the layout fixed. Inspect joins where surfaces meet,
  overlap or clip. Look for small gaps, stray slivers, uneven outlines, and
  disconnected shapes. Replay the moment that exposes the seam and use a
  narrower supported viewport where the geometry changes. After any fix,
  compare the same crop from the same state. Report unavailable views.
- When dynamic values affect the primary task, identify the value most likely
  to break it. Pair normal data with one realistic stress fixture such as
  duplicate labels, extra-long or non-Latin text, or an empty collection.
  Use an existing test hook or isolated preview with synthetic data. Keep a
  reset and reuse the same fixture for the retest. Check the actual result.
  For example, duplicate search results should remain distinguishable before
  Enter and should still open the intended item.
