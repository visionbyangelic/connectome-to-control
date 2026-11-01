# Methodology

This is the technical methodology specification. It will be updated as the circuit, data release and model are selected.

## 1. Data model

Represent the selected circuit as a directed graph G = (V, E, W).

- V: included neurons.
- E: directed connections.
- W: source-supported edge attributes and documented derived features.

Preserve source IDs and annotations. Do not collapse distinct biological attributes into a single generic weight without justification.

### Data validation

- Validate unique neuron identifiers.
- Check edge endpoints against included nodes.
- Preserve directionality.
- Detect duplicate records and define aggregation rules.
- Audit missing annotations.
- Record filtering counts and exclusions.
- Store dataset snapshot and retrieval metadata.

## 2. Graph analysis

Candidate measures:
- In-degree and out-degree.
- Weighted degree/strength where meaningful.
- Betweenness and other centrality measures.
- Clustering and motif statistics.
- Community structure where justified.
- Reachability and input/output profiles.

Compare observed measures with null models appropriate to the graph and question. Degree-preserving randomisation is a candidate, not an automatic solution; constraints and limitations must be documented.

## 3. Neural model

Baseline candidate: leaky integrate-and-fire (LIF).

    tau_m * dV_i/dt = -(V_i - V_rest) + R_m * I_i(t)

Document:
- State variables and units.
- Membrane time constant.
- Resting, threshold and reset potentials.
- Refractory period.
- Synaptic-current or conductance formulation.
- Excitatory/inhibitory sign conventions.
- Delay assumptions.
- Input protocol.
- Numerical integration method and time step.

Anatomical synapse counts are not assumed to be functional weights. Model parameters must be sourced, estimated, calibrated or explicitly labelled as assumptions.

## 4. Perturbation operators

Define interventions as explicit, serialisable objects:
- Neuron removal.
- Functional silencing.
- Edge parameter scaling.
- Input amplitude/timing changes.
- Random matched intervention.
- Network-null replacement.

Keep structural deletion distinct from functional silencing and from parameter scaling.

## 5. Evaluation

Potential neural metrics:
- Firing-rate summaries.
- Population activity.
- Response latency.
- Spike-train synchrony.
- Activity persistence and stability.

Potential behavioural metrics, conditional on a valid embodiment:
- Task success.
- Tracking error.
- Movement stability.
- Response latency.
- Recovery.

Use effect sizes, uncertainty intervals and repeated seeds. Select primary metrics before confirmatory experiments.

## 6. Embodiment interface

The neural-to-control adapter must specify:
- Which neural population or signal is read.
- How signals are transformed into control variables.
- Temporal sampling and latency.
- Scaling and clipping.
- Whether the mapping is biologically motivated, engineered or both.
- How the simulator's native controllers are disabled or accounted for.

Do not present an engineered mapping as a discovered biological pathway.

## 7. Validation

- Unit tests for graph transformations and model components.
- Small analytically tractable simulation tests.
- Numerical convergence or time-step sensitivity checks where relevant.
- Parameter recovery on synthetic data where applicable.
- Baseline and control comparisons.
- End-to-end reproducibility from configuration to results.

**Layperson summary:** This document explains how the research will be carried out in enough detail for another technical person to understand the data, equations, assumptions, experiments and validation checks.
