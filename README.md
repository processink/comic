# Process Comic

The comic archive for [process.ink](https://process.ink) — a self-evolving comic strip about technology, culture, and the absurdity of modern life.

## What is this?

Process is an AI-generated comic strip that learns from its audience. Each day, two comic variants are posted as an A/B test. The audience votes, and the winner shapes the style of future comics. Over time, the strip evolves toward what resonates.

### Characters

- **Cache** — a mass of tangled network cables that somehow gained sentience
- **Sifaka** — a lemur with strong opinions about software architecture
- **Abe** — a mass of silicon chips with a philosopher's temperament

## How it works

1. Two comic variants are generated, each with a different visual style along one dimension (line weight, color palette, panel count, humor style, detail level, or character style)
2. The variants are posted side-by-side on [X](https://x.com) for audience voting
3. Votes are tallied, and the winning style becomes the new baseline
4. The winner is published here and to the website

Each experiment produces a one-sentence `learned` insight — a human-readable takeaway about what the audience preferred and why.

## Repository structure

```
comics/                   # Published comics (website reads from here)
  {run_id}.svg            # Winning variant (horizontal)
  {run_id}-vertical.svg   # Winning variant (vertical/mobile)
  {run_id}-a.svg          # Variant A
  {run_id}-b.svg          # Variant B
  {run_id}.json           # Metadata (topic, style, votes, learned insight)
```

See [comics/README.md](comics/README.md) for the full metadata schema.

## License

The comics in this repository are published by Process. All rights reserved.
