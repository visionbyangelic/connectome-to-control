# Project Plan: From Connectome to Control

## Purpose

This document is the working execution plan for the research programme described in README.md. It converts the broad concept into staged decisions and deliverables.

## Why this project exists

An anatomical connectome describes structural relationships between neurons, but structure alone does not establish neural dynamics or behavioural function. This project will construct a tractable, connectome-constrained model and use controlled computational interventions to study the relationship between network organisation, activity and a defined sensorimotor task.

**Layperson summary:** A wiring map is a starting point, not a complete explanation of how a nervous system works. This project turns a small part of that map into a model that can be tested.

## Target outcomes

1. A defensible and reproducible circuit-selection decision.
2. A documented connectome ingestion and graph-analysis pipeline.
3. A validated baseline spiking neural model within the selected scope.
4. Controlled perturbation experiments with suitable controls.
5. A behavioural or embodied extension only if a valid input/output mapping can be justified.
6. An interactive research environment linked to real experiment records.
7. A manuscript or preprint draft if the results warrant scientific dissemination.

## Work packages

### WP1 — Literature and feasibility

- Identify candidate Drosophila circuits.
- Review primary literature on anatomy, physiology and behaviour.
- Compare candidate connectome resources and snapshots.
- Check annotation completeness, access conditions and licensing.
- Score circuits using the criteria in DATASETS.md.
- Freeze the initial research question and protocol.

**Exit criterion:** one selected circuit, documented evidence base, known data limitations and a feasible first experiment.

### WP2 — Data engineering

- Build a reproducible retrieval workflow.
- Preserve source identifiers and metadata.
- Apply documented inclusion criteria.
- Validate graph directionality and duplicate handling.
- Generate a data audit and graph exports.

**Exit criterion:** another researcher can reproduce the analysis-ready graph from the documented source and configuration.

### WP3 — Neural model

- Implement the baseline LIF formulation.
- Specify synaptic sign, dynamics and delays.
- Define input protocols.
- Add unit and integration tests.
- Verify numerical behaviour on small controlled examples.
- Separate observed connectome features from inferred physiological parameters.

**Exit criterion:** baseline simulations are reproducible and pass documented model checks.

### WP4 — Perturbation study

- Define intervention-selection rules before final analysis.
- Implement neuron and synapse perturbations.
- Create random and network-null controls.
- Repeat stochastic experiments across seeds.
- Quantify neural outcomes and uncertainty.
- Run sensitivity and parameter-recovery checks where applicable.

**Exit criterion:** a complete experiment matrix, machine-readable outputs and a transparent analysis report.

### WP5 — Embodied extension

- Select a tractable task supported by circuit evidence.
- Define a low-dimensional neural-to-control interface.
- Verify compatibility with the selected FlyGym / NeuroMechFly release.
- Establish a simulator baseline.
- Integrate the model and compare baseline/perturbed behaviour.

**Exit criterion:** a reproducible integration with a defensible mapping and measurable task outcomes. If this cannot be achieved, document the limitation and retain the non-embodied research result.

### WP6 — Release and communication

- Prepare the manuscript.
- Build the interactive explorer.
- Link visualisations to experiment metadata.
- Record environment and dataset versions.
- Create a demonstration video and accessible project overview.
- Archive release artefacts and citation metadata.

**Exit criterion:** public release is reproducible, scientifically cautious and understandable to both technical and non-technical audiences.

## Decision gates

| Gate | Decision |
|---|---|
| G1 | Is there a circuit with sufficient anatomy, annotation and functional evidence? |
| G2 | Can its source data be retrieved and processed reproducibly? |
| G3 | Does the baseline neural model behave as specified? |
| G4 | Do perturbation experiments have appropriate controls and measurable outcomes? |
| G5 | Is an embodied mapping scientifically defensible and technically feasible? |
| G6 | Are results sufficiently complete and robust for public scientific communication? |

## Scope-control rules

- Do not expand to a whole-brain model during the first study.
- Do not build the full dashboard before the data and experiment pipeline works.
- Do not add deep learning unless it answers a defined scientific or engineering need.
- Do not claim a behavioural result without a validated mapping and baseline.
- Keep a working end-to-end path at every major milestone.

## Application strategy

For computational neuroscience employers, emphasise graph analysis, simulation, perturbation design and software quality. For academic programmes, emphasise the biological question, literature grounding, methodological reasoning and research independence. For fellowships, emphasise reproducibility, open science and the potential contribution to neuroscience.

**Layperson summary:** The project is split into manageable stages. Each stage has a clear test for whether it is finished. We only add complexity when the previous stage works.
