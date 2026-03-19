## The Archive Model

We work with communities to document themselves and keep their own record.

This page outlines how we structure, maintain, and grow a shared audiovisual archive that remains useful, searchable, and owned by the people who create it.

---

### Two Types of Truth

The archive is maintained through a clear separation of responsibilities:

* **Structural truth (Archivist)**: What things are called and how they are organized. This includes file names, IDs, and canonical forms.

* **Semantic truth (Storyteller)**: What things mean. This includes topics, concepts, and how recordings are understood and connected.

This separation ensures the archive remains both coherent and flexible as it grows.

---

### Roles

#### Archivist

* Commitment: ~10 hrs/week
* Responsibility: Stewardship of archive structure, metadata integrity, and long-term usability

#### Storyteller

* Commitment: ~8 hrs/week
* Responsibility: Narrative layer, discoverability, and contextualization of recordings

---

### Core Workflow (Parallel Pipelines)

The Archivist and Storyteller operate as autonomous, non-blocking coordinator roles with independent workflows.

#### Archivist (Preservation Layer)

* Assign stable ID
* Upload recording
* Add baseline metadata
* Apply and enforce controlled vocabulary (topics, speakers)
* Enforce naming conventions (files, speakers, IDs)
* Add initial tags
* Ensure structural completeness of archive items

#### Storyteller (Interpretation Layer)

Working independently on available recordings:

* Titles
* Descriptions
* Key concepts discussed (3–6 items)
* Pull quotes
* Thematic grouping
* Cross-linking
* Timestamped chapter markers (segment indexing)
* Propose additions and refinements to controlled vocabulary

#### Coordination

* Archivist maintains structural integrity and consistency
* Storyteller enhances discoverability and narrative value
* Work happens in parallel on a shared archive

---

### Key Principles

* Parallel, non-blocking execution
* Shared standards over constant coordination
* Storytelling is layered on top of the archive
* Consistency over complexity

---

### Minimal Metadata Schema

Each recording includes:

1. **ID**: Stable unique identifier
2. **Title**: Clear, human-readable
3. **Speakers**: Names normalized to canonical format
4. **Event**: Event name
5. **Date**: Recording date (ISO 8601)
6. **Description**: Short summary
7. **Key Concepts Discussed**: 3–6 specific ideas
8. **Topics**: Standardized tags
9. **Links**: Related resources
10. **Chapters**: Time-coded segments with short descriptions
11. **License**: Attribution and usage rights

**Storage format:** YAML (source of truth in repo)

---

### Controlled Vocabulary

The archive uses a controlled vocabulary to maintain consistency over time.

* Topics and terminology are curated and normalized
* Naming conventions ensure consistency across files and records
* Vocabulary evolves through ongoing contributions informed by the content

Example:

* "zkp" → "zero-knowledge"
* "Vitalik" → "Vitalik Buterin"

---

### How We Work

Zk AV Club operates primarily asynchronously, with contributors working across time zones and contexts.

Roles are designed to be autonomous, with clear responsibilities and shared standards that keep the archive coherent as it grows.

---

### Outcome

Over time, this approach produces:

* A searchable archive (not a media dump)
* A navigable knowledge base (not just videos)
* A growing map of ideas across the FOSS and decentralized tech ecosystems

The goal is simple: recordings that remain useful long after they are created.

---

### Want to contribute?

We’re always looking for people who care about documentation, storytelling, and building shared knowledge.

→ See [Opportunities](/opportunities/)
