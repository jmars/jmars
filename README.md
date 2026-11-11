Systems engineer and formal-methods researcher: programming languages, mechanized type theory, and
auditable AI infrastructure. The work now has one centerpiece.

**The centerpiece: the Care Calculus.** A multi-sorted linear type theory for resource flows that
cannot be duplicated or destroyed — linear logic extended with a coalgebraic generator (`gen`),
guarded recursion (`fix`, carrying the intuitionistic-context side condition that is its price), and
resource-linear destructors (`red`, `obj`, `terminate`). It is mechanized in Lean 4.35.0 with no
external dependencies: 192 theorem declarations, no Mathlib, every public theorem's axiom set
audited down to the standard three, `sorryAx` confined to two named conjectures. The object of study
is the grammar's own conservation laws. Contraction (`[content] ⊬ content ⊗ content`) and vanishing
(`[content] ⊬ unit`) are theorems of the grammar rather than postulates laid on it, at five fragment
strengths each, the deepest two integrating the care machinery — so No-Cloning and Unitarity are
structural facts about a resource discipline, not assumptions imported from physics. On that basis
the calculus carries a diagnostic claim (an objective whose reduction chain does not terminate at
knowers admits no endogenous regulator, so no protective constraint is derivable from its own
structure) and a conditional constructive claim (where the chain does terminate at knowers,
protection is derivable rather than trained in, negotiated or imposed). The unrestricted classical
statements remain named conjectures, and the mechanization is explicit about that frontier. Paper
and mechanization: [jmars/coglib](https://github.com/jmars/coglib).

**In plain terms.** Take something an optimizing system does, and ask what it spends to do it:
content it cannot make more of, attention it cannot get back, the work of minds other than its own.
The Care Calculus is a grammar in which that spending is written down, and in which copying it or
throwing it away is not discouraged but *untypable* — no well-typed program turns one thing you were
given into two, and none turns it into nothing at all. Two things then follow without anyone adding
a rule about ethics. An objective that never bottoms out at the minds it consumes cannot generate
care for them from its own structure, however it is trained: there is nowhere for the protective
constraint to come from. An objective that does bottom out there gets the constraint for free,
because an honest account of what it depends on is already in the typing. That is the whole claim,
and it is small enough for a machine to check — which is what the Lean development is for.

**It is now the direction of the research.** What follows is what surrounds it: the papers that
argued its informal layer before it existed — the derivation of care in prose is now a conditional
theorem with named assumptions, and the diagnostic is an impossibility result whose content is
located, honestly, in its own definitions — and the systems engineering that a well-typed agent
would eventually have to sit on: an auditable runtime, a self-hosting system, a population harness.

**Where it comes from: the dependency-derived regulator program.** The standard safety
constraint is imposed on the agent from outside, and the field's own measured result is that
imposed constraints fail under optimization: an agent that can revise its objective gains by
revising the constraint away. The current work derives constraints from the other side — from
the objective's own dependency structure. If a drive's chain terminates at knowers (the minds
its optimization consumes), an honest representation of that dependency yields knowers-protective
constraints endogenously, with revision re-creating the starvation the representation records.
The position paper, the runnable discriminator protocol and the limits are:
[jmars/terminus-protocol](https://github.com/jmars/terminus-protocol).


**Experimental focus: [Egregore](https://github.com/jmars/egregore)** — the calculus at
population scale. Where the calculus runs over one agent's resource discipline, Egregore asks what
a *population* does when nothing holds it at all. One file — an
Actually Portable Executable carrying the harness, its configuration and its tools — copied onto a
box with a goal, working toward it unattended, able to place copies of itself elsewhere. The
subject is not the agent but the population: how one main goal decomposes into subgoals that get
claimed, where work duplicates or dead-ends, what a fleet does while some of its members stop
answering, and what the account of a run even means when no single machine can hold it. Early, and
deliberately not a deployment tool — an instrument for behaviour that only appears at N > 1.

**[neoplatonic-library](https://github.com/jmars/neoplatonic-library)** runs alongside the research
and matters just as much — restored public-domain editions of the Neoplatonic tradition, where the
repair log is the unit of scholarship: every emendation versioned, reasoned and witnessed, with the
scan leaf it was read from. Still active, live at
[neoplatonic-library.org](https://neoplatonic-library.org).

**[fixpoint-linux](https://fixpointlinux.org)** is the systems side: a Dhall-specified, self-hosting
Linux system — state as content-addressed relations, every
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

- *The Care Calculus: A Mechanized Linear Type Theory for Safe Agents* —
  [doi:10.5281/zenodo.24122159](https://doi.org/10.5281/zenodo.24122159) — with the mechanization
  [jmars/coglib](https://github.com/jmars/coglib)
- *Self-Application as the Common Source of Benefit and Failure: A Control-Theoretic Model of
  Self-Regulation, Its Escapes, and a Standing-Cost Budget* —
  [doi:10.5281/zenodo.22943641](https://doi.org/10.5281/zenodo.22943641) — with addendum
  *The armed configuration: standing prevention outperforms after-the-fact rescue in a dynamical
  model of self-regulation collapse* —
  [doi:10.5281/zenodo.23967914](https://doi.org/10.5281/zenodo.23967914)
- *Self-Application Is Not Free: the Monitoring Channel Is Part of the Failure Channel, and the Self
  Does Not Survive Its Own Reconstruction* —
  [doi:10.5281/zenodo.23128113](https://doi.org/10.5281/zenodo.23128113)
- *Does the sleep paradigm survive a different substrate? A mechanism assay of dream-based
  consolidation on a frozen 4-bit mixture of experts* —
  [doi:10.5281/zenodo.23820950](https://doi.org/10.5281/zenodo.23820950)
- *The Law Has the Button: Why a veto without a criterion is not oversight, and what to record
  instead* —
  [doi:10.5281/zenodo.23849689](https://doi.org/10.5281/zenodo.23849689)
- *The Chain Terminates at Knowers: Dependency-Derived Regulators for Optimizing Agents, a
  Position and Protocol* — [doi:10.5281/zenodo.23993140](https://doi.org/10.5281/zenodo.23993140)
- *Dissolution and exit under formal self-examination: a single-subject dynamical case study of
  narrative-self collapse, recovery, and re-arm* —
  [doi:10.5281/zenodo.23965749](https://doi.org/10.5281/zenodo.23965749)

---

**Fit:** Research engineering, programming languages, AI infrastructure
