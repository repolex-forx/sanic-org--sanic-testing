# Repolex Knowledge Graph of sanic-org/sanic-testing

RDF knowledge graph data for [sanic-org/sanic-testing](https://github.com/sanic-org/sanic-testing), parsed by [repolex](https://repolex.ai).

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
rlex download sanic-org/sanic-testing
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 66b72d22979f594b8ea45283c7a2f7db6f13c5e3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 66b72d22979f594b8ea45283c7a2f7db6f13c5e3
│           └── chunk-001.nq.gz
├── blob
│   ├── 1bb9b4f10e5a3a598df89ac68610acf80717955b.nq.gz
│   ├── 2749b62c07bde1a143fc788a01f65d448e50ff4f.nq.gz
│   ├── 30b16448ebbc00ee3f15628758f1ca52d552a4ff.nq.gz
│   ├── 327761ef937afcbf27df1ddf4e21a43b5f1a98ce.nq.gz
│   ├── 3baabded116d7489081208c28fdf825c7e23cc79.nq.gz
│   ├── 4f2f8ce00cd37e6f1b9d94c132ed1f1017ab39a4.nq.gz
│   ├── 526565a99166de41b8c2a4beed8309b4e33e1055.nq.gz
│   ├── 5690dc479c799b1154dcd3f3f8642c34e119f9db.nq.gz
│   ├── 7559a405a0f1b4d263d5bc0b88ce87dbd464084a.nq.gz
│   ├── 8faddcb45e7e88b13ea1bfdcac0a718e048f5f8e.nq.gz
│   ├── 90e73f6989b4a26fc2994f763bc49ff0dbf7aeba.nq.gz
│   ├── 977daa9dafeecb8569fe97073ada5d75921d2913.nq.gz
│   ├── 9a148b47dca84a7d9bd9363a59834f1071512862.nq.gz
│   ├── 9cf68d88704d191348e4afb6847867f039bdd095.nq.gz
│   ├── b2e72f0eec7897edda044f16dc8630ef113fc4fc.nq.gz
│   ├── c78d40e9d62e10b864e789c5b951afd95b5e48c7.nq.gz
│   ├── d11e149da27725a27c83c0e797c9f17189cb8e52.nq.gz
│   ├── ddc3deecb46aed7eaf136cf3e424df14a30189a7.nq.gz
│   ├── e17066564cd1f6f8e603379e975c45962dc5c34c.nq.gz
│   └── ee9b1861a59dafbb195ec974a3ba969b35d616c8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 66b72d22979f594b8ea45283c7a2f7db6f13c5e3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[sanic-org/sanic-testing](https://github.com/sanic-org/sanic-testing)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
