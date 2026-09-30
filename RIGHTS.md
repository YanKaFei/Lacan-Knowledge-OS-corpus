# RIGHTS.md — rights and permitted use of this corpus

> **This repository is public. The text in it is not free to reuse.**
>
> Public visibility is not a licence. No rights in any text published here were transferred to this
> project, and none are granted by the fact that you can read them.
>
> This page states the boundary as precisely as this project can. It is **not legal advice**, and it
> does not decide anything for you. Where your situation is unclear, the determination — and the
> risk — are yours.

---

## 1. What is here, and whose it is

| Source id | What it is | Rights position |
|---|---|---|
| `corpus-source.staferla` | a publicly readable French **working transcription** of Lacan's seminars (S1–S27) | Being readable online is **not** a licence to reuse. The transcription site's own legal position is not documented here, and this project does not assert one. |
| `corpus-source.seuil-print` | text extracted from the **Seuil print edition** (S1–S5), with page numbers | An in-copyright commercial edition. Extracting, storing and republishing its text engages the publisher's and the author's estate's rights. |
| `corpus-source.zh-translation-project` | a **community Chinese translation** project | A translation is a **derivative work**: it carries the translator's rights *and* the underlying author's rights. |

Lacan died in 1981. In France and the EU, rights run for **70 years after death**, so the underlying
texts remain in copyright for decades. Other jurisdictions analyse differently (in the United States:
publication date, renewal, fair use), and **this project asserts nothing about the status of any part
of this corpus in any jurisdiction**.

The **engine code** is a different artifact with a different licence:
[Apache-2.0](https://github.com/YanKaFei/Lacan-Knowledge-OS/blob/main/LICENSE). Reading that licence and
concluding "therefore the seminars are reusable" is the most likely mistake this page exists to prevent.

---

## 2. Permitted and not permitted

| Permitted | Not permitted |
|---|---|
| read, study and analyse the text yourself | commercial use of any kind — paid products, deliverables, services, consultancy outputs |
| quote passages in your own scholarly writing, with attribution to the recorded source | re-uploading, mirroring, re-packaging, bundling or posting the corpus pack anywhere |
| build local indexes or embeddings for your own research | exposing the text to third parties — a website, an API, an app, a dataset release |
| keep it offline on your own machine | using it as training data for a model you distribute or deploy publicly |
| cite passage ids and witnesses in your work | presenting the corpus, or a derivative of it, as your own licensed material |

Access to and use of this corpus is granted **for research and study only**. If your intended use is
in the right-hand column, you must obtain permission from the relevant rights holders yourself.

---

## 3. Arguments that do not change the analysis

**"It was transcribed or scanned by someone else."** Derivation adds a rights holder, it does not
remove one. A transcription or scan of a protected work is still a reproduction of it.

**"I am not using it commercially."** Non-commerciality is relevant to private study and can weigh in a
fair-use analysis. It is not a licence, and it does not make **publishing an entire protected work** a
permitted act.

**"The repository is public, so it must be free."** Public visibility is a hosting decision by one
person who holds no rights in the material, made for the convenience of researchers. It grants you
nothing and it transfers nothing.

**"Other people do it."** Enforcement is uneven, not absent. Rights holders in these texts have pursued
unauthorised circulation, and hosting platforms act on notices with takedowns and account sanctions.

None of this means that reading material you obtained lawfully, for your own study, is wrongdoing.
It means the decision to publish, mirror, sell or serve it is not one this project can make for you.

---

## 4. What this project does to keep the boundary honest

1. **The engine contains no corpus text.** Its publication is scripted and then negatively verified:
   fragments sampled from the corpus are searched for across the engine tree, and a single hit rejects
   the build (see [`docs/PUBLIC_EDITION.md`](https://github.com/YanKaFei/Lacan-Knowledge-OS/blob/main/docs/PUBLIC_EDITION.md)).
2. **The corpus is published as a hash-manifested pack**, so an altered or partial copy cannot pass
   verification: `tools/fetch-corpus.py` checks the pack hash and then every file hash, and refuses to
   install anything that does not match.
3. **Agents are instructed not to cross the line.** The engine's
   [`AGENTS.md`](https://github.com/YanKaFei/Lacan-Knowledge-OS/blob/main/AGENTS.md) tells any AI working
   there never to fabricate an answer the corpus cannot support, and never to treat this text as licensed
   for redistribution.
4. **Rights concerns are acted on.** See below.

---

## 5. Reporting a rights concern

If you hold rights in material published here and want it removed, clarified, attributed differently or
replaced: open an issue on the [engine repository](https://github.com/YanKaFei/Lacan-Knowledge-OS/issues)
without pasting corpus text, or contact the maintainer through the repository profile.

We will act on a substantiated request. Removing material on request is not an admission about anything —
it is the only responsible default.

---

## 中文要点

- **本仓库是公开的，但里面的文本不是公有领域、也不是自由可用的。**「公开可见」不等于「授权」；
  本项目对这些文本**不持有任何权利**，也没有把任何权利转移给你。
- **三个来源**：Staferla 法语工作转录（能在线阅读 ≠ 可再利用）、**瑟伊版印刷本**（S1–S5）的文本抽取
  （在版商业出版物）、**社区中译项目**（译本属演绎作品，含译者与原作双重权利）。
  拉康 1981 年去世，法国/欧盟的保护期为死后 70 年 —— 原作仍在版权期内。
- **只允许**：本人研读、在学术写作中引用并注明来源、在本地建索引、离线自用。
- **不允许**：任何形式的商用；再上传/镜像/重新打包/转载；把文本做成对外提供的内容
  （网站/API/App/数据集）；作为对外发布或部署的模型的训练数据；把本语料或衍生物说成自己已获授权。
- **是否合法由你自己判断。** 本页只陈述边界，**不构成法律意见**，也不替你作决定。
- **需要能公开或商用的文本？** 用引擎 + 你有权使用的语料（公有领域 demo、你自己的文本、或已授权版本）。
- **权利人请求下架/更名/改注**：见上面 §5，本项目会处理有依据的请求。
