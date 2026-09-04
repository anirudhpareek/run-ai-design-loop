# Run AI Design Loop

A reusable design-direction skill for ChatGPT and Codex. It moves an interface
from divergent concepts to an explicit direction, fresh-context rendered
critique, bounded revision, and a final subtraction and quality pass.

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
codex plugin marketplace add /absolute/path/to/run-ai-design-loop-0.1.0
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
```

## License

MIT. See [LICENSE](LICENSE).
