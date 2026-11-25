# Shuyi Engine: reverse-engineering research materials

The scripts, fixture crates and results of four experiments run for
[Shuyi Engine](https://github.com/Zafnok/shuyi-engine)'s *Public demo
defenses* track. They lived in the engine at `tools/research/` until
engine ticket 2093 moved them here, with their history, so that the
engine's builds and CI no longer carry them.

The findings are the engine's reports; this repository only holds what
reproduces them.

| Folder | Engine ticket | Report |
| --- | --- | --- |
| [`2912/`](2912/) | 2912, game cloning by threat path | [`2912-game-cloning-threat-paths.md`](https://github.com/Zafnok/shuyi-engine/blob/f4b902f89e317504bcf1a4fc3544517923ca1c77/docs/research/2912-game-cloning-threat-paths.md) |
| [`2913/`](2913/) | 2913, human-readable, AI-disruptive clips | [`2913-human-readable-ai-disruptive-clips.md`](https://github.com/Zafnok/shuyi-engine/blob/f4b902f89e317504bcf1a4fc3544517923ca1c77/docs/research/2913-human-readable-ai-disruptive-clips.md) |
| [`2914/`](2914/) | 2914, a cold rules kernel against dynamic analysis | [`2914-protected-cold-rules-dynamic-analysis.md`](https://github.com/Zafnok/shuyi-engine/blob/f4b902f89e317504bcf1a4fc3544517923ca1c77/docs/research/2914-protected-cold-rules-dynamic-analysis.md) |
| [`2915/`](2915/) | 2915, capture controls, recipient marks and AI-use signals | [`2915-capture-controls-marks-and-ai-signals.md`](https://github.com/Zafnok/shuyi-engine/blob/f4b902f89e317504bcf1a4fc3544517923ca1c77/docs/research/2915-capture-controls-marks-and-ai-signals.md) |

The track's closing report is the engine's
[2917](https://github.com/Zafnok/shuyi-engine/blob/f4b902f89e317504bcf1a4fc3544517923ca1c77/docs/research/2917-reverse-engineering-angles-not-yet-covered.md).

## Running them

The scripts expect to sit at `tools/research/` inside an engine checkout:
the fixture crates depend on the engine's crates by relative path, and
the scripts find files from the engine's root.

**As they last ran.** The engine's commit
[`f4b902f8`](https://github.com/Zafnok/shuyi-engine/tree/f4b902f89e317504bcf1a4fc3544517923ca1c77/tools/research)
is the last that still has them, with the two fixture crates in its
workspace and CI's browser replay step. Check it out and follow each
report's *Reproduce* section as written:

```sh
git clone https://github.com/Zafnok/shuyi-engine.git
cd shuyi-engine
git checkout f4b902f89e317504bcf1a4fc3544517923ca1c77
```

**On a later engine.** Clone this repository into `tools/research/` of
the engine checkout, and add `tools/research/2912/fixture` and
`tools/research/2914/web-fixture` back to the root `Cargo.toml`'s
`members`. The engine's API may have moved since, so expect to fix the
fixtures against it:

```sh
git clone https://github.com/Zafnok/shuyi-engine-research.git tools/research
```

`2913/capture/` is its own workspace (it has its own `Cargo.lock`) and
is built with `--manifest-path`, as the reports say.

## License

Like the engine, MIT OR Apache-2.0, at your option:
[`LICENSE-MIT`](LICENSE-MIT), [`LICENSE-APACHE`](LICENSE-APACHE).
