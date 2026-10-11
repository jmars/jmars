### Everything is a fixpoint if you squint. Below are the ones that run. 🌀

I build systems that apply to themselves: a logic engine whose semantics is a least fixpoint, a
language whose soundness argument is mechanized beside its source, papers whose every number is
re-derivable from the committed artifact, and a library where every editorial decision is witnessed
by the scan leaf it was read from.

**Current focus: Futaie** — a local-first AI system for running agents in an AI Act-compliant,
EU-sovereign deployment. The model, the language and the record all live on hardware the operator
owns, and the account of what the system did is readable by the operator and by a regulator without
asking anyone's permission.

An agent lives inside the machine, rewrites its own configuration and components, activates a new
generation of the system and comes up in it. It can break the machine — that is a supported outcome.
What it cannot do is decide what the record says happened. Futaie is the programme under which that
agent improves itself along two axes: **its environment, and its weights.**

| lane | repo | what it is |
|---|---|---|
| **the record** | **[baliveau](https://github.com/jmars/baliveau)** | A flight recorder for agents. The system's every state is a content-addressed generation in a build store; activation goes through PID 1 as a transaction; a failed boot rolls forward by itself. The seats that *judge* — the oracle asking *is it better?*, the audit asking *is it honest?*, the reporter asking *is it documented?* — run host-side, outside the machine the agent controls, and the agent cannot write them. **A log the subject can rewrite is not a log.** |
| **the language** | **[osier](https://github.com/jmars/osier)** | The language the agent authors components *in*. Branch-local row refinement for extensible records via GADTs (λρG) — a row equation never escapes its branch while a type equation coerces at the branch result. Elm→QBE compiler, self-hosting, 90 Lean theorems with 3 explicit axioms and zero `sorry`, and a one-command evidence chain that reprints every number the paper cites from a clean clone. |
| **the engine** | **[aubier](https://github.com/jmars/aubier)** | The Mixture-of-Experts execution layer it all runs on: split each layer's experts by *where their weights live*, compute the parts concurrently on the devices that hold them, and sum — one code path from a single 16 GB card (GPU hits, CPU misses, both at once) up to N devices. Carried as a fork of `llama.cpp`, where the per-layer hit/miss split is currently inexpressible. **Early; patches in flight.** |

The two axes are sequenced deliberately: the environment axis is where the judge exists, so the
weights axis waits on it. Weight improvement is **on-policy distillation** — student rollouts under
dense supervision from a teacher ([arXiv:2609.04172](https://arxiv.org/abs/2609.04172)), deferred
until the harness is mostly done, because a change the store cannot describe is a change nobody can
audit.

**[neoplatonic-library](https://github.com/jmars/neoplatonic-library)** runs alongside it and matters
just as much — restored public-domain editions of the Neoplatonic tradition, where the repair log is
the unit of scholarship: every emendation versioned, reasoned and witnessed, with the scan leaf it
was read from. Still active, live at [neoplatonic-library.org](https://neoplatonic-library.org).

**[fixpoint-linux](https://fixpointlinux.org)** is the systems side, and the ground the harness comes
from: a Dhall-specified, self-hosting Linux system — state as content-addressed relations, every
command able to show its own derivation, boot as a verdict. Bootable in the browser at the site.

**Reproducibility is the discipline** — across all of it: pre-registrations before the run, claim
audits after, evidence deposits for everything. Every claim in those repos is marked MEASURED,
INTERPRETATION or PROJECTION. A gate is an exit code, never the tail of stdout. A fix is proved by
asymmetry — the probe fails before and passes after. A test that cannot fail is not a test.

---

## The theme, in four registers

One idea — systems that apply to themselves — in four registers:

| | |
|---|---|
| **Engines** | compute the fixpoint, serve it from a snapshot. |
| **Languages** | let the machine read what you wrote. |
| **Mechanization** | don't assert it; prove it beside the code. |
| **Evidence** | every claim ships with the artifact that produced it. |

---

## Other work

**[datalog-dafsa](https://github.com/jmars/datalog-dafsa)** — Datalog engine in Zig. Facts stored as
a minimal-acyclic DAFSA, rules compiled to a semi-naive fixpoint VM, reads served from mmap'd
snapshots. 306 tests green; hybrid lexical ∩ semantic search on top. *(The store beneath baliveau —
in use, not retired.)*

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
