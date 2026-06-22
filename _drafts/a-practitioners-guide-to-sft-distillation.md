---
layout: post
title: "A Practitioner's Guide to SFT Distillation"
---

*Draft outline — vendor-neutral, no proprietary specifics. Fill each section with
your own hard-won intuition; the "I shipped this and saw gains" conviction is what
makes it credible without needing to quote numbers.*

## Why distill instead of fine-tuning directly?

- When a strong teacher's outputs beat your available ground-truth labels.
- Cost/latency: a small student that inherits most of a large teacher's behavior.
- Coverage: the teacher fills gaps your human-labeled set never reaches.

## Choosing the teacher

- Capability headroom over the student — and where that headroom actually matters.
- The teacher's failure modes become the student's failure modes. Audit them first.
- Single teacher vs. ensemble / best-of-N sampling tradeoffs.

## Building the distillation set

- Prompt distribution: match production, not the benchmark.
- Filtering teacher outputs (rejection sampling, self-consistency, verifier models).
- Data mixing: distilled data + original SFT data, and why the ratio matters.
- Contamination and dedup against your eval sets.

## The failure modes nobody warns you about

- Mode collapse / loss of diversity in student outputs.
- Inheriting the teacher's confident-but-wrong patterns.
- Distribution shift between distillation prompts and real traffic.

## Evaluation pitfalls

- Why win-rate against the teacher is a trap.
- Holdout sets the teacher never touched.
- Measuring what you actually shipped for, not proxy metrics.

## What I'd do differently next time

- (Your retrospective.)
