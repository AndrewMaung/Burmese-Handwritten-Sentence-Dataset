# Burmese Handwritten Sentence Dataset (BHSD)

![BHSD banner](BHSD_Banner.png)

The **Burmese Handwritten Sentence Dataset (BHSD)** is an open sentence-level handwriting dataset for Burmese optical character recognition (OCR), handwritten text recognition (HTR), error analysis, and research on low-resource scripts.

The complete dataset is hosted on Hugging Face:

**[Download BHSD from Hugging Face](https://huggingface.co/datasets/Drew2456/Burmese-Handwritten-Sentence-Dataset)**

> **BHSD would not have been possible without its volunteers.** Every handwritten image exists because a volunteer generously contributed their time, effort, and handwriting to support open Burmese-language research.

## Dataset at a Glance

| Collection | Contributors | Sentences per contributor | Images |
|---|---:|---:|---:|
| Core collection | 54 | 50 | 2,700 |
| Supplementary coverage collection | 10 | 15 | 150 |
| **Complete dataset** | **54 unique writers** | — | **2,850** |

All ten supplementary contributors are members of the original group of 54 writers. They do not represent ten additional writers.

## Sentence Categories

The core collection contains 50 prompts per writer:

| Category | Canonical labels | Count | Purpose |
|---|---|---:|---|
| Natural | `NAT_01`–`NAT_30` | 30 | Natural Burmese sentences |
| Rare | `RARE_01`–`RARE_10` | 10 | Less-common vocabulary, names, numbers, and mixed content |
| Nonce | `NONCE_01`–`NONCE_10` | 10 | Constructed Burmese-like words for recognition testing |

The supplementary collection contains 15 additional natural sentences with canonical labels `SUP_01`–`SUP_15`.

Core image filenames use forms such as `NAT01.png`, `RARE01.png`, and `NONCE01.png`. Supplementary images are named numerically from `1.png` to `15.png` inside each coverage folder. The machine-readable metadata connects these filenames to their canonical labels and Burmese reference text.

## Repository Purpose

This GitHub repository is the companion repository for BHSD. It contains documentation, citation information, scripts, notebooks, metadata examples, and a small number of sample images. The complete image collection is maintained on Hugging Face rather than duplicated here.

Suggested structure:

```text
BHSD/
├── README.md
├── LICENSE
├── CITATION.cff
├── requirements.txt
├── scripts/
├── notebooks/
├── metadata/
│   └── metadata_sample.csv
└── samples/
    └── example images
```

## Metadata

The complete Hugging Face release includes a `metadata.csv` file with one row per image:

| Column | Description |
|---|---|
| `writer_id` | Anonymous writer or coverage collection identifier |
| `file_name` | Relative path to the handwriting image |
| `label` | Canonical sentence label, such as `NAT_01` or `SUP_01` |
| `text` | Burmese reference text visible in the corresponding image |
| `category` | `NAT`, `RARE`, `NONCE`, or `SUP` |

The `Coverage1`–`Coverage10` values are collection identifiers. They should not be counted as additional unique writers.

## Loading the Dataset

After downloading the Hugging Face repository, the image directory can be loaded with the Hugging Face `datasets` library:

```python
from datasets import load_dataset

dataset = load_dataset(
    "imagefolder",
    data_dir="Burmese_Handwritten_Sentence_Dataset"
)
```

## Intended Uses

BHSD is intended for:

- Burmese OCR and handwritten text recognition research
- Sentence-level recognition baselines
- Character and grapheme coverage analysis
- Writer-independent evaluation
- Error analysis and robustness studies
- Low-resource language technology research

Users should avoid attempting to identify writers or using the data for handwriting-based identity profiling.

## Licence

BHSD is released under the [Creative Commons Attribution 4.0 International Licence (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). You may share and adapt the dataset, including for commercial purposes, provided that appropriate attribution is given and changes are indicated.

See [LICENSE](LICENSE) for the attribution notice and licence link.

## Citation

If you use BHSD, please cite the dataset. GitHub can generate a formatted citation from [CITATION.cff](CITATION.cff).

```bibtex
@dataset{oo_2026_bhsd,
  author    = {Oo, Ah Maung and DatarrX},
  title     = {Burmese Handwritten Sentence Dataset (BHSD)},
  year      = {2026},
  publisher = {Hugging Face},
  url       = {https://huggingface.co/datasets/Drew2456/Burmese-Handwritten-Sentence-Dataset}
}
```

## Acknowledgements

The deepest thanks go to all 54 volunteers who contributed their handwriting to BHSD. Their generosity, patience, and trust created every core and supplementary image in this release. This dataset could not exist without them, and users are asked to recognise and respect their contribution whenever BHSD is used or discussed.

**Special thanks to kalix.louiss.**

**Thank you to every volunteer, from Andrew and DatarrX.**

## Maintainer

**Ah Maung Oo**  
DatarrX — [datarrx.org](https://datarrx.org)
