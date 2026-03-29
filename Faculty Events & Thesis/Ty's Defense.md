Reproducibility at Scale

Provenance = Data Lineage + Execution History, or the history of how data was produced, and supports reproducabillity
Provenance-Aware storage systems (PASS), system level and doesn't capture workflow structure. 

Distributed preovenance on distributed environemtsn: execution arguements, start time and duration, execcution host, enviornment, stdout/stderr. 

Previous fine grained approach: encapsulates each component of the workflow intoo individual containers, and captures the workflow record trail (provenance) at runtime. 
- leverage apptainer containers
- develop apptainer plugin for custom build and runtime enviornment

Monoloithic Container Architectures: creates an opaque execution path: hides internal execution steps. 

- I would like to see more figures

Capturing Metadata

Data (dynamic and static md) -> app (plugin) -> data 

Originally, this was for building and executing locally, and you need to do manual build runs. 

**Hypothesis**: Fine-grained containerized workflow environments can be extended to support arbitrary multi-layer DAG workflows and distributed execution. 

Approach: multi-layer DAG support: automate workflow builds and local execution. 
Pegasus Execution: Leverage pegasus to submit fine grained containzered workflows for distributed execution. Distributed provenance can go with any distributed job. Dynamicity, img container format. 

Low quality image on "tested-scenario"

Using an IMG format reduced .img size by about 60%. 

Motivation, Background & Related Work, Research Questions & hypothesis / Methodology / Results / Conclusion