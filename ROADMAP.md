# Development Roadmap

Estimated duration: 7–9 months. This is a planning estimate, not a deadline guarantee.

## Month 1 — Literature and feasibility

- Review candidate circuit literature.
- Compare FlyWire and BANC suitability.
- Audit annotations, access and licences.
- Select a circuit and task candidate.
- Refine hypotheses and metrics.

**Deliverable:** feasibility report and research protocol.

## Month 2 — Connectome pipeline

- Implement retrieval and provenance.
- Build filtering and graph construction.
- Add validation and data-audit reports.
- Produce first graph summaries.

**Deliverable:** reproducible circuit graph.

## Month 3 — Neural simulation baseline

- Implement LIF model.
- Specify synaptic dynamics and input.
- Add tests and numerical checks.
- Run baseline activity experiments.

**Deliverable:** validated baseline model within the selected scope.

## Months 4–5 — Perturbation experiments

- Implement intervention operators.
- Add random and network-null controls.
- Run repeated experiments.
- Quantify neural outcomes.
- Conduct sensitivity and recovery checks.

**Deliverable:** experiment matrix and analysis report.

## Months 6–7 — Embodied integration (conditional)

- Define a defensible sensorimotor task.
- Build neural-to-control adapter.
- Verify FlyGym version and compatibility.
- Establish simulator baseline.
- Evaluate baseline and perturbed behaviour.

**Deliverable:** reproducible embodied demonstration, or documented rationale for excluding embodiment.

## Months 8–9 — Publication and release

- Finalise analysis.
- Draft manuscript or preprint.
- Build interactive explorer.
- Link views to experiment provenance.
- Prepare demonstration video and project page.
- Archive release artefacts.

**Deliverable:** reproducible research and engineering release.

## First 6–8 weeks: minimum public milestone

1. Literature review.
2. Dataset comparison.
3. Candidate circuit decision.
4. Data access and retrieval pilot.
5. Graph extraction demonstration.
6. Refined protocol and risk register.

## Weekly work rhythm

- One literature/research question session.
- One implementation session.
- One validation/testing session.
- One short research log update.
- End each week with a reproducible artefact or a documented blocker.

## Scope rules

Do not build the full dashboard before the data and modelling pipeline works. Do not expand to whole-brain simulation. Do not force embodiment if the circuit-to-control mapping is not justified.

**Layperson summary:** This is the order in which the work should happen. The first useful result arrives in roughly six to eight weeks; the larger research and interactive release comes later.
