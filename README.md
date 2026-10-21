# Repolex Knowledge Graph of PyCQA/bandit-action

RDF knowledge graph data for [PyCQA/bandit-action](https://github.com/PyCQA/bandit-action), parsed by [repolex](https://repolex.ai).

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
rlex download PyCQA/bandit-action
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 044eb14cd9d9e339d23c8f6511f217824a10a256
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 044eb14cd9d9e339d23c8f6511f217824a10a256
│           └── chunk-001.nq.gz
├── blob
│   ├── 04beb2d04c6092731c946960476314d0309cf1b0.nq.gz
│   ├── 123014908bebbfb7ecfa1d15daaceb272fabe05b.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 34f39d2fa23e80361d622a72e0e32e2d52918488.nq.gz
│   ├── 559c5e17dbf91b289ea02beffab9a26a86ca1f72.nq.gz
│   ├── 67e8a09c4b8dec6961cebcd6a90364a4a08eff3f.nq.gz
│   ├── 6b613871be68328ab69b144878e49cbf08011142.nq.gz
│   ├── af26e4d460763a29b82b24b6322719b1d402c6c1.nq.gz
│   ├── ee6e14affc5361a244d204b6be0f856e3c275137.nq.gz
│   ├── fbf5bae1ad218cbb858232fb2debd19a4c3e2db2.nq.gz
│   └── fc936e67c6f02fa04a09b048e0d2b395258f99d5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 044eb14cd9d9e339d23c8f6511f217824a10a256.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[PyCQA/bandit-action](https://github.com/PyCQA/bandit-action)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
