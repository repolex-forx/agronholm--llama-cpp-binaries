# Repolex Knowledge Graph of agronholm/llama-cpp-binaries

RDF knowledge graph data for [agronholm/llama-cpp-binaries](https://github.com/agronholm/llama-cpp-binaries), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/llama-cpp-binaries
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0356d5af3d097ee07e17d94581e7b04858d4a755
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0356d5af3d097ee07e17d94581e7b04858d4a755
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ad25db4bd1d86c452db3f9602ccdbe172438f52.nq.gz
│   ├── 1292be89786de1c6dcfe0662cfc61b20fda92c24.nq.gz
│   ├── 76685ee6224b2d2b3603af9cd2db8769f39aa4e2.nq.gz
│   ├── 7cfff9c182bd4ce85f23ef5b96d7b5139346b3e5.nq.gz
│   ├── 8b3e948e7fe2c2cd85b13124c560893595ea7928.nq.gz
│   ├── 969dd848af7363559a809208281c0439dbbe596b.nq.gz
│   ├── bde75cc3b0f5ef98e49e3d75ba2ab0597f60028d.nq.gz
│   ├── ca607c52614852ef96fb6599ed3c65a60053a5c0.nq.gz
│   ├── dbde1f156e4c6f91aeb1c68ea995230d173d4824.nq.gz
│   ├── dc4cba502604e7a2613beb27881e19b3703233fd.nq.gz
│   ├── e49bf1b658705882810aa0dd15b62c70172e551b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e75df6112fee409219ce94ff301beab8ecf53246.nq.gz
│   └── ece1061e71af58f93e856e8a60c8db5b674ef9aa.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0356d5af3d097ee07e17d94581e7b04858d4a755.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 20 files
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

[agronholm/llama-cpp-binaries](https://github.com/agronholm/llama-cpp-binaries)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
