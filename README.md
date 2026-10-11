# Repolex Knowledge Graph of certifi/erlang-certifi

RDF knowledge graph data for [certifi/erlang-certifi](https://github.com/certifi/erlang-certifi), parsed by [repolex](https://repolex.ai).

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
rlex download certifi/erlang-certifi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 36e47cba36c8cdfa2d81246c864161d4710a6c92
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 36e47cba36c8cdfa2d81246c864161d4710a6c92
│           └── chunk-001.nq.gz
├── blob
│   ├── 13ad9ad8b091a9c10b8cc73e0ee73dd62ea31a20.nq.gz
│   ├── 3566ecf863ce31dd38e7eea3ca36a788b1153996.nq.gz
│   ├── 3a707dbc43824bdf41a33d82e8eb83db0e282535.nq.gz
│   ├── 431b9418516da775cbf7e752cac9f5ee807e89d5.nq.gz
│   ├── 4f06d364c4af0d8fe576cab32a80f2c859637069.nq.gz
│   ├── 57afcca04590ff2bbf2f83b8eac4f856df782c74.nq.gz
│   ├── 667297d8ef83b22b0ccef96b6c7e77cc52d3172c.nq.gz
│   ├── 9cb7f6eef7b1c7900db6462777b7ec1cbdccf8d5.nq.gz
│   ├── a9336dafb0d34c4a1e6cffb84d470e7dd874e6c3.nq.gz
│   ├── a9ee1744e7315f87f2c76eb70febdf631f1edf4e.nq.gz
│   ├── c052788771a24843a7cb4c9a06978fcb8140f773.nq.gz
│   ├── d112c489681e6881391f6b0adcefb05644a6dfad.nq.gz
│   └── d865692761d3e17ad719f68edaca16726a3faef1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 36e47cba36c8cdfa2d81246c864161d4710a6c92.nq.gz
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

[certifi/erlang-certifi](https://github.com/certifi/erlang-certifi)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
