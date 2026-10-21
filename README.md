# Mafāhīm

**An open ontology for classical Quran commentaries (tafsir) and the concepts they explain.**

Version 0.1.0 · draft · [CC BY 4.0](LICENSE)

Mafāhīm describes how classical tafsir works can be made machine-readable verse by verse without losing who said what. Every statement is tied to its exact place in a work. Interpretations from different works are grouped by the question they answer. Concepts such as taqwā, raḥma or tawakkul are described in their lived meaning: what they mean in practice for a person, as the scholars explain it.

This release contains the **ontology only** (classes, properties and controlled lists in Arabic, Turkish, English and German). The dataset built on it follows after expert review.

## Model in six layers

| Layer | Main classes | Purpose |
|---|---|---|
| 1 Quran | `mfh:Sure`, `mfh:Vers`, `mfh:Versabschnitt` | Surah, verse, word range |
| 2 Work | `mfh:Werk`, `mfh:Tefsir`, `mfh:Ausgabe`, `mfh:Eintrag`, `mfh:Hasiye` | Work, digital edition, entry per verse range, gloss |
| 3 Content | `mfh:Einheit` | One statement with one function, anchored in the text |
| 4 Interpretation | `mfh:Frage`, `mfh:Deutung` | Questions on a passage and the interpretations that answer them |
| 5 Provenance and review | `mfh:Pruefstatus` | Suggested, reviewed or rejected, with PROV-O |
| 6 Concept | `mfh:Mafhum`, `mfh:Aspekt` | Concepts in their lived meaning, each aspect backed by a statement |

Controlled lists (SKOS): genre, school, unit type, stance, aspect type, topic area.

All 130 terms carry labels in Arabic, Turkish, English and German. Arabic labels marked with `skos:editorialNote "ar label: unreviewed suggestion"` are still awaiting review.

Core rules built into the model:
- No unit without a text anchor.
- No concept aspect without a supporting statement.
- Machine-suggested content keeps the status `mfh:pVorschlag` until a person reviews it.
- The school of a work (e.g. Sunni, Shia Imami) is always shown.

## Files

| File | Content |
|---|---|
| `ontology/mafahim.ttl` | Ontology in Turtle (source) |
| `ontology/mafahim.owl` | Same as RDF/XML |
| `ontology/mafahim.jsonld` | Same as JSON-LD |

Namespace: `https://w3id.org/mafahim/ontology#` (prefix `mfh`). The w3id redirect is being registered.

## Builds on

- [SemanticTafsir](https://github.com/talhaahmed884/SemanticTafsirKG) (MIT): base classes for verse and commentary
- [Quranic Universal Library (QUL)](https://qul.tarteel.ai/): verse and word numbering
- W3C standards: OWL, SKOS, PROV-O, Dublin Core

## Cite

See [`CITATION.cff`](CITATION.cff). A DOI follows with the first archived release.

## Feedback

Questions and suggestions are welcome as GitHub issues.

---

**Deutsch.** Mafāhīm ist eine offene Ontologie für klassische Koran-Kommentare (Tefsir). Sie verbindet Vers, Werk, Textstelle, Deutung, Prüfvermerk und Begriff, sodass jede Aussage auf ihre Quelle zurückführt. Version 0.1.0 enthält nur die Ontologie, der Datensatz folgt nach der Fachprüfung. Hintergrund und Methode: [kuersatcifci.de](https://kuersatcifci.de).

**Türkçe.** Mafāhīm, klasik tefsirler için açık bir ontolojidir. Âyet, eser, metin yeri, yorum, kontrol durumu ve kavramı birbirine bağlar; her ifade kaynağına kadar izlenebilir. 0.1.0 sürümü yalnızca ontolojiyi içerir, veri seti uzman kontrolünden sonra yayımlanacaktır.

---

Maintained by Kürşat Çifçi · [kuersatcifci.de](https://kuersatcifci.de) · [Hugging Face](https://huggingface.co/kuersatcifci)
