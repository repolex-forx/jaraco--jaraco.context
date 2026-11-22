# Repolex Knowledge Graph of jaraco/jaraco.context

RDF knowledge graph data for [jaraco/jaraco.context](https://github.com/jaraco/jaraco.context), parsed by [repolex](https://repolex.ai).

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
rlex download jaraco/jaraco.context
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   ├── 0474f208479be3752a7e7a3a6af39386af0fe91c
│   │   │   └── chunk-001.nq.gz
│   │   └── 098f39c911d4504b2c718f2ff483ae24f1c4d378
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 098f39c911d4504b2c718f2ff483ae24f1c4d378.nq.gz
│   └── repolex
│       ├── 0474f208479be3752a7e7a3a6af39386af0fe91c
│       │   └── chunk-001.nq.gz
│       └── 098f39c911d4504b2c718f2ff483ae24f1c4d378
│           └── chunk-001.nq.gz
├── blob
│   ├── 03941de3f479e26e5db081921200026cb308d98c.nq.gz
│   ├── 1f2aa7533b0423a8eb943f6f4ec02498e39581a0.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 3c1f8b13da0b37a2a517e9c0e2bae5bb680109ac.nq.gz
│   ├── 42f91d13e23f869b416433c3f364ef9a3252c925.nq.gz
│   ├── 46ef1f44197eb2ca0cc9b8ad9167389f72fc109d.nq.gz
│   ├── 47b328bd545ad4fa90a0bf5826a355b7cecb98bb.nq.gz
│   ├── 54c9000ec94341dd65c2053251b85b124017b9b5.nq.gz
│   ├── 54cc8303b22089e12053e552d4e6cb852a865b8a.nq.gz
│   ├── 54f99acbfac68c2be8283174ea64f1730a795e49.nq.gz
│   ├── 577e87a793a20e413f7321f4f17ec1eba2ea1962.nq.gz
│   ├── 58d98f096b5355e7cd377871380c788ec7512172.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 5c05f9e27d57a4b7a3c3a9fdfecf8cddb8be499f.nq.gz
│   ├── 63c0825f6bd49615f4f386b95463111f7992f6bc.nq.gz
│   ├── 700235be57c1b2872455c0be5333f59cf568e252.nq.gz
│   ├── 701b0bdb9705fc13d4646709501641a3c779a7e0.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 79ee087a57d265060fa79a943de1549fc8b445a7.nq.gz
│   ├── 8de62b9bd6d913f99c633360b270bb607785ed09.nq.gz
│   ├── 9cc26defe2029014a876e9c7dd15c3707da9559b.nq.gz
│   ├── a3c063bdbac1940db4cfca3740a6b0165be40993.nq.gz
│   ├── a511eaea6dbbe24d2316f477e9fee9c64950ccd2.nq.gz
│   ├── c8baa5b62dc6c6dcc8629b4c5bd534f12ef94dc9.nq.gz
│   ├── ca68a9439e82ade23deecb45b2fcc64b47d9c940.nq.gz
│   ├── d40c74ac327565dfb08b3560a524385ba357eb8c.nq.gz
│   ├── d71e08b3c95a628d3d537496061cf27d1cb27685.nq.gz
│   ├── e05a3d4a2ab888e32952006d8cd380864368db5f.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 098f39c911d4504b2c718f2ff483ae24f1c4d378.nq.gz
├── filetree
│   ├── 0474f208479be3752a7e7a3a6af39386af0fe91c.nq.gz
│   └── 098f39c911d4504b2c718f2ff483ae24f1c4d378.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

17 directories, 43 files
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

[jaraco/jaraco.context](https://github.com/jaraco/jaraco.context)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
