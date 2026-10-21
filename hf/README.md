---
license: cc-by-4.0
pretty_name: "Mafāhīm ontology"
language:
  - ar
  - tr
  - en
  - de
tags:
  - ontology
  - knowledge-graph
  - linked-data
  - rdf
  - owl
  - quran
  - tafsir
  - arabic
  - digital-humanities
size_categories:
  - n<1K
---

# Mafāhīm: Quranic concepts in classical tafsir (ontology v0.1.0)

Open ontology for classical Quran commentaries (tafsir). It links verse, work, text passage, interpretation, review status and concept, so every statement can be traced back to its source. Concepts such as taqwā, raḥma or tawakkul are modelled in their lived meaning, as the scholars explain them.

**This repository is a copy.** The maintained original is on GitHub: https://github.com/kuersatcifci/mafahim. Each version here has the same number as the GitHub release.

All 130 terms carry labels in Arabic, Turkish, English and German. Arabic labels marked with `skos:editorialNote` are unreviewed suggestions.

Version 0.1.0 contains the **ontology only**. The verse-level dataset follows after expert review.

## Files

- `mafahim.ttl` (Turtle, source)
- `mafahim.owl` (RDF/XML)
- `mafahim.jsonld` (JSON-LD)

## Load

```python
from huggingface_hub import hf_hub_download
import rdflib

path = hf_hub_download("kuersatcifci/mafahim", "mafahim.ttl", repo_type="dataset")
g = rdflib.Graph().parse(path)
print(len(g), "triples")
```

## License

CC BY 4.0. Extends SemanticTafsir (MIT).

Method and background: https://kuersatcifci.de
