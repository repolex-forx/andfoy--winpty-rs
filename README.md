# Repolex Knowledge Graph of andfoy/winpty-rs

RDF knowledge graph data for [andfoy/winpty-rs](https://github.com/andfoy/winpty-rs), parsed by [repolex](https://repolex.ai).

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
rlex download andfoy/winpty-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1cc115c87a80c1194083e4d16eb2c770eef28438
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 1cc115c87a80c1194083e4d16eb2c770eef28438.nq.gz
│   └── repolex
│       └── 1cc115c87a80c1194083e4d16eb2c770eef28438
│           └── chunk-001.nq.gz
├── blob
│   ├── 09875d6bb9b732c1a7ff90d805fe016a7ceea2cc.nq.gz
│   ├── 0a51969a3e1da3c8f8d3e9ea3da202a70e332ed0.nq.gz
│   ├── 114b3ea10e584170493ac5ebebdec1e3dae8fcb7.nq.gz
│   ├── 17d370dd3a29578183eeeec651ede64bb0bece3e.nq.gz
│   ├── 1d8042d7f18c37e473fcca004dc5bdfaac1a861a.nq.gz
│   ├── 1e3ac29a1868a36fe39c48ed861a6a99b497574e.nq.gz
│   ├── 359e3be98cadcd8c6827d4b808cae55d284f6dda.nq.gz
│   ├── 36e7d8a798144babdc97cb64753fab8f25a2cd3a.nq.gz
│   ├── 3768dbb7ce9fcb380b90b705071ccafd879a7bd3.nq.gz
│   ├── 392654a670cd4680f46a461733d1683c39b0970d.nq.gz
│   ├── 40b77fe14a0dab644a77c32712a15b2838f56768.nq.gz
│   ├── 4be65a9394e989519cab6b1d43b39f651e865afd.nq.gz
│   ├── 4e8226b6e05fe20950d8123dff4102b5b7e9ad7c.nq.gz
│   ├── 55a81928019771b1e42ba98e17955dbf7e47aea6.nq.gz
│   ├── 59f15300f4975f1659bf4023e3bd7f41ce810fdb.nq.gz
│   ├── 643c8f6a1f4eafb15a8f64512ac559fd92e24d82.nq.gz
│   ├── 6873eb95920598e34b17f5d1bfe2e7c248dc54cd.nq.gz
│   ├── 6e36f8bd6d3e6464c302d09df49cf358e6f5baa9.nq.gz
│   ├── 7095065b279935cfef60c7f6072e0861724115b6.nq.gz
│   ├── 7f6b46730a88fdd0b65b44edb6de2ef26a144ba4.nq.gz
│   ├── 8389df004e7a06ffeb05b9363805ef1c354677d7.nq.gz
│   ├── 8b00a6164bef2d070bfe6f86239cb036bfb85b9c.nq.gz
│   ├── aee9c9f9b3c439f02bf47d21a3841bd5839aeb25.nq.gz
│   ├── b2653af58f4c9229733f70227adfcc035442b3ee.nq.gz
│   ├── c1c17cd689eb47399c6f215511a5ad4cc8bd492f.nq.gz
│   ├── c23b34fcb237c671e60253eda4d254b318b08de8.nq.gz
│   ├── d7ec80719e811367deed073c8c675554f7359788.nq.gz
│   ├── e500adfa9f2561a55ba82cc818c3ffc6e3578314.nq.gz
│   ├── e8987e66a7cc832f58cb5722694333f635238d43.nq.gz
│   ├── e8ff9b03701d83d453f32c2f4099c36f06ced230.nq.gz
│   ├── ee383854633b2659248419c684daad9745ccca0d.nq.gz
│   ├── ef8dcd2a11cc61f268c3b3650c7374f323555f69.nq.gz
│   ├── f6f95ecbb3a98549fb0f59bb81f543638a06c64f.nq.gz
│   ├── fdb4e31e1c3c7e4c812af28627506b3f8c66ce92.nq.gz
│   └── ffcaeec97871bed53e07ba6e4ba81d61bc4dd268.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 1cc115c87a80c1194083e4d16eb2c770eef28438.nq.gz
├── filetree
│   └── 1cc115c87a80c1194083e4d16eb2c770eef28438.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 45 files
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

[andfoy/winpty-rs](https://github.com/andfoy/winpty-rs)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
