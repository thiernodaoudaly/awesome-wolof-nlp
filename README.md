# awesome-wolof-nlp [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources for Natural Language Processing (NLP) in Wolof and related West African languages.

Wolof is spoken by approximately 10 million people, primarily in Senegal, Gambia, and Mauritania. Despite this, NLP resources remain very scarce. This repo catalogs everything that exists — datasets, models, tools, papers — with comments to help you choose the right resource for your use case.

**Contributions welcome!** See [CONTRIBUTING.md](#contributing).

---

## Contents

- [Datasets](#datasets)
- [Models & Embeddings](#models--embeddings)
- [Tools](#tools)
- [Papers & Research](#papers--research)
- [Groups & Labs](#groups--labs)
- [Related Languages](#related-languages)
- [General African NLP Resources](#general-african-nlp-resources)

---

## Datasets

### Parallel Corpora

- **[JW300](https://opus.nlpl.eu/JW300.php)** — Wolof–French parallel corpus extracted from religious publications. ~300k aligned sentences. Good lexical coverage, but register is formal and thematically narrow (religion). Widely used as a baseline.

- **[FLORES-200](https://github.com/facebookresearch/flores)** — Meta's multilingual benchmark including Wolof (code `wol`). 1,012 sentences translated from English. Ideal for evaluating translation models, but too small for training.

- **[OPUS Wolof](https://opus.nlpl.eu/)** — Aggregator of parallel corpora. Search `wol` to browse all available language pairs (Wolof–EN, Wolof–FR, etc.). Quality varies by source.

- **[Common Voice Wolof](https://commonvoice.mozilla.org/wo)** — Mozilla's crowdsourced audio corpus for speech recognition. A few hours of speech validated by native speakers. Still growing — **you can contribute!**

- **[Tatoeba Wolof](https://tatoeba.org/en/sentences/search?from=wol)** — Short collaboratively translated sentences. Low volume (~500 sentences) but clean, human-verified data.

### Monolingual Corpora

- **[Wolof Wikipedia](https://wo.wikipedia.org)** — ~1,400 articles. Small but useful for text mining. Downloadable via [Wikimedia Dumps](https://dumps.wikimedia.org/wowiki/).

- **[Leipzig Corpora Collection – Wolof](https://wortschatz.uni-leipzig.de/en/download/Wolof)** — Monolingual corpus collected from the web (~100k sentences). Useful for language modeling.

### Lexicons & Dictionaries

- **[Panlex Wolof](https://panlex.org/)** — Multilingual lexical database including Wolof. Useful for building dictionaries or translation resources.

- **[Wolof CLDR Data (Unicode)](https://github.com/unicode-org/cldr)** — Unicode localization data including some Wolof entries (month names, country names, etc.).

---

## Models & Embeddings

- **[AfriBERTa](https://github.com/keleog/afriberta)** — Language model pre-trained on 11 African languages including Wolof. Based on XLM-R. The first truly multilingual African model. Good option for fine-tuning on classification or NER tasks.

- **[AfroXLMR](https://github.com/castorini/afro-xlmr)** — XLM-RoBERTa adapted to 17 African languages (Wolof included) via continued pre-training. Outperforms AfriBERTa on several benchmarks. **Recommended starting point.**

- **[MasakhaNER models](https://huggingface.co/masakhane)** — NER models trained on African languages. Wolof is not yet included, but the architecture and training scripts are directly reusable.

- **[NLLB-200 (Meta)](https://huggingface.co/facebook/nllb-200-distilled-600M)** — Meta's No Language Left Behind translation model supporting 200 languages including Wolof (`wol_Latn`). The 600M distilled version runs on CPU. **Best available Wolof translation model to date.**

- **[Helsinki-NLP Opus-MT](https://huggingface.co/Helsinki-NLP)** — Lightweight translation models based on MarianMT. Search `wol` for available language pairs. Older than NLLB but much lighter.

---

## Tools

### Tokenization & Preprocessing

- **[spaCy – generic tokenizer](https://spacy.io/usage/models)** — spaCy has no native Wolof model, but the generic tokenizer (`xx`) works reasonably well for Latin-script Wolof. The simplest starting point.

- **[SentencePiece](https://github.com/google/sentencepiece)** — Google's unsupervised tokenizer. Can be trained directly on raw Wolof text to build a custom vocabulary. Widely used with Transformer models.

- **[Morfessor](https://github.com/aalto-speech/morfessor)** — Unsupervised morphological segmentation. Relevant for Wolof given its agglutinative morphology.

### Evaluation

- **[sacrebleu](https://github.com/mjpost/sacrebleu)** — Standard tool for evaluating translation models (BLEU score). Supports Wolof via FLORES-200.

- **[MasakhaNEWS Benchmark](https://github.com/masakhane-io/masakhane-news)** — News classification benchmark for African languages. Wolof not yet included, but worth watching.

---

## Papers & Research

- **[MasakhaNER: Named Entity Recognition for African Languages (2021)](https://arxiv.org/abs/2103.11811)** — First large-scale NER resource for African languages. Wolof not included but the methodology is directly applicable. *Highly cited — a great entry point.*

- **[AfriBERTa: Exploring the Viability of Pretrained Multilingual Language Models for Low-resourced Languages (2021)](https://arxiv.org/abs/2111.11971)** — Evaluates several pre-training approaches on low-resource African languages including Wolof. *Essential reference for understanding the state of the art.*

- **[No Language Left Behind (NLLB, Meta 2022)](https://arxiv.org/abs/2207.04672)** — Paper describing the translation model covering 200 languages including Wolof. *Very technical, but Section 4 on low-resource languages is accessible.*

- **[Masakhane – Participatory Research for Low-resourced Machine Translation (2020)](https://arxiv.org/abs/2003.11529)** — Describes Masakhane's community-driven approach to building African NLP resources. *Inspiring read for understanding how to contribute to the ecosystem.*

- **[Wolof Morphological Analysis (Dione, 2012)](https://aclanthology.org/L12-1396/)** — Formal morphological analysis of Wolof. Useful theoretical foundation before diving into NLP tools. *Dense but referenced in many subsequent works.*

---

## Groups & Labs

- **[Masakhane](https://www.masakhane.io/)** — Pan-African NLP research community. The best place to find collaborators and data. Strong presence in West Africa. [GitHub](https://github.com/masakhane-io) | [Discord](https://discord.gg/masakhane)

- **[LLACAN (CNRS)](https://llacan.cnrs.fr/)** — French lab for African and comparative linguistics. Produces high-quality linguistic resources on Atlantic languages including Wolof. Rigorous academic work.

- **[African Language Technology (ALT)](https://alt.sadilar.ac.za/)** — South African initiative covering the entire continent. Tools and resources for African NLP.

- **[Zindi Africa](https://zindi.africa/)** — African data science competition platform. Occasionally hosts NLP challenges on local languages. Worth following.

- **[Université Cheikh Anta Diop (UCAD) – Dakar](https://www.ucad.sn/)** — Home to linguistics and computational linguistics researchers working on Wolof and Senegalese languages.

---

## Related Languages

Resources for languages in the same family or region — useful for transfer learning and cross-lingual approaches.

- **[Pulaar/Fula – OPUS](https://opus.nlpl.eu/)** — Pulaar shares many speakers with Wolof in Senegal. Search `fuf` (Fula) on OPUS.

- **[Bambara/Mandinka datasets – OPUS](https://opus.nlpl.eu/)** — Corpora for Bambara/Dioula/Mandinka. Niger-Congo family, useful for comparing approaches.

- **[Serer – LLACAN](https://llacan.cnrs.fr/)** — Linguistic resources for Serer, another major language of Senegal.

- **[GLOTTOLOG – Atlantic-Congo](https://glottolog.org/resource/languoid/id/atla1278)** — Reference for language classification in the region. Useful for understanding cross-lingual relationships.

---

## General African NLP Resources

- **[OPUS – African Languages](https://opus.nlpl.eu/)** — Main portal for parallel corpora in African languages.

- **[Hugging Face – Wolof datasets](https://huggingface.co/datasets?language=language:wo)** — Filter by `language:wo` for Wolof datasets on HuggingFace.

- **[AfricaNLP Workshop (ACL)](https://africanlp.github.io/)** — Annual workshop dedicated to African NLP, co-located with major conferences (ACL, EMNLP). Great reading list to follow the state of the art.

- **[Lacuna Fund](https://lacunafund.org/)** — Fund that finances dataset creation for underrepresented languages. Worth monitoring for funding opportunities.

---

## Contributing

Contributions are welcome! Before submitting a PR:

1. Make sure the resource is not already listed.
2. Add a short comment (1–2 sentences) explaining **why** the resource is useful.
3. Place the resource in the most relevant section.
4. For papers, include the year and a link to ArXiv or ACL Anthology when available.

See [CONTRIBUTING.md](CONTRIBUTING.md) for full guidelines.

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

This repo is under CC0 — public domain. Use, copy, and modify freely.

---

*Community maintained. Last updated: 2026.*