# Sofi

Sofi (from Sophia, Σοφία, wisdom) is a terminal coding assistant written in Python.
You describe a software-development pipeline as a graph of agent nodes, choose the
model and effort for each node, and Sofi runs it on your repository, looping where
the pipeline says to and asking for your approval before every file change.

> **Status:** early development. Nothing below works yet; this is the target for v1.
> Sofi is being built from scratch as the final project of the AUEB
> "AI for Developers" programme.

## Planned for v1

- A terminal UI in the style of the Claude CLI: transcript, multi-line composer, `/` commands.
- Pipelines defined as graphs: nodes, conditional edges, loops with limits.
- Reusable agent profiles: model, effort, instructions, rules, allowed tools.
- Per-run overrides of model and effort for each node.
- Read, search and edit tools sandboxed to the repository; every edit is a diff you approve,
  applied on a dedicated git branch.
- OpenAI as the first provider, behind an interface so others can be added.
- Saved runs and an evaluation suite.

## Development

Requires [uv](https://docs.astral.sh/uv/).

```
git clone https://github.com/dimitriskl/agent-sofi.git
cd agent-sofi
uv sync
uv run sofi
uv run pytest
```

Sofi reads the OpenAI key from the `OPENAI_API_KEY` environment variable.
Never put keys in files inside the repository.

## License

MIT, see [LICENSE](LICENSE).
