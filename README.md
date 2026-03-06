# PRL-logic-lean4

Lean 4 formalisation of the core semantic results in:

> **Processual-Relational Logic: Syntax, Semantics, and Completeness for a Process Ontology**
> Luciano Floridi (Yale University)

## Overview

Processual-Relational Logic (PRL) is a many-sorted first-order system whose models are process domains: algebraic structures in which processes are primitive, entities emerge as identity processes within the compositional structure, and properties are adverbial qualifications of processual conduct rather than monadic predicates borne by substances.

This repository contains a machine-verified formalisation (587 lines, zero `sorry`, compiled against Lean's Mathlib library) covering the algebraic and semantic core of PRL.

## What is verified

| Result | Paper reference | Status |
|--------|----------------|--------|
| PRL-prestructures and PRL-structures (axioms A1–A16) | Definitions 3.1–3.2 | ✓ Verified |
| Partiality Seam (all five parts) | Lemma 5.1 | ✓ Verified |
| Source/target are identity processes | Lemma 6.4 | ✓ Verified |
| Identity processes are seq-idempotent | Lemma 6.5 | ✓ Verified |
| Soundness (representative instances incl. A15, A16) | Theorem 4.1 | ✓ Verified |
| Category construction C_M | Definition 6.1, Theorem 6.1 | ✓ Verified |
| Yoneda-Roundabout Theorem | Theorem 7.2 | ✓ Via Mathlib |
| Dissolution Theorem | Theorem 7.3 | ✓ Verified |
| Small-model bound (5k + 1) | Theorem 7.4 | ✓ Verified |
| Decidability of entity-fragment | Theorem 7.5 | ✓ Bound verified |
| Supervenience of nominal on adverbial properties | Theorem 8.1 | ✓ Verified |
| Non-Reducibility Theorem (concrete counterexample) | Theorem 8.2 | ✓ Verified |

## What remains pen-and-paper

Four results are not formalised, for the reasons noted:

- **Strong completeness** (Theorem 5.1): requires a Henkin construction not yet built for PRL's axiom system in Lean 4/Mathlib.
- **Enrichment Lemma** (Lemma 5.6): requires Dedekind–MacNeille completion glue code.
- **Equivalence of prestructure- and structure-validity** (Theorem 5.2): depends on the Enrichment Lemma.
- **Monoidal representation** (Theorem 6.2): requires monoidal category infrastructure beyond what Mathlib currently provides for this application.

## Building

Requires Lean 4 and Mathlib. To build:

```bash
lake update
lake build
```

The first build will download and compile Mathlib, which may take some time.

## File structure

```
CPRL/
  Basic.lean       — the complete formalisation (587 lines)
Main.lean          — thin wrapper
lakefile.toml      — Lake build configuration
lean-toolchain     — Lean version pin
```

## Changelog

- **v1.0-submission**: Full axiom system A1–A16 (interchange and parallel absorption added), 587 lines, zero `sorry`. Corresponds to paper version 29.

## Licence

MIT

## Author

Luciano Floridi, Yale University
