# Repolex Knowledge Graph of pytest-dev/regendoc

RDF knowledge graph data for [pytest-dev/regendoc](https://github.com/pytest-dev/regendoc), parsed by [repolex](https://repolex.ai).

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
rlex download pytest-dev/regendoc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e6013a994fb1577c557591b5ae1cee56a0c88380
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e6013a994fb1577c557591b5ae1cee56a0c88380
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b5eaf76f18d1a0e43be2fc23961678617f1b536.nq.gz
│   ├── 16a31fa9f0f4e6c16624fe6a6ddecc54f5d2339f.nq.gz
│   ├── 315d1ea0601479748aea12e3e5a774b85e6b21ef.nq.gz
│   ├── 325f2ec84003a0f4a4eb7329a99643d7a3426ee7.nq.gz
│   ├── 429b4fcf1ee8db5af64705220afe8c67e28aea7d.nq.gz
│   ├── 438ec35314103e1e5a5964677c69bb6e5a4baa7d.nq.gz
│   ├── 44a13fee6bc9332481673008c36176e72d2e5198.nq.gz
│   ├── 84d48817e299bcbdb67a6137287b216fc6b34ee4.nq.gz
│   ├── 8c32274d0fb7099170621ba143dba655dd489f61.nq.gz
│   ├── 8d962c243abf6aaec75970db419c1770b3fb08e5.nq.gz
│   ├── 96389cbf93e46a18f8c0b1cf7f1a306c2523bdc5.nq.gz
│   ├── a612ad9813b006ce81d1ee438dd784da99a54007.nq.gz
│   ├── b7d83e19a2335a7586212a06eb298ea4b3cb8b5c.nq.gz
│   ├── d42d6e8a9069b53320a7279dba033738528053ec.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ee3001df02566b73e6f5cfe9a0ebab2bc9d6baf8.nq.gz
│   └── faaef8f073279e7f7949b20a5767954ad16ebb8e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e6013a994fb1577c557591b5ae1cee56a0c88380.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[pytest-dev/regendoc](https://github.com/pytest-dev/regendoc)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
