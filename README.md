# Lacan Knowledge OS — corpus pack (**PRIVATE**)

> ⚠️ **This repository is private on purpose, and it must stay private.**
> It ships third-party copyrighted texts. Do not make it public, do not mirror it, do not
> redistribute the pack.

## What is in here

`corpus-pack-v1.manifest.json` lists every file with its sha256. The pack itself is attached to
the [corpus-v1 release](../../releases/tag/corpus-v1) as an asset (215.7 MB compressed,
1,427 MB uncompressed, 2,078 files):

| Contents | Detail |
|---|---|
| `02_Lacan_Seminars/**` | 1,979 seminar files, French + Chinese, with frontmatter (ids, provenance, review status) |
| `_data/passage_store/*.jsonl` | passage store: 249,105 passages with `raw_text` / `normalized_text`, witnesses, realizations, sessions, concepts, corpus sources |
| `_data/render_normalization.jsonl`, `_data/terminology_bridge.jsonl` | derived tables |
| `_data/ontology/**`, `_data/entities/**`, `_data/bibliography/**` | canonical ontology, person/case registry, bibliography registry |
| `_data/eval/**` | human-review, gold-v2 and frozen-identity artifacts — the freeze verifies these |
| `_data/corpus_inventory.json`, index manifests | the data-version inputs `core_freeze.py --verify` reads |
| `_data/index/alias_index.jsonl` and other small retrieval inputs | derived from the engine's own code references, so nothing is missed |
| `_index/passage_store.sqlite`, `_data/index/lexical.sqlite` | ready-to-run stores — no rebuild needed |

## Rights (read this before sharing)

| Source | What it is | Why it cannot be public |
|---|---|---|
| `corpus-source.staferla` | public French working-transcription site | being readable online is not a licence to redistribute |
| `corpus-source.seuil-print` | text extraction from the **Seuil** print edition (S1–S5) | in-copyright commercial edition |
| `corpus-source.zh-translation-project` | community Chinese translation project | a translation is a derivative work; the rights are not ours to grant |

The **engine** is open source (Apache-2.0): https://github.com/YanKaFei/Lacan-Knowledge-OS —
that repository deliberately contains no source text. This pack is the other half, and it is
distributed only to people who are entitled to use these texts.

## How to use it

```sh
# 1) get the engine
git clone https://github.com/YanKaFei/Lacan-Knowledge-OS.git
cd Lacan-Knowledge-OS

# 2) download the pack (private: needs a token with repo read access)
#    ⚠️ use the API asset endpoint — the plain /releases/download/ URL returns 404 for
#    private repos, and the redirect needs the Authorization header re-attached.
ASSET=$(gh release view corpus-v1 --repo YanKaFei/Lacan-Knowledge-OS-corpus --json assets \
        --jq '.assets[0].id')
curl -sL -H "Authorization: Bearer $GITHUB_TOKEN" -H "Accept: application/octet-stream" \
  -o corpus-pack-v1.tar.gz \
  "https://api.github.com/repos/YanKaFei/Lacan-Knowledge-OS-corpus/releases/assets/$ASSET"
curl -sL -o corpus-pack-v1.manifest.json \
  https://raw.githubusercontent.com/YanKaFei/Lacan-Knowledge-OS-corpus/main/corpus-pack-v1.manifest.json

# 3) verify + install (refuses on any hash mismatch)
python3 tools/fetch-corpus.py --pack corpus-pack-v1.tar.gz \
  --manifest corpus-pack-v1.manifest.json --into .

# 4) run
python3 -m workspace_ui.server.cli --port 3090     # → http://127.0.0.1:3090/help
```

## Rebuilding the pack

From a full local vault:

```sh
python3 tools/pack-corpus.py --out /tmp/corpus-pack            # 215 MB
python3 tools/pack-corpus.py --out /tmp/corpus-pack --with-vector   # + vector index (+365 MB)
python3 tools/fetch-corpus.py --pack … --manifest … --check     # verify without installing
```

## Verified on a clean install

8/8 layers READY · a Seminar XI run returning `VALIDATED_WITH_QUALIFICATIONS` with 3 claims and
3 citations · passage text readable in the Evidence Inspector · 62 concepts and 249,105 passages
in Explore · a 13-page Help Centre.

## Granting someone access

Add them as a collaborator (Settings → Collaborators) — that is the intended way to share this.
Downloading it requires a GitHub token with read access to this repository.
