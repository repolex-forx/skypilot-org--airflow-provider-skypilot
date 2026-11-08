# Repolex Knowledge Graph of skypilot-org/airflow-provider-skypilot

RDF knowledge graph data for [skypilot-org/airflow-provider-skypilot](https://github.com/skypilot-org/airflow-provider-skypilot), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download skypilot-org/airflow-provider-skypilot
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── aedad84786f567536f9540ccd726f1cb8d9f5443
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── aedad84786f567536f9540ccd726f1cb8d9f5443
│           └── chunk-001.nq.gz
├── blob
│   ├── 10b131c7ace5fd7a33a0d45b43fb9e68c16b8d57.nq.gz
│   ├── 1c5354f4d6e01e559b80284b5874ebe7155bc521.nq.gz
│   ├── 1fbf61ebaf2a12298c7f66f34dcf699632be7dd2.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2b5b7ecaf1017667775c8d770105297505de95bc.nq.gz
│   ├── 2bc0b8e2d3522e86d98f8b7fcd6571f4c3b43732.nq.gz
│   ├── 310eb18d1b94b5e0cc8999e25772fa661e77294a.nq.gz
│   ├── 3f78cbad434409b4fd2b7f8e4a8f7b7bcd459778.nq.gz
│   ├── 418bfbfb23eef8eac782139618393656668c3795.nq.gz
│   ├── 4915a01214658a23c04f9d54491a010ecd585662.nq.gz
│   ├── 53056eb22da6b2e9878db2daed027e3444c0521e.nq.gz
│   ├── 59740f44c5eea98801767482f7e4adbaa774d0ca.nq.gz
│   ├── 5b5e8e9a4231864d0e018a31d0867d5743bf86d4.nq.gz
│   ├── 6d4bd0e2bb05e88cf7029ed551e4dde326701ce8.nq.gz
│   ├── 6eab51473ea77991456d0fce032509f084d5fce7.nq.gz
│   ├── 75ccd32898c104d7511acbd938de58b5adc2866e.nq.gz
│   ├── 77aca40164b9e0b976b9eb09905b808f7215ee95.nq.gz
│   ├── 81284dc20888bfe2999fdef52960fbe8cefe2dc8.nq.gz
│   ├── 8633dd4950183ab08d3001eb73514e0937b644a3.nq.gz
│   ├── 8945a356c2cc1dcda1332090b6d1634d44c11eb4.nq.gz
│   ├── 8d3d7d710ae7c5ba48619df9428d83300ce85c9f.nq.gz
│   ├── 9975d370dd06173075062f31253cd4a9f5d54abf.nq.gz
│   ├── ab91da564f894bc81fc51e05cc40b9ca64590477.nq.gz
│   ├── b98267cf6feb6e73d97c58277bc41ce66a95ec94.nq.gz
│   ├── b99356a820f6a6f9eadc96bce38f122885a1456a.nq.gz
│   ├── c2ea655da4c4aade0599b0480ed75fb3087aa77b.nq.gz
│   ├── c3c8da0afe19be1acdc61b1c3bec05dd36997f01.nq.gz
│   ├── c849812be7063205ed59d46ed8dd38d13b0eea03.nq.gz
│   ├── cf042c090d32c7434ceea14b664efc5937a2aa9f.nq.gz
│   ├── d793774a93cc9714052ccb3b9ae86ad4a4de5259.nq.gz
│   ├── df7782a33378a57c966a2eb1df947a674c6a63bc.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e7798cf2b6b7b8ef0cf6855c69ebcb4e24cd76d5.nq.gz
│   ├── eb92ffa9535940b753fad0bd350c95202ad848e7.nq.gz
│   └── fd8141c722ffc5b7c3cce731e311ac9b4e36c6ad.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── aedad84786f567536f9540ccd726f1cb8d9f5443.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 42 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[skypilot-org/airflow-provider-skypilot](https://github.com/skypilot-org/airflow-provider-skypilot)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
