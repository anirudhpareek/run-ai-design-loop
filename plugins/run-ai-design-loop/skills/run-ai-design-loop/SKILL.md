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

Use this skill as an orchestration layer. Load a specialist design,
implementation, image-generation, or motion skill only when that part of the
work actually requires it; do not duplicate its detailed guidance here.

If a specialist skill, renderer, or browser is unavailable, use the closest
available implementation path and state what could not be visually verified.
Ask for screenshots when they would unblock critique; never treat source
inspection alone as rendered proof.

## Operating Contract

- Respect an existing design system, supplied references, product behavior,
  content, and technical constraints.
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

First inspect the current product or brief. Establish the audience, primary
task, desired feeling, platform, brand and technical constraints, existing
design primitives, and the states that must remain functional. Capture a
rendered baseline when an implementation already exists.

Create several meaningfully different direction briefs rather than cosmetic
variants of one layout. Each brief should make clear:

- the design thesis and product metaphor;
- composition, hierarchy, typography, color, and material character;
- one memorable visual or interaction idea;
- how the direction supports the primary task;
- its main usability, accessibility, performance, or implementation risk.

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

Make lightweight rendered proofs when prose is insufficient to judge the
directions. Keep enough real content and behavior for the comparison to be
honest.

Select one direction explicitly against product fit, distinctiveness,
legibility, brand coherence, feasibility, and the user's stated taste. Ask the
user to choose when the decision would materially change the product and they
have not asked for autonomous execution; otherwise choose, state why, and move
forward.

## 2. Define: Turn Direction Into Identity

Freeze the selected direction before polishing it. Record a short design
identity containing:

- a one-sentence thesis and intended emotional response;
- the hierarchy and signature moment;
- a few non-negotiable visual or interaction decisions;
- explicit anti-goals and patterns to avoid;
- the practical accessibility, responsive, and performance limits.

Build or update the interface, then use an independent fresh-context critic
whenever delegation or an equivalent review context is available. If it is not
available, state that limitation and run the same screenshot-only brief as a
constrained self-review.
Give the critic a fresh context containing the design identity, relevant
professional references, and screenshots of the rendered result. Omit source
code, implementation effort, prior rationale, previous critiques, and the
builder's desired score so sunk-cost bias and score gaming do not shape the
review. Before sharing screenshots or artifacts with another agent or service,
remove credentials, personal data, customer data, and confidential material,
and stay within the user's authorized account and service boundaries.

The critic should:

1. Evaluate composition and product hierarchy before fine detail.
2. Compare the result with the intended identity and reference quality bar.
3. Identify generic patterns, inconsistency, weak restraint, and functional
   confusion.
4. Return a short, prioritized set of concrete changes, separating observable
   defects from subjective options.

Prefer ranking against strong examples or anchored criteria over an arbitrary
numeric score. If a score is useful, define what each threshold means and keep
the stopping threshold out of the critic prompt.

Have the builder implement the highest-leverage changes, render the same states
and viewports again, and re-run the unchanged critic brief. Stop when the main
gaps are resolved, feedback becomes marginal or circular, or further changes
would trade away product clarity. Product constraints and explicit user intent
override the critic.

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

Then verify the actual experience:

- render critical states at relevant mobile and desktop sizes;
- inspect real interactions, loading, empty, error, overflow, and long-content
  behavior where applicable;
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

## Handoff

Report the selected direction and rationale, rendered evidence, files changed,
critic feedback resolved or still open, checks run, and any limitations. Label
the result honestly as a concept, prototype, implementation, or production-ready
surface.
