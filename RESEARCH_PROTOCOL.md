# Research Protocol

**Status:** Draft protocol. Final details depend on circuit selection and dataset feasibility.

## 1. Research question

How does the structural organisation of a selected Drosophila neural circuit influence its functional robustness, and how do targeted disruptions affect its ability to support a defined sensorimotor task?

## 2. Study design

A computational modelling study with:
- Connectome-derived directed graph construction.
- Graph-topology analysis.
- Connectome-constrained spiking neural simulation.
- Controlled computational perturbations.
- Network-null and random-intervention controls.
- Behavioural evaluation only if a defensible neural-to-control interface is established.

## 3. Hypotheses

- H1: Connectome-derived structure produces measurable differences in network dynamics or perturbation response compared with appropriate randomised controls.
- H2: Some targeted perturbations produce larger changes in predefined functional measures than degree-matched random interventions.
- H3: Perturbations to pathways relevant to the selected task change predefined task measures in the coupled model.
- H4: Main qualitative conclusions are not dependent on one narrow set of model parameters.

These are hypotheses, not assumed findings.

## 4. Experimental conditions

| Condition | Description |
|---|---|
| Baseline | Unmodified selected model |
| Random ablation | Random neuron removal using a documented sampling rule |
| Targeted ablation | Removal of predefined neurons selected by biological or graph criteria |
| Synaptic weakening | Reduction of specified model connection parameters |
| Synaptic enhancement | Increase of specified model connection parameters |
| Input perturbation | Controlled change to input amplitude, timing or pattern |
| Network null | Appropriate degree-preserving randomised graph |

The intervention dose, sampling method, repetition count and random seeds must be recorded in experiment configuration files.

## 5. Outcomes

### Neural outcomes

Potential primary/secondary outcomes include firing-rate distribution, population response, response latency, spike-train synchrony, activity persistence and network stability. Exact metrics will be chosen before confirmatory analysis.

### Behavioural outcomes

Only after circuit and task selection: task success, target acquisition, tracking/navigation error, movement stability, response latency and recovery.

Behavioural metrics require an explicit mapping between neural model output and simulator control variables.

## 6. Controls and validation

- Multiple random seeds for stochastic experiments.
- Random intervention controls matched on relevant network properties.
- Appropriate network null models.
- Baseline model checks and implementation tests.
- Calibration/evaluation separation.
- Parameter sensitivity analysis.
- Synthetic parameter-recovery tests where applicable.
- Effect sizes and uncertainty intervals.
- Multiple-comparison correction where relevant.
- Predefined inclusion and exclusion criteria.
- Retention of failed runs and exclusion reasons.

## 7. Analysis principles

- Distinguish exploratory analyses from confirmatory analyses.
- Do not select metrics after inspecting outcomes without labelling the analysis exploratory.
- Report null and negative results.
- Distinguish anatomical connectivity from physiological synaptic efficacy.
- Distinguish model perturbations from biological interventions.
- Avoid biological causal claims based only on in-silico outcomes.

## 8. Reproducibility record

Each run should store:
- Experiment identifier.
- Dataset and snapshot identifier.
- Circuit selection and filtering configuration.
- Model and parameter configuration.
- Intervention definition and dose.
- Random seed.
- Software environment.
- Start/end time and runtime.
- Output paths and metrics.
- Warnings, errors and exclusions.

## 9. Protocol amendments

Any change to the circuit, hypothesis, primary metric, intervention selection or analysis plan must be recorded with date, reason and whether it occurred before or after outcome inspection.

**Layperson summary:** This protocol is the project's rulebook. It states what we plan to test, what we will measure, which comparisons will keep the experiments fair, and how we will record decisions so the results can be checked.
