# Repolex Knowledge Graph of pyca/ed25519

RDF knowledge graph data for [pyca/ed25519](https://github.com/pyca/ed25519), parsed by [repolex](https://repolex.ai).

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
rlex download pyca/ed25519
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bc01a714d2cbeec676991192c7beb01b2e072100
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bc01a714d2cbeec676991192c7beb01b2e072100
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e259d42c996742e9e3cba14c677129b2c1b6311.nq.gz
│   ├── 123014908bebbfb7ecfa1d15daaceb272fabe05b.nq.gz
│   ├── 1fbde466a7c89c285d8166eeb9d91e2d4fc64b26.nq.gz
│   ├── 2c57616816dccf985b4736f7be21c1e025c56898.nq.gz
│   ├── 3f3ead60080f6427da1b00775f41a8962ce5807a.nq.gz
│   ├── 7dbd36e392462a94ea60132a7bb895a1c969c8c6.nq.gz
│   ├── 88032391df0bcddb06e6e1d3911cd899fb31df6a.nq.gz
│   ├── bbab0e6fe5d9254c8344451f13a9d572bb8c358a.nq.gz
│   ├── bfd157a0c978bf1d832da6f73ff2159d5210b7a3.nq.gz
│   ├── c13ed92522be89239b43552d25488c2b9bf5c6d1.nq.gz
│   ├── cca6232a874658d1dd8e0e3899d48e24b997365d.nq.gz
│   ├── d86cb58f5a5fb8b297aaa55fd67a390102519059.nq.gz
│   └── fd74fbe135154e1f375b6181d907abfdbfd67f05.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bc01a714d2cbeec676991192c7beb01b2e072100.nq.gz
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

[pyca/ed25519](https://github.com/pyca/ed25519)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
