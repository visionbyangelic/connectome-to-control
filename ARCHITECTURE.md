# Software Architecture

## Design principles

- Modular scientific components with explicit interfaces.
- Configuration-driven runs.
- Provenance attached to derived data and experiment outputs.
- Separation of source observations, model assumptions and simulation results.
- Reproducible experiments and testable transformations.
- Visualisation consumes recorded outputs; it does not invent scientific results.

## System flow

    Public connectome source
             |
             v
    Retrieval + provenance
             |
             v
    Filtering + graph construction
             |
             v
    Circuit topology analysis
             |
             v
    Connectome-constrained neural model
             |
             v
    Baseline and perturbation experiments
             |
             v
    Neural evaluation
             |
       optional validated
       neural-control adapter
             |
             v
    Embodied simulation
             |
             v
    Metrics + experiment records
             |
             v
    Interactive research explorer

## Package responsibilities

### connectome

Source adapters, retrieval, metadata, validation, filtering and graph exports.

### circuit_analysis

Graph metrics, motif analysis, null models and circuit summaries.

### neural_simulation

Neuron and synapse model definitions, input protocols, simulation execution and output recording.

### perturbations

Typed intervention definitions, selection rules, random controls and experiment orchestration.

### embodiment

Optional adapter from model outputs to simulator control variables; simulator integration and behavioural measurement.

### evaluation

Metric computation, statistics, uncertainty summaries, plots and machine-readable reports.

## Configuration

Configurations should define:
- Dataset source and snapshot.
- Circuit inclusion criteria.
- Model parameters and units.
- Input protocol.
- Perturbation type and dose.
- Repetition count and random seeds.
- Evaluation metrics.
- Output location.

Avoid hard-coding experiment choices inside notebooks.

## Experiment record

Each run should create a structured record containing:
- Unique run ID.
- Git commit or code version.
- Dataset manifest identifier.
- Configuration snapshot.
- Environment/dependency versions.
- Random seed.
- Runtime and resource usage.
- Output artefact paths.
- Metrics and warnings.

## Interactive platform

The future platform may use:
- React and TypeScript for the user interface.
- Plotly and Three.js for visualisation.
- FastAPI for a controlled backend if live experiment execution is needed.
- Static result artefacts for initial release.

The initial interface should read precomputed, versioned experiment outputs. Running arbitrary expensive simulations from a public website is not part of the first release.

**Layperson summary:** The project is built like a set of connected but independent tools. One part reads the biological data, another analyses it, another simulates neurons, and another displays the results. This makes the work easier to test and reuse.
