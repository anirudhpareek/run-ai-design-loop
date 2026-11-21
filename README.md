# Run AI Design Loop

A design-direction skill for ChatGPT and Codex. Compare directions you can try,
use critique to see where they hold up, and choose what to develop.

## Try it

> Use $run-ai-design-loop on this existing photo review screen. I’m torn
> between keeping the thumbnail strip visible and giving the photo the whole
> frame. Let me try both while moving through the same set of photos and
> returning to the one I was reviewing. Help me decide what to keep.

When a comparison leaves you torn, the loop looks for a shared usability issue
or a tradeoff the first pass missed. It gives the remaining options the same
test so you can make a more informed choice.

## Install as a plugin

Add this GitHub repository as a Codex marketplace:

```bash
codex plugin marketplace add anirudhpareek/run-ai-design-loop --ref main
codex plugin add run-ai-design-loop@anirudh-design
```

Then start a new Codex task or restart the ChatGPT desktop app. You can also
open the Plugins Directory, choose the **Anirudh Design** source, and manage
**Run AI Design Loop** there. Invoke the bundled skill with
`$run-ai-design-loop` in Codex or select it with `@` in ChatGPT.

To fetch a later release:

```bash
codex plugin marketplace upgrade anirudh-design
```

## Install from a shared archive

After unzipping the release, add its absolute folder path as a local
marketplace and install the plugin:

```bash
codex plugin marketplace add /absolute/path/to/unpacked-run-ai-design-loop
codex plugin add run-ai-design-loop@anirudh-design
```

## Install as a standalone skill

If you only want the skill folder, clone the repository and copy it into your
user skills directory:

```bash
git clone https://github.com/anirudhpareek/run-ai-design-loop.git
mkdir -p "$HOME/.agents/skills"
cp -R run-ai-design-loop/plugins/run-ai-design-loop/skills/run-ai-design-loop "$HOME/.agents/skills/"
```

Codex normally detects new skills automatically. Restart it if the skill does
not appear.

## Methods and credit

- Tie feedback to an element or moment in a playable option. [Design Lab](https://github.com/0xdesign/design-plugin)
- Compare designs with controlled inputs and repeatable states. [Component Canvas](https://www.ui-skills.com/skills/ibelick/component-canvas)
- Check what the interface shows alongside how it reads. [Impeccable](https://github.com/pbakaus/impeccable/blob/main/skill/reference/critique.md)
- Capture the moment that matters in a transition and save choices you can
  replay. [Interface BTS](https://iamnoman.com/interface-bts), [DialKit](https://github.com/joshpuckett/dialkit)
- Check the result through the actual workflow. [Toolcraft](https://github.com/pixel-point/toolcraft)
- Look closely at how neighboring surfaces and states fit together. `tactile-design`
- Turn confirmed, recurring design corrections into scoped project rules.
  [Learn Taste](https://aiforui.dev/skills/learn-taste)
- Pick a specialist when a specific part of the work needs one. [Ask Emil](https://aiforui.dev/skills/ask-emil)
- Replay the primary task with a realistic stress fixture. [Break UI](https://aiforui.dev/skills/break-ui)

## What it expects

- An interface brief or an existing implementation to improve.
- Rendering or screenshots for visual verification whenever possible.
- Optional specialist implementation, image-generation, or motion skills when
  the selected direction actually needs them.
- At most two critique-and-revision cycles by default.

The skill contains no API keys, external service configuration, scripts, or
bundled assets.

## Public availability

This repository makes the plugin public and installable by URL. It does not by
itself list the plugin in OpenAI's universal Plugins Directory; that directory
uses a separate publisher verification and review process.

## Repository layout

```text
.agents/plugins/marketplace.json
plugins/run-ai-design-loop/
  .codex-plugin/plugin.json
  skills/run-ai-design-loop/
    SKILL.md
    agents/openai.yaml
    references/
      rendered-review.md
      taste-rules.md
```

## License

MIT. See [LICENSE](LICENSE).
