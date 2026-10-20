# Repolex Knowledge Graph of spulec/uncurl

RDF knowledge graph data for [spulec/uncurl](https://github.com/spulec/uncurl), parsed by [repolex](https://repolex.ai).

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
rlex download spulec/uncurl
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ee947f48b906b0010eacd89acf426206dfb0537f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ee947f48b906b0010eacd89acf426206dfb0537f
│           └── chunk-001.nq.gz
├── blob
│   ├── 0eca7008b6d6b1b92b1d6803f74dd808292130fc.nq.gz
│   ├── 12120fb1a0a6919c7d1a64e1ebf6435a0cf714fc.nq.gz
│   ├── 275f088bcb32cdd1274bb1b46c44e8d3a2640a1a.nq.gz
│   ├── 2b83f8948b545f81677a59550b88a71e8035c0e7.nq.gz
│   ├── 488c1f01dbbc6f6e017f971db9e6ce81abad38ca.nq.gz
│   ├── 62f69c14fb494434f31eaf508d79a28728d9304c.nq.gz
│   ├── 75501b2363f799107a432e21266e40a580d36211.nq.gz
│   ├── 7a07fa240d9331b021cef4aa9d8e106c19658c05.nq.gz
│   ├── 7dbccfe156bb948b4e531d9458252a2b9d60bc05.nq.gz
│   ├── 90a85e7149454f173dd595bdeb884340cc01e6f6.nq.gz
│   ├── 9ae18b61031608f6d964cd42e643da886c79f1af.nq.gz
│   ├── bca6674eac87d17a28ca57dd72204ae63cd71632.nq.gz
│   └── eacc963ed68bab9bb5fd3eece1643e932c73ec91.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ee947f48b906b0010eacd89acf426206dfb0537f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[spulec/uncurl](https://github.com/spulec/uncurl)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
