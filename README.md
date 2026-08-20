# ADMET properties prediction

Profiles a compound across 41 ADMET endpoints in one pass, spanning absorption, distribution, metabolism, excretion and toxicity. ADMET-AI, from Swanson and colleagues, fits an ensemble of five Chemprop models augmented with RDKit descriptors to the ADMET benchmark group of the Therapeutics Data Commons, of which 31 tasks are classification and 10 regression. Speed was the design goal, making it practical to profile entire virtual libraries, though each endpoint inherits the size and quality of its source dataset.

This model was incorporated on 2025-06-17.Last packaged on 2026-07-06.

## Information
### Identifiers
- **Ersilia Identifier:** `eos7m30`
- **Slug:** `admet-ai-exact`

### Domain
- **Task:** `Annotation`
- **Subtask:** `Property calculation or prediction`
- **Biomedical Area:** `ADMET`
- **Target Organism:** `Homo sapiens`
- **Tags:** `ADME`, `Toxicity`

### Input
- **Input:** `Compound`
- **Input Dimension:** `1`

### Output
- **Output Dimension:** `49`
- **Output Consistency:** `Fixed`
- **Interpretation:** Predictions across 41 ADMET endpoints, combining classification probabilities and regression values.

Below are the **Output Columns** of the model:
| Name | Type | Direction | Description |
|------|------|-----------|-------------|
| molecular_weight | float | high | Physicochemical property for molecular weight |
| logp | float | low | Physicochemical property for logarithm of partition coefficient (logP) |
| hydrogen_bond_acceptors | integer | high | Physicochemical property for the number of hydrogen bond acceptors |
| hydrogen_bond_donors | integer | high | Physicochemical property for the number of hydrogen bond donors |
| lipinski | integer | high | Compliance with Lipinski's rule of five (out of 4) |
| qed | float | high | Quantitative estimate of drug-likeness (0-1) |
| stereo_centers | integer | high | Physicochemical property for the number of stereocenters |
| tpsa | float | high | Physicochemical property for topological polar surface area (TPSA) in squared Angstroms |
| ames | float | high | Predicted probability of Ames mutagenicity |
| bbb_martins | float | high | Predicted probability of blood-brain barrier penetration |

_10 of 49 columns are shown_
### Source and Deployment
- **Source:** `Local`
- **Source Type:** `External`
- **DockerHub**: [https://hub.docker.com/r/ersiliaos/eos7m30](https://hub.docker.com/r/ersiliaos/eos7m30)
- **Docker Architecture:** `AMD64`, `ARM64`
- **S3 Storage**: [https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos7m30.zip](https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos7m30.zip)

### Resource Consumption
- **Model Size (Mb):** `1`
- **Environment Size (Mb):** `6050`
- **Image Size (Mb):** `6023.19`

**Computational Performance (seconds):**
- 10 inputs: `35.95`
- 100 inputs: `27.61`
- 10000 inputs: `331.75`

### References
- **Source Code**: [https://github.com/swansonk14/admet_ai](https://github.com/swansonk14/admet_ai)
- **Publication**: [https://doi.org/10.1093/bioinformatics/btae416](https://doi.org/10.1093/bioinformatics/btae416)
- **Publication Type:** `Peer reviewed`
- **Publication Year:** `2024`
- **Ersilia Contributor:** [GemmaTuron](https://github.com/GemmaTuron)

### License
This package is licensed under a [GPL-3.0](https://github.com/ersilia-os/ersilia/blob/master/LICENSE) license. The model contained within this package is licensed under a [MIT](LICENSE) license.

**Notice**: Ersilia grants access to models _as is_, directly from the original authors, please refer to the original code repository and/or publication if you use the model in your research.


## Use
To use this model locally, you need to have the [Ersilia CLI](https://github.com/ersilia-os/ersilia) installed.
The model can be **fetched** using the following command:
```bash
# fetch model from the Ersilia Model Hub
ersilia fetch eos7m30
```
Then, you can **serve**, **run** and **close** the model as follows:
```bash
# serve the model
ersilia serve eos7m30
# generate an example file
ersilia example -n 3 -f my_input.csv
# run the model
ersilia run -i my_input.csv -o my_output.csv
# close the model
ersilia close
```

## About Ersilia
The [Ersilia Open Source Initiative](https://ersilia.io) is a tech non-profit organization fueling sustainable research in the Global South.
Please [cite](https://github.com/ersilia-os/ersilia/blob/master/CITATION.cff) the Ersilia Model Hub if you've found this model to be useful. Always [let us know](https://github.com/ersilia-os/ersilia/issues) if you experience any issues while trying to run it.
If you want to contribute to our mission, consider [donating](https://www.ersilia.io/donate) to Ersilia!
