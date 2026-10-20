# Repolex Knowledge Graph of simonw/alchemy-utils

RDF knowledge graph data for [simonw/alchemy-utils](https://github.com/simonw/alchemy-utils), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/alchemy-utils
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c2432fb580317dd6a8cdf3e3451a2fc6a85631f7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c2432fb580317dd6a8cdf3e3451a2fc6a85631f7
│           └── chunk-001.nq.gz
├── blob
│   ├── 05824e72aded266398c3b6b76e6247840ea8b922.nq.gz
│   ├── 063b8e03edf9f5bfb7bad5e85ff6b31fca1ad7a6.nq.gz
│   ├── 1242d43277017748bbbf3d0a104ec4cf78245822.nq.gz
│   ├── 1b32d93a0e2766dc2616af95f6aa30cdb37a7e25.nq.gz
│   ├── 1b4a90534c3da00bd497d9b81b472cb3937a6916.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2c13511c89630a4b3c56fdaa625122de2ab9c9a8.nq.gz
│   ├── 2fd3abcf09eec28177b40b8da5ef658124bc30b0.nq.gz
│   ├── 36f3270afddeea899d01d3d8456d8ffb1ad7223b.nq.gz
│   ├── 4692ce166bcdd48ef154d91111052bc6579dcc85.nq.gz
│   ├── 4764b15a969ac7ca162fc52e6f8d4133bb8f829c.nq.gz
│   ├── 4b9515429f2f6dbebf63a5a8f0a87b4a84d2b841.nq.gz
│   ├── 4cafccbafc79cf668801fe36c883a1a624f98913.nq.gz
│   ├── 543ec9a23c94cabe4150d19c8f566b6b7d0def9c.nq.gz
│   ├── 572614e0225825293d3f4c7edf7ee35eba7b4622.nq.gz
│   ├── 582d879a3e14c181b47ff589658325b439e1deb4.nq.gz
│   ├── 6ca9d1c9779a9056f98146e5a54d2f1f27457974.nq.gz
│   ├── 88f7c465f0a2aa214b3576a82bc6204b3ccf3a03.nq.gz
│   ├── 97d25fdb9752a1def2bf9c517ae57d07867ec082.nq.gz
│   ├── a06499531e9540f5e28fb9c043e688ec1b75de81.nq.gz
│   ├── aab879467e3941f7931fd4678d75e87b047823b0.nq.gz
│   ├── c4ef7ce7500fe5e5699faf05ae4ce59efa14225e.nq.gz
│   └── db0805ae48896a86af2798a892bc2feabaa24e94.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c2432fb580317dd6a8cdf3e3451a2fc6a85631f7.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 29 files
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

[simonw/alchemy-utils](https://github.com/simonw/alchemy-utils)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
