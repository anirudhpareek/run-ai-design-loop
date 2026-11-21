---
name: run-ai-design-loop
description: >-
  Orchestrate open-ended interface design through divergent concepts, explicit
  direction selection, rendered-artifact critique in fresh context, iterative
  refinement, and a final subtraction and quality pass. Use when the user asks
  AI to explore visual directions, act as a design team or design director,
  improve a generic UI through screenshot critique, or run a
  Discover-Define-Deliver process. For a fully specified design, use the
  constrained-fidelity route only when the skill is explicitly invoked or
  iterative rendered critique is requested. Do not use for design-token
  extraction, isolated polish fixes, or motion-only review.
---

# Run AI Design Loop

Direct the design process from possibility to evidence. The goal is not novelty
by itself; it is a distinctive interface that fits the product, helps the user,
and survives production constraints.

Use this skill to run the design loop. When translation, motion, imagery, or
another specialist task becomes the limiting step, read and use the closest
available specialist skill for that step. Add another only for a distinct need.

If a specialist skill, renderer, or browser is unavailable, use the closest
available implementation path and state what could not be visually verified.
Ask for screenshots when they would unblock critique; never treat source
inspection alone as rendered proof.

## Operating Contract

- Protect explicit requirements, scoped references, user data, and required
  product behavior. Treat inherited layout, component choices, and style
  conventions as defaults unless the brief or project makes them binding. If
  a default is getting in the way, test a different approach in a reversible
  preview. Resolve conflicting requirements before making dependent changes.
- Judge rendered output and live behavior. Source code, passing builds, and the
  presence of CSS are not visual proof.
- Use user taste as an input: record what they prefer, reject, and want users to
  feel. Do not replace those signals with generic adjectives such as “modern.”
- Keep critique loops finite. The default maximum is two critique-and-revision
  cycles. Another bounded round requires the user's authorization.
- Never paste, echo, commit, or embed API keys. Use already configured tools or
  scoped environment secrets without exposing their values.
- Treat generated imagery, video, shaders, and 3D as optional materials. Add
  them only when they strengthen the selected direction and can meet
  accessibility, performance, licensing, and fallback requirements.
- Confirm that supplied and reference assets may be used as intended. Do not
  assume that access to an asset grants permission to copy or redistribute it.

If a user supplies a credential or asks for a client-side secret, do not use it
in that unsafe boundary. Continue the safe remainder of the design work, require
a server-only or configured-secret path for the blocked integration, and advise
rotation if the value may be real. Before handoff, verify that it did not enter
changed files, client bundles, logs, screenshots, or deployment inputs.

## Route the Request

- **Open direction:** run the full Discover, Define, and Deliver loop.
- **Existing but generic interface:** capture the baseline, explore only the
  weak dimensions, then run independent critique and Deliver.
- **Precise reference or specification:** use this constrained-fidelity route
  only when explicitly invoked or iterative rendered critique is requested.
  Treat the reference as the source of truth, skip creative divergence,
  establish allowed files, surfaces, and preserved behavior before editing,
  compare paired renders at target viewports, and verify the final diff stayed
  inside the boundary. Never remove a reference-mandated detail during the
  subtraction pass. For a simple one-shot implementation, route to the relevant
  implementation skill instead.

## 1. Discover: Create Real Alternatives

Inspect the current product and the available brief first. Identify the audience,
primary task, outcome, and decision still open. Record what is fixed, what is an
existing default worth testing, and what is genuinely unknown. Capture a rendered
baseline when an implementation already exists. Read the project's DESIGN.md
and any linked design rules before exploring. Use confirmed project preferences
when comparing directions and polishing.

If two plausible interpretations would change the audience, primary task,
constraints, or definition of success, ask one focused question that explains
the choice it unlocks. Continue common, reversible work while waiting. If the
answer is already in the evidence, the user has settled it, or the choice is
low-cost and reversible, proceed and note any material assumption. Delegated
design judgment gives you room to choose a direction. Resolve conflicts
between binding requirements before dependent edits.

Create several meaningfully different direction briefs rather than cosmetic
variants of one layout. Each brief should make clear:

- the design thesis and product metaphor;
- composition, hierarchy, typography, color, and material character;
- one memorable visual or interaction idea;
- what should become easier, clearer, or more memorable in the primary task,
  and which moment would show whether that happened;
- its main usability, accessibility, performance, or implementation risk.

Name the main difference that people could actually experience, such as the
order they encounter information or what stays visible while they act. When
the existing design is still a viable choice, include it as a baseline using
the same task. Keep exploration scoped to the decision the user left open.

Use one or more of these divergence mechanisms when needed:

- **Reference tension:** combine relevant cues from different fields while
  avoiding literal copying.
- **Ambitious constraint:** propose an unusual but product-relevant structure,
  material, spatial model, or interaction instead of asking for “something
  unique.”
- **External seed:** if outputs keep converging, generate a real random string
  with a local tool and use its patterns to influence creative decisions. The
  seed is a diversity device, not a quality signal, and should not appear in
  the interface.

When two credible directions would change what people notice, choose, or do in
the primary task, compare them as small playable prototypes before choosing.
Use the same representative content, viewport, task, and resettable starting
state. Add one realistic edge case when it could change the choice. Change one
input dimension at a time, such as ordering, long names, or empty states. If
randomization helps probe the case, use synthetic values and record the seed
or exact fixture so each direction can replay it. Keep comparisons isolated
from the shipped UI. If playback is unavailable, use matched captures or
recordings and state what behavior remains unverified. A lightweight render
can settle a visual-only choice. If a direction changes how people resume
their work after an action, cancellation, or interruption, test that return
with the same starting state. Check what stays visible and what state, such as
filter, selection, or reading position, is preserved.

Select one direction explicitly against product fit, distinctiveness,
legibility, brand coherence, feasibility, and the user's stated taste. Ask the
user to choose when the decision would materially change the product and they
have not asked for autonomous execution; otherwise choose, state why, and move
forward.

At the choice point, give the designer a neutral task they can try and one
specific moment to react to. Keep their reason tied to the option and state
where it happened. If they prefer one overall but like a detail in another,
check that the detail serves the chosen direction and replay the affected task
before carrying it over.

If the user is still torn, use the comparison or critique to identify a shared
obstacle, missing evidence, or a tradeoff the first comparison obscured. Fix
shared obstacles the same way across the viable options, narrow to meaningful
finalists, and replay the same task and conditions. Use one such follow-up per
decision within the revision budget. Ask one focused question tied to the tradeoff
the replay exposes. If the user is still torn after the replay, no new evidence
justifies it, or the user wants to keep the options open, state your recommendation
and leave the choice open. Polish a direction only once it has been selected.

## 2. Define: Turn Direction Into Identity

Freeze the selected direction before polishing it. Record a short design
identity containing:

- a one-sentence thesis and intended emotional response;
- the hierarchy and signature moment;
- a few non-negotiable visual or interaction decisions;
- explicit anti-goals and patterns to avoid;
- the practical accessibility, responsive, and performance limits.

Build or update the interface. Run a [rendered review](references/rendered-review.md)
with a fresh-context critic when available. Get their visual observations first,
before sharing the intended direction, past feedback, or a suspected flaw.
When first-use clarity matters, give a neutral task and ask for their first
action and expected outcome before explaining the design. Then review fit
against the selected direction. If independence is unavailable, disclose it
and run the same review in a constrained context.

Have the builder implement the highest-leverage changes, render the same states
and viewports again, and re-run the unchanged critic brief. Stop when the main
gaps are resolved, feedback becomes marginal or circular, or further changes
would trade away product clarity. Product constraints and explicit user intent
override the critic.

If the remaining decision is about a tunable detail such as density or motion,
save two replayable presets of the same design with the same starting state.
Change the value under review, keep other variables fixed, and apply the chosen
values to the implementation. Use existing preview controls when possible.
For motion, capture the decisive intermediate state or interruption if start
and end frames miss the difference.

Before retaining rich generated media, define and measure a transfer,
critical-path, and runtime-performance budget appropriate to the product and
target devices. Video or animated-canvas treatments need a poster or static
fallback and reduced-motion handling; keep them off the critical path unless
the core experience explicitly depends on them.

## 3. Deliver: Subtract, Then Prove

Run a subtraction pass before adding final decoration. Remove anything that
does not help the primary task or reinforce the chosen identity. Audit for:

- redundant labels, explanatory copy, badges, cards, and containers;
- decorative gradients, glows, shadows, and textures with no clear role;
- repeated visual motifs, arbitrary iconography, and fake data visualizations;
- custom controls that are less usable than appropriate native or established
  components;
- multiple competing “signature” effects where one strong move would suffice.

Before calling the design done, use the [rendered review](references/rendered-review.md)
for a 2× inspection of high-risk seams and edges at a fixed layout. Replay the
state that exposes each join and compare the same crop after a fix. If dynamic
content can change the outcome, replay the task with one relevant stress case.

Then verify the actual experience:

- render critical states at relevant mobile and desktop sizes;
- run the primary task from its normal entry point and inspect the result the
  user relies on, such as a saved state after reload or the opened export;
- inspect loading, empty, error, overflow, and long-content behavior where
  applicable;
- check semantic controls, keyboard and focus behavior, contrast, touch targets,
  reduced-motion handling, and non-motion fallbacks;
- check asset weight, image dimensions, video or canvas fallbacks, responsive
  loading, and interaction smoothness;
- preserve data contracts and user-provided content precedence;
- confirm the final diff stays inside any declared file and behavior boundary;
- distinguish prototype polish, implementation health, production readiness,
  and genuinely public deployment. Do not present one as proof of another.

Complete the relevant QA before deploying. Deploy only when the user has
explicitly requested or authorized it. After deployment, verify the target is
reachable in the intended authentication context before claiming it is
published or publicly shareable.

## Learn from Corrections

When the user confirms a reusable preference and has authorized recording it,
add the narrowest applicable rule to the project's DESIGN.md. Use
[taste rules](references/taste-rules.md) to trace it to feedback, check its scope,
and merge it with related guidance. Keep inferred reasons provisional.

## Handoff

Report the selected direction and rationale, rendered evidence, files changed,
critic feedback resolved or still open, checks run, and any limitations. Show
what changed the decision and give the user the smallest useful artifact to
revisit it. Label the result honestly as a concept, prototype, implementation,
or production-ready surface.

If the user asks to track steering, count direction decisions, undecided
responses, clarifying answers, and course corrections separately. Report elapsed
time separately from observed hands-on time. Use a matched comparison before
claiming a speed improvement.
