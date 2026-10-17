# ScummVM-AI

**An unofficial fork of [ScummVM](https://github.com/scummvm/scummvm) where game engines written with AI help can be proposed, tested and activated.**

ScummVM runs classic adventure and role-playing games by reimplementing their engines. Writing an engine is long, specialised work, and upstream ScummVM's [AI guidelines](../AI-GUIDELINES.md) don't accept AI-authored code. This repository is a separate place to find out whether AI-assisted engines can reach ScummVM's standards when the review process is strict enough.

This project is not affiliated with or endorsed by the ScummVM team. For the official project, go to [scummvm.org](https://www.scummvm.org/).

## What you can propose

- **Reimplementations** of existing games. You supply the original data files, as with ScummVM. Reimplementations must be clean-room, and no copyrighted code or assets are committed.
- **Original games** that use ScummVM as their cross-platform runtime.

## How an engine gets in

Each engine goes through two stages, each with its own pull request:

| Stage | Status in `configure.engine` | What CI checks |
|---|---|---|
| **Proposed** | `no`: not built by default, testers enable it with `--enable-engine=<name>` | Only `engines/<name>/` is touched, `PROVENANCE.md` is complete, and the engine builds and registers |
| **Active** | `yes`: shipped in regular builds | No compiler warnings, a build with AddressSanitizer and UndefinedBehaviorSanitizer, the game is detected, a recorded playthrough replays to the end without errors, a completed `REVIEW.md`, and approval from maintainers |

A human answers for every engine, AI-written or not: the *responsible human* named in its `PROVENANCE.md`.

## Staying close to ScummVM

This fork only adds files and never edits upstream ones. Every day, a workflow merges ScummVM's `master` and rebuilds every AI engine against it. When upstream changes break an engine, it shows up within a day. Everything else (the engine API, backends, platforms) is plain ScummVM.

## Get started

- **Engines in this fork:** see [ENGINES-AI.md](../ENGINES-AI.md) for each engine's game, kind, status and responsible human.
- **Contributors:** read [README-AI.md](../README-AI.md) for the rules and the step-by-step process.
- **Coding agents:** read [CLAUDE.md](../CLAUDE.md).
- **Building and running ScummVM:** see the upstream [README](../README.md).

## License

GPLv3 or later, like ScummVM. See [COPYING](../COPYING).
