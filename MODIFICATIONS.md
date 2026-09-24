# Modifications in this fork

This repository is a modified version of
[litagin02/Style-Bert-VITS2](https://github.com/litagin02/Style-Bert-VITS2),
forked from upstream commit `66de777` (2025-08-24), by Omakase AI
([Omakase-Robotics-Org](https://github.com/Omakase-Robotics-Org)).
It remains licensed under the **GNU AGPL v3.0** ([LICENSE](LICENSE)). The
`text/user_dict/` module remains under the **GNU LGPL v3.0** ([LGPL_LICENSE](LGPL_LICENSE)).
The complete source of what we run is this repository; see the git history for exact diffs.

| date | file(s) | change |
|---|---|---|
| 2026-09-23 | `style_bert_vits2/nlp/english/user_dict.rep` (new), `style_bert_vits2/nlp/english/g2p.py` | Project English lexicon merged over CMUdict at load. A word split into several subword tokens is phonemized as one word instead of piece by piece. |
| 2026-09-23 | `style_bert_vits2/nlp/english/normalizer.py` | `N%` is read as "N percent" (the `%` was dropped). |
| 2026-09-23 | `style_bert_vits2/nlp/bert_models.py` | BERT models are cast to fp32 after loading (fp16 vs fp32 mismatch on torch >= 2.7 / Blackwell). |
| 2026-09-23 | `style_gen.py` | wespeaker checkpoint loaded from a local download with `torch.serialization.safe_globals` (current huggingface_hub / torch `weights_only`). |
| 2026-09-24 | `server_fastapi.py` | Optional `SBV2_SKIP_JP=1` skips starting the JP pyopenjtalk worker, for EN-only serving. Unset keeps upstream behavior. |
| 2026-09-24 | `MODIFICATIONS.md` (new), `README.md` | This notice. |
