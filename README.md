# From Connectome to Control

**A perturbation-tested computational model of neural circuit function and embodied sensorimotor behaviour.**

![Status](https://img.shields.io/badge/status-research%20design-blue)
![Field](https://img.shields.io/badge/field-computational%20neuroscience-6f42c1)
![Language](https://img.shields.io/badge/language-Python-3776ab)

> **Project status:** Research design and feasibility stage. This repository documents the proposed scientific programme and software architecture. It does not yet contain completed experiments, validated biological conclusions, or a working FlyGym integration.

## At a glance

| Item | Description |
|---|---|
| Project | From Connectome to Control |
| Researcher | Angelic Charles |
| Domain | Computational neuroscience, connectomics, neural dynamics and embodied modelling |
| Biological system | Drosophila melanogaster |
| Core methods | Connectome graph analysis, spiking neural networks, controlled perturbations and behavioural evaluation |
| Proposed simulation | Brian2; FlyGym / NeuroMechFly subject to feasibility |
| Primary outputs | Reproducible research paper or preprint; interactive research environment |
| Current phase | Research question, dataset and circuit feasibility |

## Layperson summary

A brain is not just a collection of neurons. It is a network of connected cells whose activity helps an animal sense the world and decide how to move.

This project asks how the wiring of a small part of a fruit fly's nervous system helps produce behaviour. We will use publicly available maps of neural connections to build a computer model, simulate its activity, and carefully alter selected connections or neurons. We will then investigate whether those changes affect the model's ability to perform a simple sensorimotor task.

The long-term goal is to make the experiments explorable: a visitor should be able to inspect a circuit, see simulated neural activity, apply a virtual perturbation, and compare the resulting measurements. The model is a scientific approximation, not a claim that we have recreated a living brain.

---

## 1. Why this project?

Connectomics provides increasingly detailed descriptions of anatomical neural connectivity. However, a wiring diagram alone does not explain how a circuit produces activity or contributes to behaviour. Bridging structure, dynamics and behaviour requires explicit models, carefully defined assumptions, and tests against independent evidence.

This project is designed around that bridge:

1. **Structure:** derive a documented, versioned graph representation from a public connectome resource.
2. **Dynamics:** construct a biologically motivated spiking-network model constrained by the selected circuit's connectivity.
3. **Intervention:** perturb neurons, connections or inputs using controlled experimental conditions.
4. **Function:** quantify changes in network activity and, if a defensible interface is available, sensorimotor performance in an embodied simulation.
5. **Reproducibility:** preserve data provenance, model parameters, seeds, analysis code and experiment configurations.

The project deliberately begins with a tractable, biologically interpretable circuit rather than attempting to simulate an entire fly brain. Circuit selection will be justified by anatomical coverage, annotation quality, published functional evidence, computational feasibility and a plausible route to measurable output.

### Layperson summary

A map of roads does not tell us exactly how traffic will behave. In a similar way, knowing which neurons connect does not automatically tell us what the brain circuit does. We will build a computer model, test how it behaves, and investigate what changes when parts of its wiring are disrupted.

## 2. Research question and objectives

### Primary research question

**How does the structural organisation of a biological neural circuit influence its functional robustness, and how do targeted disruptions to that circuit affect its ability to support sensorimotor behaviour?**

### Objectives

- Identify a Drosophila circuit with suitable public connectivity data and sufficient biological interpretation.
- Build a traceable data pipeline from source connectome records to an analysis-ready directed graph.
- Characterise circuit topology and compare it with appropriate network null models.
- Implement and validate a spiking neural network whose architecture is constrained by the selected connectome.
- Design controlled neuron-ablation, synaptic-perturbation and input-perturbation experiments.
- Quantify neural and, where feasible, behavioural effects using predefined metrics.
- Test sensitivity to modelling assumptions and parameter uncertainty.
- Deliver a reproducible codebase, technical report or manuscript, and interactive research visualisation.

### Layperson summary

We want to find out which parts of a neural circuit matter most, how its activity changes when connections are altered, and whether those changes affect a simple behaviour. We will compare our model with control networks so that we do not mistake an ordinary network effect for a special property of biological wiring.

## 3. Hypotheses

These are testable hypotheses, not established findings. They may be refined after the literature review and circuit feasibility assessment.

- **H1 — Structural organisation:** The selected connectome-derived network will exhibit measurable differences in network dynamics or perturbation response compared with appropriately constructed randomised networks.
- **H2 — Targeted versus random perturbation:** Some biologically or structurally targeted interventions will produce larger changes in predefined functional measures than degree-matched random interventions.
- **H3 — Circuit output and task performance:** Perturbations to pathways that are demonstrably relevant to the selected sensorimotor task will alter predefined behavioural measures in the coupled model.
- **H4 — Robustness to modelling assumptions:** The main qualitative conclusions will be assessed across plausible parameter ranges and alternative model assumptions rather than depending on one hand-selected parameter setting.

Null results, contradictory findings and failed integrations will be documented rather than hidden.

## 4. Scope and boundaries

### In scope

- A single, justified Drosophila circuit or circuit subnetwork for the first complete study.
- Publicly accessible connectome data and documented annotations.
- Directed, weighted graph analysis, with the meaning and limitations of each edge weight stated explicitly.
- Spiking neural simulation using a tractable model such as leaky integrate-and-fire (LIF).
- Controlled computational perturbations and network-level evaluation.
- A low-dimensional sensorimotor interface and embodied simulation if biological and software feasibility are established.
- Interactive visualisation of actual model outputs and experiment metadata.

### Out of scope for the initial study

- Reconstructing or simulating every neuron in the entire fly brain.
- Claiming a complete biological emulation.
- Treating anatomical synapse counts as direct measurements of functional synaptic efficacy.
- Inferring causal biological facts solely from in-silico interventions.
- Claiming behavioural validity without an explicit mapping, suitable baseline and external validation evidence.
- Training a large model simply to make the project appear more advanced.

### Layperson summary

The first version will study one manageable part of the nervous system. It will not try to recreate an entire animal's brain. We will only make claims that our data and experiments can support.

## 5. Biological system and dataset strategy

### Candidate resources

The initial feasibility review will compare:

- **FlyWire / Codex:** adult Drosophila brain connectome and associated annotations. Candidate snapshot to investigate: dataset version 783.
- **BANC:** a brain-and-nerve-cord connectome resource. Candidate snapshot to investigate: dataset version 888.
- **Published circuit datasets and supplementary data:** used where they provide clearer circuit-specific functional context or a more direct link to a behavioural task.

These are candidate resources, not a decision to merge datasets. Dataset versions, coordinate systems, annotation schemes, coverage and licensing/access terms must be checked at project start. The selected dataset and exact snapshot will be recorded in DATASETS.md.

### Circuit-selection criteria

Each candidate circuit will be scored against:

1. Biological interpretability and relevant primary literature.
2. Completeness and confidence of connectivity data.
3. Availability of neuron-type and neurotransmitter annotations.
4. Evidence connecting the circuit to sensory processing, motor output or a defined behaviour.
5. Feasibility of implementing a defensible input/output model.
6. Compatibility with available embodied-simulation interfaces.
7. Computational cost and reproducibility.

The first circuit will be selected only after this review. A circuit will not be chosen solely because it is visually impressive or easy to render.

### Data provenance

Every derived dataset should record:

- Source resource and citation.
- Dataset release or snapshot identifier.
- Retrieval date and retrieval method.
- Filtering and inclusion criteria.
- Neuron and synapse counts before and after filtering.
- Annotation fields used and missingness.
- Transformation steps and software versions.
- Checksums or stable identifiers where practical.

### Layperson summary

We will use existing scientific maps of fly neurons rather than inventing a brain map. Before choosing a section to study, we will check how complete and trustworthy its data are and whether scientists already understand enough about its role to test a meaningful question.

## 6. Methodology

### 6.1 Connectome ingestion and graph construction

Represent the selected circuit as a directed graph G = (V, E, W), where V is the set of included neurons, E is the set of directed connections, and W stores source-supported edge attributes such as synapse counts or other documented connectivity measures.

The graph pipeline will:

- Retrieve source records through documented interfaces.
- Apply a version-controlled inclusion and filtering specification.
- Preserve source identifiers and annotations.
- Validate directionality, duplicate handling and missing values.
- Export analysis-ready tables and graph objects.
- Generate a data audit report.

A synapse count may be used as an anatomical connectivity feature. It will not automatically be interpreted as a calibrated synaptic conductance or physiological efficacy.

**Layperson summary:** We turn the biological wiring map into a computer-readable network. Each neuron becomes a node and each documented connection becomes a directed edge. We keep track of where every piece of information came from.

### 6.2 Circuit topology and network analysis

Candidate measures include:

- In-degree and out-degree distributions.
- Weighted degree or strength, where edge weights have a defensible interpretation.
- Betweenness and other centrality measures, interpreted cautiously.
- Clustering and motif statistics.
- Community structure, if appropriate to the circuit.
- Path and reachability measures.
- Input/output connectivity profiles.

Biological-network statistics will be compared against suitable null models. At minimum, investigate degree-preserving randomisation where the graph representation permits it. Null-model construction and limitations will be documented.

**Layperson summary:** We examine how the network is organised. For example, we ask whether some neurons connect to many others, whether groups form, and whether the real circuit has patterns that are unusual compared with carefully shuffled networks.

### 6.3 Spiking neural dynamics

The initial model will use a tractable spiking-neuron formulation, with LIF as the baseline candidate.

A standard LIF membrane equation is:

    tau_m * dV_i/dt = -(V_i - V_rest) + R_m * I_i(t)

A neuron emits a spike when its membrane potential reaches threshold; the model then applies a reset and, if specified, a refractory period.

The implementation will document:

- Membrane time constants and voltage conventions.
- Threshold, reset and refractory parameters.
- Synaptic-current or conductance formulation.
- Excitatory/inhibitory sign conventions.
- Synaptic delays, if represented.
- Input encoding and stimulation protocol.
- Numerical integration method and time step.
- Parameter sources, calibration procedure and uncertainty.

The model will distinguish source-observed anatomical information from inferred physiological parameters. Where biological parameters are unavailable, they will be treated as assumptions or calibrated parameters, not measurements.

Potential extensions such as adaptive LIF or more detailed conductance-based models will be considered only if the baseline model cannot answer the research question.

**Layperson summary:** Neurons communicate through electrical events called spikes. We will simulate simplified versions of those events and connect the simulated cells according to the biological wiring map. The simplifications will be stated clearly.

### 6.4 Perturbation experiments

Planned intervention families:

- **Neuron ablation:** remove selected neurons from the simulated network.
- **Synaptic weakening or enhancement:** alter specified model connection parameters.
- **Input perturbation:** change the magnitude, timing or pattern of sensory drive.
- **Targeted versus random interventions:** compare selected nodes or edges with random controls matched on relevant properties.
- **Network null controls:** compare connectome-derived results with appropriately randomised networks.

Perturbation dose, selection rule, number of repetitions and random seeds will be pre-specified. The analysis will distinguish structural removal from functional silencing and from changes in model synaptic parameters.

**Layperson summary:** We will perform controlled virtual experiments. We can temporarily silence a neuron, weaken a connection or change the input to the network, then measure what changes. We will also run random interventions as controls.

### 6.5 Neural and behavioural evaluation

Neural outcomes may include:

- Firing-rate distributions.
- Population activity and temporal response.
- Spike-train synchrony, using a clearly specified statistic.
- Response latency.
- Stability or persistence of activity.
- Changes in network-level activity following perturbation.

Behavioural outcomes depend on the final circuit and task. Candidate metrics include:

- Task success or target acquisition rate.
- Navigation or tracking error.
- Movement stability.
- Response latency.
- Recovery following perturbation.

A behavioural metric will only be included if the model has a documented mapping from circuit output to the relevant control variable. We will not infer behaviour from neural activity without this interface.

**Layperson summary:** We measure what happens inside the simulated network and, if we can connect it reliably to a virtual animal, what happens to its movement. We decide how to measure success before running the final experiments.

### 6.6 Embodied simulation

FlyGym / NeuroMechFly is the candidate environment for a later integration stage. The integration is conditional on:

- A compatible current software release.
- A biologically and computationally defensible circuit-to-control mapping.
- A tractable sensorimotor task.
- Baseline performance that can be measured and reproduced.
- A clear separation between neural-model output and the simulator's built-in controllers or dynamics.

The initial embodied experiment should be deliberately small. If a valid neural-to-motor interface cannot be established, the project will still deliver a complete connectome and neural-dynamics study, and the limitation will be reported.

**Layperson summary:** Eventually, we want the simulated neurons to influence a virtual fly's actions. But we will only make that connection if we can explain exactly how the neural signals control the virtual body.

## 7. Experimental design and controls

| Condition | Intervention | Purpose |
|---|---|---|
| Baseline | Unmodified selected model | Reference performance |
| Random ablation | Randomly selected neuron removal | Control for generic network damage |
| Targeted ablation | Predefined structural or biological target selection | Test targeted vulnerability |
| Synaptic weakening | Reduce selected model connection parameters | Test sensitivity to connection strength |
| Synaptic enhancement | Increase selected model connection parameters | Test sensitivity to connection strength |
| Input perturbation | Alter sensory/input drive | Test response to changed conditions |
| Network null | Degree-preserving randomised network where feasible | Test dependence on biological topology |

### Statistical and computational controls

- Repeat stochastic experiments across multiple seeds.
- Report sample sizes and uncertainty intervals.
- Use effect sizes alongside significance tests.
- Correct for multiple comparisons when applicable.
- Keep calibration and evaluation data or conditions separate.
- Use parameter sweeps and sensitivity analysis.
- Conduct parameter-recovery tests on synthetic data where relevant.
- Test implementation invariants and deterministic cases.
- Preserve failed runs and exclusion reasons.
- Distinguish exploratory analyses from confirmatory tests.

Exact sample counts, perturbation levels and statistical tests will be selected after the circuit and model are specified. They should not be invented in advance of feasibility evidence.

### Layperson summary

One simulation is not enough. We will repeat experiments, compare them with fair controls, and check whether the results survive reasonable changes to our assumptions. This helps us avoid drawing a big conclusion from a lucky run.

## 8. Software architecture

The software will be modular so that data processing, neural simulation, perturbation experiments and visualisation can be tested independently.

    connectome-to-control/
    ├── README.md
    ├── PROJECT_PLAN.md
    ├── RESEARCH_PROTOCOL.md
    ├── METHODOLOGY.md
    ├── DATASETS.md
    ├── ARCHITECTURE.md
    ├── ROADMAP.md
    ├── REFERENCES.md
    ├── CITATION.cff
    ├── pyproject.toml
    ├── configs/
    ├── data/
    │   ├── raw/
    │   ├── processed/
    │   └── metadata/
    ├── src/
    │   └── connectome_to_control/
    │       ├── connectome/
    │       ├── circuit_analysis/
    │       ├── neural_simulation/
    │       ├── perturbations/
    │       ├── embodiment/
    │       └── evaluation/
    ├── experiments/
    ├── notebooks/
    ├── tests/
    ├── results/
    ├── paper/
    ├── dashboard/
    └── docs/

### Module responsibilities

| Module | Responsibility |
|---|---|
| connectome | Retrieval, provenance, filtering and graph construction |
| circuit_analysis | Topology, motifs, null models and circuit summaries |
| neural_simulation | Neuron models, synapses, input protocols and simulation |
| perturbations | Reproducible intervention definitions and execution |
| embodiment | Neural-to-control interface and FlyGym adapter |
| evaluation | Metrics, statistical analysis, comparisons and reports |

### Engineering standards

- Typed, documented Python APIs for reusable modules.
- Configuration-driven experiments rather than hidden notebook state.
- Unit tests for transformations and model components.
- Integration tests for end-to-end experiment paths.
- Fixed random seeds where reproducibility is expected.
- Explicit environment and dependency versions.
- Structured experiment logs and machine-readable outputs.
- No large raw datasets committed to Git.
- Dataset retrieval instructions and provenance metadata.
- Continuous integration for tests and basic quality checks.

### Layperson summary

The code is organised into separate components, each with one job. This makes it easier for another researcher to understand, test and reuse the work rather than having to decipher one enormous notebook.

## 9. Planned technical stack

| Area | Candidate technology | Use |
|---|---|---|
| Core language | Python | Data, modelling and analysis |
| Numerical computing | NumPy, SciPy, pandas | Arrays, scientific computation and tables |
| Graph analysis | NetworkX | Connectome graph operations |
| Neural simulation | Brian2 | Spiking neural network baseline |
| Machine learning | PyTorch, scikit-learn | Optional predictive analyses and model comparison |
| Embodied simulation | FlyGym / MuJoCo | Conditional virtual-body integration |
| Visualisation | Matplotlib, Plotly, Three.js | Static and interactive figures |
| API | FastAPI | Serving experiment data and controlled operations |
| Interface | React, TypeScript | Interactive research environment |
| Testing | pytest | Unit and integration tests |
| Experiment tracking | MLflow or lightweight structured manifests | Run metadata and comparisons |
| Version control | Git and GitHub | Code, review and reproducibility |

Dependencies will be selected and pinned after a minimal compatibility test. A GPU will be used only where benchmarks show a benefit; graph analysis and some spiking simulations may be CPU-bound.

## 10. Interactive research environment

The visualisation platform is a research interface, not a substitute for the scientific analysis.

Planned views:

1. **Circuit explorer:** inspect included neurons, edges, annotations and graph metrics.
2. **Network activity:** view spike raster plots, firing rates and population activity over time.
3. **Perturbation workbench:** choose a documented intervention and run or load a reproducible experiment.
4. **Comparison view:** compare baseline and intervention conditions using the same metrics and scales.
5. **Behaviour view:** display embodied simulation outputs only when the integration is validated.
6. **Experiment provenance:** expose configuration, dataset version, model parameters, random seed and software environment.

The interface should link each displayed result to its underlying experiment record and analysis code.

### Layperson summary

Visitors will be able to explore the network, watch the model's activity and compare what happens when a selected part is changed. The visual interface will show real outputs from the research code, not decorative or fabricated scientific data.

## 11. Cloud compute and resource strategy

The project will use a laptop for development and cloud compute for workloads that require additional memory or acceleration.

| Workload | Initial environment |
|---|---|
| Data inspection and small graph analysis | Local Python environment |
| Circuit extraction and graph processing | Local or cloud CPU, depending on memory |
| Small and medium Brian2 simulations | Benchmark local/cloud CPU |
| Repeated perturbation sweeps | Cloud CPU or GPU according to benchmark |
| ML extensions | Cloud GPU only if required |
| Interactive site | Static hosting plus lightweight API if needed |

A benchmark milestone will record runtime, peak memory and numerical consistency for representative workloads before scaling up. The project will avoid assuming that GPU acceleration is automatically beneficial.

## 12. Research outputs

### Scientific output

- A documented research protocol.
- A reproducible connectome-processing pipeline.
- A validated baseline neural model within the stated scope.
- Controlled perturbation experiments and statistical analysis.
- A technical manuscript or preprint if results warrant it.
- A transparent limitations and reproducibility statement.

### Engineering output

- Modular Python package.
- Automated tests and environment specification.
- Versioned experiment configurations.
- Machine-readable results and analysis figures.
- Interactive circuit and experiment explorer.
- Documentation for reproducing the main results.

### Communication output

- A concise technical demonstration video.
- A project page with a plain-language explanation.
- Research figures with accessible captions.
- A clear distinction between measured source data, model assumptions, simulation outputs and biological evidence.

## 13. Project roadmap

The estimated timeline is 7–9 months, subject to dataset access, circuit complexity and the feasibility of embodied integration.

| Phase | Estimated period | Deliverable |
|---|---|---|
| 1. Research feasibility | Month 1 | Literature review, dataset comparison, circuit choice and protocol |
| 2. Connectome pipeline | Month 2 | Versioned, tested graph extraction and audit report |
| 3. Neural model | Month 3 | Baseline spiking model and validation tests |
| 4. Perturbation study | Months 4–5 | Controlled experiment suite and analysis |
| 5. Embodied integration | Months 6–7 | Conditional neural-to-motor integration and evaluation |
| 6. Release | Months 8–9 | Manuscript/preprint draft, interactive platform and reproducibility package |

### Early milestone: first 6–8 weeks

The first public milestone should include:

- A concise literature review.
- A dataset feasibility report.
- A justified candidate circuit.
- A reproducible data-ingestion demonstration.
- A first graph analysis notebook or script.
- A refined research protocol.

This ensures the project produces a meaningful, reviewable result well before the full roadmap is complete.

## 14. Risks and mitigation

| Risk | Mitigation |
|---|---|
| Selected circuit lacks usable functional evidence | Compare candidate circuits before committing |
| Dataset annotations are incomplete | Record missingness and narrow claims |
| Anatomical weights are mistaken for physiology | Separate observed connectivity from inferred parameters |
| Model becomes too large | Start with a circuit-level model and benchmark scaling |
| Neural-to-motor mapping is unjustified | Make embodiment conditional; preserve a valid non-embodied study |
| Results depend on hand-tuned parameters | Sensitivity analysis, calibration/evaluation separation and recovery tests |
| Cloud compute is limited | Use sparse representations, smaller circuits and staged experiments |
| Visualisation outruns scientific validation | Only expose outputs linked to reproducible experiment records |
| Project scope expands excessively | Freeze the first research question and define explicit release milestones |

## 15. Reproducibility and research integrity

The project will follow these principles:

- Cite all datasets, software and scientific claims.
- Respect dataset access terms, licences and attribution requirements.
- Preserve dataset versions and retrieval provenance.
- Document every preprocessing and exclusion decision.
- Distinguish observed biological data from model assumptions.
- Distinguish simulation outcomes from biological observations.
- Report uncertainty, limitations and negative results.
- Avoid claiming causal biological conclusions from computational perturbations alone.
- Release code and experiment configurations where licensing permits.
- Do not publish sensitive or restricted source data.

## 16. Intended audience and applications

This project is designed to demonstrate skills relevant to:

- Computational neuroscience research groups.
- Connectomics and neural circuit modelling teams.
- Neuroscience and neuroengineering internships.
- Research software engineering roles.
- Machine learning for biological and neural data.
- Master's and PhD applications in computational neuroscience, neuroinformatics, cognitive science and related fields.
- Research fellowships that value independent, reproducible scientific work.

It is not designed around one employer or one admissions programme. The scientific core should stand independently, while the application narrative can emphasise the most relevant components for each opportunity.

## 17. References and starting points

The following resources are starting points for the feasibility review. Exact versions and relevant papers will be recorded in REFERENCES.md as the design is finalised.

- [FlyWire Codex](https://codex.flywire.ai/) — connectome exploration and dataset information.
- [FlyWire project](https://flywire.ai/) — project and data-resource context.
- [NeuroMechFly documentation](https://neuromechfly.org/) — neuromechanical simulation documentation.
- [FlyGym GitHub repository](https://github.com/NeLy-EPFL/flygym) — source code and current implementation.
- [Brian2 documentation](https://brian2.readthedocs.io/) — spiking neural network simulator.
- [NetworkX documentation](https://networkx.org/documentation/stable/) — graph analysis.
- [PyTorch documentation](https://pytorch.org/docs/stable/index.html) — machine learning framework.

A curated bibliography of primary literature on the selected circuit, connectome dataset, neural model and behavioural task will be added after circuit selection.

## 18. Project status and next actions

**Current status: research design / feasibility.**

- [ ] Review literature and identify candidate circuits.
- [ ] Compare FlyWire and BANC dataset suitability.
- [ ] Verify access, dataset versions, annotations and licences.
- [ ] Select one circuit and define inclusion criteria.
- [ ] Finalise hypotheses, metrics, controls and analysis plan.
- [ ] Set up the Python environment and repository tests.
- [ ] Implement the first reproducible connectome extraction.
- [ ] Establish a baseline neural model.
- [ ] Run and document perturbation experiments.
- [ ] Evaluate whether embodied integration is scientifically defensible.
- [ ] Build the interactive research environment.
- [ ] Prepare manuscript and public release.

### The immediate next step

**Do not start by building the dashboard.** Start with the literature and data feasibility review. The first decision is which circuit can support a meaningful, testable connection between anatomy, neural dynamics and a defined behaviour.

---

## Layperson summary: the whole project in one minute

We are building a computer-based research environment to study how the wiring of a fruit fly's nervous system helps support behaviour.

First, we use a public map of neurons and their connections. Next, we turn a selected part of that map into a mathematical network and simulate how neurons communicate. Then we perform controlled virtual experiments, changing selected neurons or connections and measuring the effects. If we can establish a scientifically sound connection to a virtual fly's movement, we will test whether those changes also affect its behaviour.

The result will be both a research study and an interactive tool that lets other people inspect the network, understand the experiments and reproduce the findings.

**The central idea:** move from a map of neural connections, to a model of neural activity, to testable predictions about behaviour.
