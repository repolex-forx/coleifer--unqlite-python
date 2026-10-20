# Repolex Knowledge Graph of coleifer/unqlite-python

RDF knowledge graph data for [coleifer/unqlite-python](https://github.com/coleifer/unqlite-python), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/unqlite-python
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b42c6aa4e53af15a8d8851017016f5883a20a4e4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b42c6aa4e53af15a8d8851017016f5883a20a4e4
│           └── chunk-001.nq.gz
├── blob
│   ├── 0937ffd353692cc1aaaf07b57165fdaa0114276d.nq.gz
│   ├── 1156dae80463fd710d80ea8604d1ba3887d4d7d6.nq.gz
│   ├── 2d4ddec40dce5095f7d75f6d3642e6881b6e48c5.nq.gz
│   ├── 411127284d1841139a4b1fdf42ee6a5561497bf4.nq.gz
│   ├── 4332c0a3bca5f6c29309140994ca41c82f4dac92.nq.gz
│   ├── 558c620be9c0dbcd7e6e1f13bf394ef36ad7dbd2.nq.gz
│   ├── 6507454824fdcdd6916f6f94ee823b6a55aaab85.nq.gz
│   ├── 68df82b679859a402ef042a508d8db2853c9bd81.nq.gz
│   ├── 69c39fd3f5cfe429882ab58573b7d4b891605a84.nq.gz
│   ├── a0df4d4bca8988e83c77c65ae42105d72a3c31fb.nq.gz
│   ├── b8651d571336ac318253020ff1cb866b3489ce91.nq.gz
│   ├── bac270613ff462ab041ed19df82f6ba60c6b6511.nq.gz
│   ├── c752ab3ead2e7be324e5cafb5e1d53135c16af13.nq.gz
│   ├── d553e71acb25b56bf1e6379a8131fbae6c88b13c.nq.gz
│   ├── de11b8ad0dc390e75287b8c2c1ddf816975f0705.nq.gz
│   ├── e2c6ac55935d22b537c9866cbddecc064c6ed5ca.nq.gz
│   ├── eb02f550d140d9e6290414bca2568f4cd09f306b.nq.gz
│   ├── efb3362ff1c49a3877144b7daadae60912aaf9ba.nq.gz
│   └── fd457595fda53d602ce78c03862edad080f91ae6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b42c6aa4e53af15a8d8851017016f5883a20a4e4.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[coleifer/unqlite-python](https://github.com/coleifer/unqlite-python)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
