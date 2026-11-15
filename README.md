# Skills

This repo has two skills that I made. A skill is a folder holding a `SKILL.md` file of instructions, which an AI agent loads when a request matches the description at the top of the file. Claude, Gemini CLI, and Antigravity all read this format.

1. `ethical-thinking` helps you reason through a decision with ethical stakes, such as whether to launch a feature, using the Ethics Toolkit from Stanford's McCoy Family Center for Ethics in Society.
2. `eamonn-voice` makes text that will go out under my name read as if I wrote it, and keeps out the habits that make readers suspect an AI wrote it.

The first is for anyone. The second describes how I write, so it is not much use to anyone else as-is, but it might be a useful model if you want to make one for your own writing.

## Installing

In the Claude app you upload a skill as a zip file under Customize > Skills. The zip has to contain the skill folder itself, not just the files inside it:

```sh
git clone https://github.com/eobrain/skills.git
cd skills
zip -r ethical-thinking.zip ethical-thinking
```

In Claude Code you can add this repo as a plugin marketplace and install from it:

```
/plugin marketplace add eobrain/skills
/plugin install ethical-thinking@eobrain-skills
```

Otherwise, copy the skill folder into the agent's personal skills directory. That is `~/.claude/skills/` for Claude Code, `~/.gemini/skills/` for Gemini CLI, and `~/.gemini/config/skills/` for Antigravity:

```sh
git clone https://github.com/eobrain/skills.git
mkdir -p ~/.claude/skills
cp -r skills/ethical-thinking ~/.claude/skills/
```

## ethical-thinking

The Ethics Toolkit (v1.1, October 2025) by Manuela Travaglianti and Thomas Both is five printable worksheets (a Future Story, an Impacts Explorer, an Ethics Frame, an Ethics Gauge, and a Weighing Options sheet) plus a deck of nine Value Cards. The skill recasts them as question sequences and chat formats that an agent can work through with you.

It uses the lightest treatment that fits the decision:

1. A quick check of a few paragraphs, for an everyday question.
2. One tool, usually the Ethics Frame, for a concrete plan.
3. A full pass through the toolkit's three stages (explore, evaluate, and decide) for something like a launch or a policy.

In every case the agent structures the reasoning and leaves the decision to you.

The toolkit is licensed CC BY 4.0, and the attribution is at the end of the `SKILL.md`. This adaptation is not affiliated with or endorsed by Stanford.

## eamonn-voice

The profile in this skill was built from about 44,000 words I wrote between 2002 and 2024: my blog at eamonn.org, tweets, GitHub READMEs, LinkedIn posts, and sent email. It records measured habits, such as a mean sentence length of 23 words and almost no em-dashes, along with excerpts of my writing so that the agent can pick up the rhythm.

It also lists the tells of AI-generated prose to keep out, and it tells the agent never to make up an anecdote or a number and attribute it to me. When a request is too thin to write from, the agent asks, or leaves gaps in square brackets for me to fill.

## License

Everything here is licensed under [CC BY 4.0](LICENSE), the same license as the Stanford toolkit.
