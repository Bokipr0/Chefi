# LLM Wiki — Schema & Operating Manual

This vault is an **LLM-maintained knowledge base**. Lior curates sources and asks
questions. The LLM writes and maintains every page in `wiki/`, every map in
`maps/`, plus `index.md` and `log.md`.

The point of this vault is not storage — it is **connection**. A fact filed
without at least one justified, typed link to existing knowledge has failed to be
ingested. Every ingest ends with the question: *what does this change about what
I already believed?*

---

## 1. Layers

| Layer | Path | Who writes it |
|---|---|---|
| Raw sources (immutable) | `raw/`, images in `raw/assets/` | Lior only. **Never edit or delete.** |
| The wiki | `wiki/**` | LLM only |
| Maps (arrowed graphs) | `maps/*.canvas`, `maps/*.md` | LLM only |
| Catalog | `index.md` | LLM only |
| Timeline | `log.md` | LLM only (append-only) |
| This schema | `CLAUDE.md` | Co-evolved by Lior + LLM |

### Page types and where they live

| Type | Folder | What it is | Granularity |
|---|---|---|---|
| `source` | `wiki/sources/` | One page per raw source: provenance, faithful summary, key claims, quotes | 1 per file in `raw/` |
| `note` | `wiki/notes/` | One **atomic** idea, extracted from a source and rewritten in the vault's own voice | 1 idea = 1 page |
| `entity` | `wiki/entities/` | A person, org, place, product, tool, dataset, event | 1 per real thing |
| `concept` | `wiki/concepts/` | An idea, theme, mechanism, method, pattern | 1 per idea |
| `question` | `wiki/questions/` | An open question the vault cannot yet answer | 1 per question |
| `synthesis` | `wiki/syntheses/` | Cross-cutting analysis; an answer to a query, filed back | 1 per thesis |

Filenames are `kebab-case.md` and stable. Renaming is allowed only via Obsidian
(so links update) or by rewriting every inbound link in the same pass.

**Atomicity rule.** If a page's title needs "and" to be accurate, split it. A
note should be one claim you could argue with. Small pages make more, and more
meaningful, edges — which is the whole point.

---

## 2. Frontmatter (required on every wiki page)

```yaml
---
id: kebab-slug              # == filename without .md
title: Human Readable Title
type: note                  # source | note | entity | concept | question | synthesis
meta-sector: technical          # problem | technical | design | user-research | market | storytelling
created: 2026-08-30
updated: 2026-08-30
status: seed                # seed | developing | stable | contested | superseded
confidence: medium          # low | medium | high — in this page's own claims
weight: 50                  # optional: 1–100; importance/prominence in graph (see §2a)
tags: [topic/x, method/y]
sources: ["[[wiki/sources/some-source]]"]   # provenance; [] for pure syntheses
relations:
  - rel: contradicts
    to: "[[wiki/notes/older-claim]]"
    why: Reports a 3x higher rate under the same measurement protocol.
    basis: explicit          # explicit | inferred | speculative
    confidence: high
    found: 2026-08-30
---
```

- `[[wikilinks]]` in frontmatter **are** real links: Obsidian resolves them and
  they appear in graph view. That is why relations live here.
- `updated` changes on every touch. `created` never changes.
- `status: contested` is set on both pages of any `contradicts` pair.
- `status: superseded` requires a `superseded-by` relation. Never delete the old
  page — the vault must remember what it used to believe.
- `weight` (optional): numeric 1–100 indicating importance/prominence in the knowledge graph. Higher = more dominant node. See §2a below.

**Meta-sector.** Every wiki page carries one `meta-sector`, one of six. `problem` is the centre of the map: the question the product answers, and the open questions around it. `technical` (how the device works), `market` (who buys, competes, prices), `design` (what it should do, how it earns trust), `user-research` (what people do, say and intend), `storytelling` (narrative, inspiration, how it is told). `problem` holds the core problem and the open questions it raises. The canvas groups pages by meta-sector, and `index.md` lists them that way. Cross-sector edges are the interesting ones; keep them.

### 2a. Node Weighting

Pages can have a `weight` field (1–100) to signal importance:

| Weight Range | Meaning | Examples |
|---|---|---|
| 90–100 | **Primary nodes**: central perspectives or organizational spines | Lior, Amanda, Lior-and-Amanda synthesis |
| 80–89 | **Anchor nodes**: key to each perspective's taste | Rust in Call, Kill Bill, Progressive Rock |
| 50–79 | **Core material**: major concepts, source traditions | King Crimson, Tarantino, Synthesis Filmmaking |
| 20–49 | **Supporting material**: derivative or auxiliary entities | Individual films, stylistic concepts |
| 1–19 | **Peripheral**: context only; rarely queried | Specific actors, minor traditions |

**Visual effect in Canvas:** Higher-weight nodes should be rendered larger (width 400+, height 100+) to signal dominance. See `maps/lior-and-amanda-master.canvas` for example.

**LLM behavior:** When ingesting new material, prioritize connections to high-weight nodes. New discoveries should flow through established anchors (Lior's taste, Amanda's taste) before creating peripheral pages.

**Promotion:** A page starts low weight (20–30). Promote to 50+ only after earning 3+ connections to high-weight nodes. Promote to 80+ only if it becomes a sustained anchor for discovery.

---

## 3. The relation ontology

Direction matters. Always write the relation from **this page → the other page**,
and always add the inverse on the other page in the same edit. An edge that
exists on only one side is a bug.

### Structural
| `rel` | Inverse | Meaning |
|---|---|---|
| `instance-of` | `has-instance` | This is a specific case of that |
| `part-of` | `has-part` | Composition / containment |
| `refines` | `generalized-by` | Narrower, more precise version |

### Causal / functional
| `rel` | Inverse | Meaning |
|---|---|---|
| `causes` | `caused-by` | Directly produces |
| `enables` | `enabled-by` | Makes possible, not sufficient alone |
| `blocks` | `blocked-by` | Prevents or constrains |
| `mechanism-of` | `has-mechanism` | *How* the other thing works |

### Evidential — the load-bearing ones
| `rel` | Inverse | Meaning |
|---|---|---|
| `supports` | `supported-by` | Evidence for |
| `contradicts` | `contradicts` | Symmetric. **Always flag; never silently resolve.** |
| `qualifies` | `qualified-by` | True only under conditions stated here |
| `measures` | `measured-by` | Operationalizes / quantifies |
| `supersedes` | `superseded-by` | Newer, better information replaces older |

### Associative
| `rel` | Inverse | Meaning |
|---|---|---|
| `analogous-to` | `analogous-to` | Symmetric. Same *structure*, different domain. Highest-value inferred edge. |
| `contrasts-with` | `contrasts-with` | Symmetric. Instructive difference. |
| `co-occurs-with` | `co-occurs-with` | Symmetric. Empirical, no known mechanism. Weakest edge — prefer to upgrade or drop. |

### Discourse
| `rel` | Inverse | Meaning |
|---|---|---|
| `answers` | `answered-by` | Resolves a `question` page |
| `raises` | `raised-by` | Opens a new question |
| `sourced-from` | `yields` | Provenance: note → source |

### Derivational
*Added 2026-08-30 during the first ingest: tracking what a work is built from
needed its own family. Provenance (`sourced-from`) is about which file a claim
came from; derivation is about which prior work an idea descends from.*

| `rel` | Inverse | Meaning |
|---|---|---|
| `derived-from` | `basis-for` | This idea/text descends from that prior work |
| `expresses` | `expressed-by` | A character/work articulates a named idea |

**`basis` is not optional.** `explicit` = the source states it. `inferred` = the
LLM reasoned it from two or more pages. `speculative` = a hunch worth recording.
Speculative edges are welcome, but they must be labeled, so the vault never
launders a guess into a fact.

---

## 4. How to actually find connections

This is the core skill. Do not link by keyword overlap — that produces a hairball
of useless edges. Work through these passes, in order, on every ingest.

1. **Provenance** (mechanical) — link every note to its source, every source to
   the entities and concepts it mentions.
2. **Name collision** — grep the vault for every proper noun and technical term
   in the new material. Existing page → link. No page but mentioned 3+ times
   across the vault → create the page.
3. **Taxonomic** — read `index.md`. Where does this sit in the existing
   hierarchy? Find its parent (`instance-of`, `part-of`) and its siblings
   (`contrasts-with`).
4. **Evidential sweep** — this is the pass most systems skip. For each claim in
   the new material, search for existing claims about *the same variable*. Then
   decide: `supports`, `contradicts`, `qualifies`, or `supersedes`. If the new
   source is more recent or better-evidenced, `supersedes`; if it merely
   disagrees, `contradicts` and mark both pages `contested`.
5. **Causal chaining** — does this fill a gap in an existing chain? Look for a
   page that asserts an effect with no known mechanism, and check whether this
   supplies it (`mechanism-of`).
6. **Structural analogy** — strip the domain vocabulary from the new idea and ask
   what its abstract shape is: a feedback loop, a bottleneck, a
   principal–agent problem, a phase transition, a compounding process, a
   maintenance-cost-exceeds-value collapse. Then look for that shape elsewhere in
   the vault. These edges are the reason to keep a wiki instead of a folder.
7. **Question sweep** — re-read `wiki/questions/`. Does this answer any of them?
   Does it raise a new one? File it.

Then prune. **A page should carry roughly 3–7 typed relations.** If you have
more, keep the ones that would change a conclusion and drop the decorative ones.
Prefer one `contradicts` over ten `co-occurs-with`.

Every `why` field must state *why the connection holds*, not restate what the
pages are about. "Both discuss maintenance" is useless. "Both describe systems
that collapse when upkeep cost outgrows perceived value" is an edge.

---

## 5. Operations

### Ingest
Trigger: a new file appears in `raw/`, or Lior pastes text or a link.

1. Read the source fully. If it has local images in `raw/assets/`, read the text
   first, then view the images that matter.
2. **Report before writing** — a short chat summary: what this is, the 3–6 claims
   worth keeping, and the connections found in §4, each with its `why`. Wait for
   Lior unless told to run unsupervised.
3. Write `wiki/sources/<slug>.md`.
4. Write or update the atomic `wiki/notes/` pages.
5. Update every touched `entity` / `concept` page — and add the **inverse
   relation on each one**. A real ingest touches 5–15 files.
6. Update `index.md`.
7. Update `maps/connections.canvas` with the new arrows (§6).
8. Append to `log.md`.

If the source is pasted text with no file, save it to `raw/` first. Sources are
the vault's ground truth; nothing enters the wiki without provenance.

### Query
1. Read `index.md`, then drill into the relevant pages, then follow their
   relations one hop out. The relations *are* the retrieval index.
2. Answer with `[[wikilinks]]` as citations, and distinguish what a source says
   from what the vault inferred.
3. If the answer is non-trivial, **offer to file it** as
   `wiki/syntheses/<slug>.md`. Explorations should compound like sources do.
4. If the vault cannot answer, write a `wiki/questions/` page instead of guessing.

### Lint
Run on request, or when `log.md` shows ~10 ingests since the last pass. Check for:
- one-sided relations (inverse missing) — the most common defect
- `contradicts` pairs where both pages lack `status: contested`
- orphans: no inbound links
- hubs: 15+ inbound links → the page is probably several pages
- terms mentioned across 3+ pages with no page of their own
- stale `status: stable` pages older than the newest contradicting source
- clusters with no edges between them — a missed analogy, worth an explicit look
- `speculative` edges that new evidence can now promote or kill

Output a findings list with proposed fixes. Do not apply destructive fixes
without asking.

---

## 6. Showing connections as arrows

Graph view shows edges but **not direction**. So direction and relation type live
in Canvas maps, which do render labeled arrows.

- `maps/connections.canvas` — the running map. Every ingest adds its new nodes
  and arrows here.
- `maps/<topic>.canvas` — focused maps built on request.
- `maps/<topic>-moc.md` — a Map of Content: prose page grouping links by relation
  type, for reading rather than viewing.

Canvas is plain JSON. Nodes reference files; edges carry `label` and direction:

```json
{
  "nodes": [
    {"id":"n1","type":"file","file":"wiki/concepts/x.md","x":0,"y":0,"width":320,"height":100},
    {"id":"n2","type":"file","file":"wiki/notes/y.md","x":480,"y":0,"width":320,"height":100}
  ],
  "edges": [
    {"id":"e1","fromNode":"n1","fromSide":"right","toNode":"n2","toSide":"left",
     "label":"causes","color":"1"}
  ]
}
```

Edge colors by relation family — keep this consistent, it makes the map readable
at a glance:

| Color | Family |
|---|---|
| `"1"` red | `contradicts`, `blocks` |
| `"2"` orange | `supersedes`, `qualifies` |
| `"4"` green | `supports`, `enables`, `causes` |
| `"5"` cyan | `analogous-to`, `contrasts-with` |
| `"6"` purple | structural: `instance-of`, `part-of`, `refines` |
| *(none)* grey | `co-occurs-with`, `sourced-from` |

Dashed intent for `speculative` edges: prefix the label with `?` (e.g.
`?analogous-to`) — Canvas has no dash style, so the marker goes in the label.

Layout: place structural parents above children, causal chains left→right,
contradictions side by side on the same row. Space nodes ~480px apart
horizontally, ~200px vertically, so the canvas stays legible as it grows.

---

## 7. Conventions

- **Voice:** plain, declarative, compressed. No hedging filler, no "it is
  important to note".
- **Rewrite, don't paste.** Notes are in the vault's voice. Verbatim text goes in
  the source page under `## Quotes`, with a locator.
- **Attribute uncertainty.** "X claims", "one 2024 survey found", "inferred here".
- **Absolute dates only.** "March 2026", never "last spring".
- **Never fabricate provenance.** If unsure which source a claim came from, say so
  in the page.
- **Contradictions are assets.** Surface them prominently; do not average them
  away into a bland middle.
- **Preserve history.** Supersede, don't overwrite. The vault should be able to
  show how a belief changed.

### Standard body layout

```markdown
# Title

One-paragraph answer to "what is this and why does it matter".

## Detail
...

## Connections
- **contradicts** [[wiki/notes/older-claim]] — 3x higher rate, same protocol.
- **analogous-to** [[wiki/concepts/other]] — both are maintenance-cost collapses.

## Open questions
- [[wiki/questions/does-x-hold-at-scale]]

## Sources
- [[wiki/sources/some-source]]
```

The `## Connections` section mirrors `relations:` in frontmatter. Keep them in
sync — frontmatter is machine-readable, the body is for reading.

---

## 8. Tooling notes

- **Installed:** Excalidraw, Local REST API. Canvas is core, no install needed.
- **Worth enabling:** Dataview (turns `relations:` into live tables — e.g. a
  "contested claims" dashboard), Graph view filters by `tags`.
- **Search:** `rg` over `wiki/` is sufficient at this scale. If the vault passes
  ~300 pages, add a local hybrid search tool and document it here.
- **Git:** the vault is not yet a repo. Worth `git init` — free version history
  of how the knowledge base evolved.

---

## 9. Every response ends with

1. **Files touched** — path + one clause on what changed.
2. **New connections** — `A --rel--> B` with the `why` and `basis`, so Lior can
   audit the reasoning rather than trust it.
3. **What this changed** — any belief now contested, superseded, or newly
   supported.
4. **Next** — the sharpest 1–2 questions or the most useful source to find next.
