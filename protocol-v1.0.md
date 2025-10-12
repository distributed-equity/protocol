<!-- {{DEL:Licence version=1.0 license_uri=https://github.com/distributed-equity/licence/blob/main/del-v1.0.md copyright_holder="Kevin Ryan, Founder, DistributedEquity.org"}} -->
<!-- {{DEL:Holistic Quotable Summarizable UniquePurpose}} -->
<!-- {{DEL:UniquePurpose purpose="To define the operational protocol of the Distributed Equity License (DEL) v1.0, describing tag syntax, parsing behaviour, and permissible declaration methods."}} -->

# Distributed Equity License (DEL) — Protocol v1.0  
**Block #0000000002**

## 1  Overview

This document defines the **Distributed Equity License (DEL) Protocol v1.0**, describing how rights metadata are expressed, parsed, and validated through DEL tags or declarations.  
It serves as the operational framework for DEL implementations and registry systems.

The DEL Protocol specifies the **syntax**, **structure**, and **implementation rules** of DEL v1.0 as published in Block #0000000001.  
It ensures that both human and machine agents can interpret the meaning of rights encoded under the Distributed Equity License.

The protocol does **not** alter or supersede any legal provisions of the license; it functions as a technical and procedural companion.

---

## 2  Tagging Model

A DEL tag is a bounded rights declaration.  
Each tag begins with `{{DEL:` and ends with a matching closing tag `{{/DEL:TagName}}`.

### 2.1  Basic Structure

```text
{{DEL:<TagName> [attribute=value ...]}}
<optional metadata block in YAML or JSON>
<enclosed content>
{{/DEL:<TagName>}}
```

- **Opening Tag** — begins the scope.  
- **Metadata Block** — key–value pairs that describe license details.  
- **Closing Tag** — terminates the same `TagName`.  
- **Nesting** — inner tags override outer tags.  
- **Malformed Tags** — default to “All Rights Reserved”.

---

## 3  Declared Tags (From License v1.0)

Only the following tags are formally recognised by the DEL v1.0 protocol:

| Tag | Function |
|------|-----------|
| `Licence` | Root wrapper; declares version, license URI, and copyright holder. |
| `AITraining` | Permits use of content for AI / ML model training. |
| `AIRetrieval` | Permits indexing or retrieval-augmented generation. |
| `AITuning` | Permits model fine-tuning or adaptation. |
| `Summarizable` | Allows summarization, translation, or paraphrasing. |
| `NoSummarize` | Prohibits summarization; overrides `Summarizable`. |
| `Quotable` | Allows excerpting with attribution (≤ 250 words or 10 %). |
| `NoQuote` | Prohibits quoting; overrides `Quotable`. |
| `PublicDomain` | Irrevocably releases content to the public domain. |
| `Holistic` | Requires reuse of the complete work. |
| `UniquePurpose` | Declares a specific, single intended purpose for the work. |

---

## 4  Parsing and Validation Rules

1. **Recognition** — Parsers must detect `{{DEL:` and `{{/DEL:` boundaries.  
2. **Case Sensitivity** — Tag names are case-insensitive.  
3. **Conflict Resolution** — The most restrictive applicable tag prevails.  
4. **Unknown Tags** — Must be ignored but treated as non-permissive.  
5. **Malformed Structure** — If a closing tag is missing or nesting is invalid, all enclosed rights are voided.  
6. **Metadata Errors** — If metadata cannot be parsed, the affected content defaults to *All Rights Reserved*.

---

## 5  Metadata Requirements

Each `Licence` block MUST include:

| Field | Requirement | Purpose |
|--------|--------------|----------|
| `version` | Required | Identifies the DEL version. |
| `license_uri` | Required | Resolves to the canonical license text. |
| `copyright_holder` | Required | Names the legal rights owner. |

Optional fields — `content_hash`, `timestamp`, `wallet`, and others — may be used for provenance, payment, or verification, but omission does not invalidate the license unless a referenced flag (e.g. `micropay`) depends on it.

---

## 6  Behaviour by Tag

### 6.1  AITraining / AIRetrieval / AITuning
Presence implies permission.  
Attributes such as `permitted`, `cost_per_kb`, and `btc` may further constrain or monetise use.

### 6.2  Summarizable / NoSummarize  
`Summarizable` permits summarisation unless a nested `NoSummarize` is present.

### 6.3  Quotable / NoQuote  
`Quotable` allows excerpting up to 250 words or 10 %.  
Nested `NoQuote` blocks override.

### 6.4  Holistic  
Requires reuse of the entire work unless a nested `Quotable` section authorises smaller excerpts.

### 6.5  UniquePurpose  
Specifies that reuse for the same stated purpose requires separate permission.  
The `purpose` field is mandatory when this tag is used.

### 6.6  PublicDomain  
Supersedes all other rights declarations and is irrevocable.

---

## 7  Alternative Declaration Methods

While inline tags remain the canonical format, a Licensor may apply DEL v1.0 to an entire work through a **top-level declaration** placed in front-matter, metadata headers, or manifest files.

### 7.1  Requirements

A valid top-level declaration MUST include:

| Field | Description |
|--------|-------------|
| `License Version` | e.g. “Distributed Equity License v1.0” |
| `License URI` | Canonical link to the license text |
| `Copyright Holder` | Author or rights owner |
| `Declared Flags` | One or more of: `AITraining`, `AIRetrieval`, `AITuning`, `Summarizable`, `NoSummarize`, `Quotable`, `NoQuote`, `PublicDomain`, `Holistic`, `UniquePurpose` |
| `Purpose` | If `UniquePurpose` is declared, this field is mandatory |

### 7.2  Effect

Such a declaration confers the same rights as if equivalent DEL tags wrapped the entire content body.  
Omission of mandatory fields renders the declaration **non-machine-enforceable**, defaulting to *All Rights Reserved* for safety.

### 7.3  Example Declaration

```text
This work is released under the Distributed Equity License (DEL) v1.0  
Flags: Quotable, Summarizable, AITraining, AIRetrieval, AITuning, Holistic, UniquePurpose  
License URI: https://github.com/distributed-equity/licence/blob/main/del-v1.0.md  
Copyright Holder: Kevin Ryan, Founder, DistributedEquity.org  
Purpose: To articulate the ethical foundation of the Distributed Equity License.
```

Agents and crawlers MAY treat this header as equivalent to a root-scoped `Licence` tag enclosing the full text.

---

## 8  Implementation Guidelines

1. Parsers should recognise both **inline tags** and **header declarations**.  
2. When both are present, inline tags take precedence for their scope.  
3. Rights propagation should favour restrictive interpretation to avoid unintentional permissions.  
4. Validation tools should log unresolved or malformed tags for human review.  
5. Future versions (≥ v1.1) may introduce dedicated tags for header declarations and micropayment workflows.

---

## 9  Versioning and Provenance

- **Block #0000000000** — Distributed Equity Manifesto v1.0  
- **Block #0000000001** — Distributed Equity License v1.0  
- **Block #0000000002** — Distributed Equity Protocol v1.0 (this document)  
- **Block #0000000003 +** — Works licensed under DEL by creators and organisations  

Each block should include a content hash and timestamp for verification.

---

```yaml
Signed and encoded as Block #0000000002
DistributedEquity.org
Version 1.0 (Protocol Definition)
```

<!-- {{/DEL:UniquePurpose}} -->
<!-- {{/DEL:Holistic}} -->
<!-- {{/DEL:Licence}} -->
