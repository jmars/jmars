### Everything is a fixpoint if you squint. Below are the ones that run. 🌀

I build systems that apply to themselves: a logic engine whose semantics is a least fixpoint, a
language whose soundness argument is mechanized beside its source, papers whose every number is
re-derivable from the committed artifact, and a library where every editorial decision is witnessed
by the scan leaf it was read from.

Self-application is the theme. **Reproducibility is the discipline**: pre-registrations before the
run, claim audits after, evidence deposits for everything.

---

## The programme

One idea, in four registers:

| | |
|---|---|
| **Engines** | compute the fixpoint, serve it from a snapshot. |
| **Languages** | let the machine read what you wrote. |
| **Mechanization** | don't assert it; prove it beside the code. |
| **Evidence** | every claim ships with the artifact that produced it. |

---

## Flagship work

**[datalog-dafsa](https://github.com/jmars/datalog-dafsa)** — Datalog engine in Zig. Facts stored as
a minimal-acyclic DAFSA, rules compiled to a semi-naive fixpoint VM, reads served from mmap'd
snapshots. 306 tests green; hybrid lexical ∩ semantic search on top.

**[osier](https://github.com/jmars/osier)** — A language with branch-local row refinement for
extensible records via GADTs — Elm→ZINC compiler, CEK effect host in Zig, Lean 4 mechanization, and a
one-command evidence chain (`osier-numbers.sh`) that reproduces the paper's numbers from a clean
clone.

**[logical-english](https://github.com/jmars/logical-english)** — Kowalski's Logical English compiled
to Datalog — and back. A bidirectional bridge: controlled natural language in, logic programs out,
derived facts readable again as English.

**[selfreg-public](https://github.com/jmars/selfreg-public)** ·
**[dpdr-public](https://github.com/jmars/dpdr-public)** — Three deposited papers: a control-theoretic
model of self-regulation; self-application is not free — the monitoring channel is part of the
failure channel; applied to a working agent, pre-registered, with a held-out task suite and sealed
tests.

**[ouroboros](https://github.com/jmars/ouroboros)** — A metacircular JavaScript engine: a restricted
subset of JS bootstrapping a TDOP parser and interpreter, climbing toward
meta-vm-executing-meta-vm.

**[neoplatonic-library](https://github.com/jmars/neoplatonic-library)** — Restored public-domain
editions of the Neoplatonic tradition, where the repair log is the unit of scholarship: every
emendation versioned, reasoned, and witnessed. Live at
[neoplatonic-library.org](https://neoplatonic-library.org).

---

## Papers

- *Self-Application as the Common Source of Benefit and Failure: A Control-Theoretic Model of
  Self-Regulation, Its Escapes, and a Standing-Cost Budget* —
  [doi:10.5281/zenodo.22943641](https://doi.org/10.5281/zenodo.22943641)
- *Self-Application Is Not Free: the Monitoring Channel Is Part of the Failure Channel, and the Self
  Does Not Survive Its Own Reconstruction* —
  [doi:10.5281/zenodo.23128113](https://doi.org/10.5281/zenodo.23128113)

---

## Around the workshop

Static Zig MCP client (`mcpc`), FST-based full-text indexer in Rust (`fst-indexer`), sandbox servers
on pledge/seccomp/landlock, persistent knowledge-graph MCPs, and the Palimpsest intelligence toolkit
they belong to.

---

## Elsewhere

- [blog.jaye.ch](https://blog.jaye.ch) — plain-language companion to the self-application papers
- [fixpointlinux.org](https://fixpointlinux.org) — the systems side
- [neoplatonic-library.org](https://neoplatonic-library.org) — the tradition side

---

**Fit:** Research engineering, programming languages, AI infrastructure — roles where the hard
problem is the point, and the artifact has to run.

The status emoji is a cyclone: a loop with no visible entry. This is not an accident.
