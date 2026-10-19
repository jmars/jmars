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
| **the language** | **[osier](https://github.com/jmars/osier)** | The language the agent authors components *in*. Elm-Descendant, Branch-local row refinement for extensible records via GADTs (λρG) — a row equation never escapes its branch while a type equation coerces at the branch result. Osier→QBE compiler, self-hosting, 90 Lean theorems with 3 explicit axioms and zero `sorry` |
| **the engine** | **[aubier](https://github.com/jmars/aubier)** | The Mixture-of-Experts execution layer it all runs on: split each layer's experts by *where their weights live*, compute the parts concurrently on the devices that hold them, and sum — one code path from a single card (GPU hits, CPU misses, both at once) up to N devices. Carried as a fork of `llama.cpp`, where the per-layer hit/miss split is currently inexpressible. |
| **the weights** | **[taillis](https://github.com/jmars/taillis)** | What the weights *are*: per-expert quantization, so that a layer's 128 experts stop sharing one type because the file carries one type per tensor. Experts are grouped by measured routing hotness, each group carrying its own type, and each group arrives at the engine as a store it already knows how to compute and sum. It is a **residency** lever as much as a fidelity one — every byte off the expert set moves the engine's CPU/GPU split point — which is why it runs beside the engine work rather than after it. Mistral Small 4 is the only target. |
| **the machine** | **[souche](https://github.com/jmars/souche)** | The emulator the agent's machine runs in: a native C port of v86 — the CPU core and the devices, an interpreter, a decoded-block cache and an x86-64 JIT, each generated from the reference's own instruction table and gated against it by byte-identical machine-state transcripts. cosmocc makes it one executable on amd64 and aarch64, so the same guest image boots anywhere. Roughly 7× the interpreter it started as. |

The two axes are sequenced deliberately: the environment axis is where the judge exists, so the
weights axis waits on it. (What the weights *are* does not wait — that is **taillis**, and the engine
needs it to run the weights at all.) Weight *improvement* is **on-policy distillation** — student
rollouts under dense supervision from a teacher
([arXiv:2609.04172](https://arxiv.org/abs/2609.04172)), deferred until the harness is mostly done,
because a change the store cannot describe is a change nobody can audit.

**Experimental focus: [Egregore](https://github.com/jmars/egregore)** — the same question asked
outside the machine. Futaie asks what one agent does to its own system while the record is held
outside it; Egregore asks what a *population* does when nothing holds it at all. One file — an
Actually Portable Executable carrying the harness, its configuration and its tools — copied onto a
box with a goal, working toward it unattended, able to place copies of itself elsewhere. The
subject is not the agent but the population: how one main goal decomposes into subgoals that get
claimed, where work duplicates or dead-ends, what a fleet does while some of its members stop
answering, and what the account of a run even means when no single machine can hold it. Early, and
deliberately not a deployment tool — an instrument for behaviour that only appears at N > 1.

**[neoplatonic-library](https://github.com/jmars/neoplatonic-library)** runs alongside it and matters
just as much — restored public-domain editions of the Neoplatonic tradition, where the repair log is
the unit of scholarship: every emendation versioned, reasoned and witnessed, with the scan leaf it
was read from. Still active, live at [neoplatonic-library.org](https://neoplatonic-library.org).

**[fixpoint-linux](https://fixpointlinux.org)** is the systems side, and the ground the harness comes
from: a Dhall-specified, self-hosting Linux system — state as content-addressed relations, every
command able to show its own derivation, boot as a verdict. Bootable in the browser at the site.

---

## Other work

**[datalog-dafsa](https://github.com/jmars/datalog-dafsa)** — Datalog engine in Zig. Facts stored as
a minimal-acyclic DAFSA, rules compiled to a semi-naive fixpoint VM, reads served from mmap'd
snapshots. 306 tests green; hybrid lexical ∩ semantic search on top.

**[logical-english](https://github.com/jmars/logical-english)** — Kowalski's Logical English compiled
to Datalog — and back. A bidirectional bridge: controlled natural language in, logic programs out,
derived facts readable again as English.

---

## Papers

- *Self-Application as the Common Source of Benefit and Failure: A Control-Theoretic Model of
  Self-Regulation, Its Escapes, and a Standing-Cost Budget* —
  [doi:10.5281/zenodo.22943641](https://doi.org/10.5281/zenodo.22943641)
- *Self-Application Is Not Free: the Monitoring Channel Is Part of the Failure Channel, and the Self
  Does Not Survive Its Own Reconstruction* —
  [doi:10.5281/zenodo.23128113](https://doi.org/10.5281/zenodo.23128113)

---

**Fit:** Research engineering, programming languages, AI infrastructure
