<!-- 
Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0)
https://creativecommons.org/licenses/by/4.0/

DEL v1.0 Supplementary Terms for AI and Automated Systems
https://github.com/distributed-equity/license/blob/main/del-v1.0.md

{{DEL:License version=1.0 license="CC BY 4.0" copyright_holder="Kevin Ryan, DistributedEquity.org"}}
{{DEL:aitraining airetrieval aituning attributable quotable summarizable holistic uniquepurpose}}

author: "Kevin Ryan"
title: "Distributed Equity Protocol (DEL Protocol) v1.0"
purpose: "Technical implementation specification defining tag syntax, metadata schemas, parsing rules, and compliance mechanisms for operationalizing the Distributed Equity License framework in machine-readable form"
url: "https://github.com/distributed-equity/protocol/blob/main/del-protocol-v1.0.md"
date: "2025-10-15"
version: "1.0.0"
language: "en"
del_version: "1.0"
del_uri: "https://github.com/distributed-equity/license/blob/main/del-v1.0.md"
license_uri: "https://creativecommons.org/licenses/by/4.0/"
block_number: "0002"
depends_on: "DEL License v1.0 (#0000000001), DEL Manifesto (#000000000)"
-->

# Distributed Equity Protocol (DEL Protocol) v1.0
## Implementation Framework for Machine-Readable Licensing

---

**Release Notes - DEL Protocol v1.0**

This is the initial release of the Distributed Equity Protocol, providing technical specifications for implementing the Distributed Equity License (DEL) v1.0 framework.

**Status**: Early adoption phase  
**Stability**: Experimental - Breaking changes may occur in v2.0  
**Seeking**: Implementation feedback, parser contributions, registry operators

See Section 12 for important limitations and disclaimers.

---

**Protocol License**: This protocol document is licensed under CC BY 4.0 and DEL v1.0.

**Author**: Kevin Ryan, Founder, [DistributedEquity.org](https://distributedequity.org)

**Version**: 1.0

**Block Number**: #0000000002

**Dependencies**: DEL License v1.0 (#0000000001), DEL Manifesto (#0000000000)

---

## Table of Contents

1. [Introduction and Scope](#1-introduction-and-scope)
2. [Protocol Architecture](#2-protocol-architecture)
3. [Technical Specification](#3-technical-specification)
4. [Metadata Schema](#4-metadata-schema)
5. [Tag Parsing and Validation](#5-tag-parsing-and-validation)
6. [Implementation Guidelines](#6-implementation-guidelines)
7. [Compliance and Verification](#7-compliance-and-verification)
8. [Payment Protocol](#8-payment-protocol)
9. [Registry and Discovery](#9-registry-and-discovery)
10. [Versioning and Governance](#10-versioning-and-governance)
11. [Security Considerations](#11-security-considerations)
12. [Protocol Status and Limitations](#12-protocol-status-and-limitations)
13. [Implementation Resources](#13-implementation-resources)
14. [Appendices](#14-appendices)

---

## 1. Introduction and Scope

### 1.1 Purpose

The **Distributed Equity Protocol (DEL Protocol)** defines the technical implementation framework for the Distributed Equity License (DEL) v1.0. This protocol enables:

1. **Machine-readable license declarations** that automated systems can parse and respect
2. **Standardized metadata formats** for rights, attribution, and compensation
3. **Interoperable tag syntax** across different content types and platforms
4. **Verifiable compliance mechanisms** for AI systems and content platforms
5. **Micropayment infrastructure** for fair creator compensation

### 1.2 Relationship to DEL License

This protocol **implements** the legal framework established by the DEL License v1.0 (#0001):

- **DEL License v1.0** provides the legal terms, definitions, rights grants, and obligations
- **DEL Protocol v1.0** specifies how to technically express, parse, validate, and honor those terms

The protocol is subordinate to the license. In any conflict, the license terms prevail.

### 1.3 Design Principles

The DEL Protocol adheres to these core principles:

1. **Compatibility First**: Works alongside existing open licenses without replacement
2. **Machine Readability**: Structured for automated parsing by AI systems
3. **Human Clarity**: Readable and understandable by content creators
4. **Minimal Overhead**: Low implementation burden for both creators and consumers
5. **Forward Compatible**: Extensible without breaking existing implementations
6. **Fail-Safe Defaults**: Unknown or malformed tags default to restrictive interpretation
7. **Attribution Preservation**: Maintains creator identity through processing pipelines
8. **Economic Fairness**: Enables optional micropayments for automated usage

### 1.4 Scope of Application

This protocol applies to:

- **Content Types**: Source code, documentation, articles, books, datasets, media
- **Automated Systems**: AI/ML models, RAG systems, embedding generators, code assistants
- **Platforms**: Code repositories, content management systems, AI training pipelines
- **Actors**: Content creators, AI developers, platform operators, registry services

### 1.5 Normative References

- **DEL License v1.0** (#0001): Legal framework and terminology
- **RFC 2119**: Key words for use in RFCs (MUST, SHOULD, MAY)
- **YAML 1.2**: Metadata serialization format
- **JSON Schema**: Metadata validation
- **SPDX 2.3**: License identifier compatibility
- **Bitcoin BIP-21**: Payment URI scheme

---

## 2. Protocol Architecture

### 2.1 Layered Design

The DEL Protocol operates in three layers:

```
┌─────────────────────────────────────────┐
│   Legal Layer (DEL License v1.0)        │
│   - Rights grants and restrictions      │
│   - Legal definitions and obligations   │
└─────────────────────────────────────────┘
                   ↓
┌─────────────────────────────────────────┐
│   Protocol Layer (DEL Protocol v1.0)    │
│   - Tag syntax and metadata schema      │
│   - Parsing rules and validation        │
│   - Payment and attribution protocols   │
└─────────────────────────────────────────┘
                   ↓
┌─────────────────────────────────────────┐
│   Implementation Layer                  │
│   - Parser libraries and validators     │
│   - Platform integrations               │
│   - Registry services                   │
└─────────────────────────────────────────┘
```

### 2.2 Block Structure and Versioning

The DEL ecosystem uses a block-based versioning system:

| Block # | Document | Version | Status |
|---------|----------|---------|--------|
| #0000000000 | DEL Manifesto | 1.0 | Published |
| #0000000001 | DEL License | 1.0 | Published |
| #0000000002 | DEL Protocol | 1.0 | **This document** |
| #0000000003+ | Future extensions | TBD | TBD |

**Block Numbering Rules:**
- Core documents use sequential block numbers
- Each block is immutable once published
- New versions create new blocks (e.g., License v2.0 → #0000000010)
- Block hashes provide cryptographic verification

### 2.3 Component Overview

The protocol defines five primary components:

1. **Tag Syntax**: Inline markers (`{{DEL:...}}`) embedded in content
2. **Metadata Schema**: Structured YAML/JSON for rights declarations
3. **Parser Specification**: Rules for extracting and interpreting tags
4. **Validation Framework**: Methods for verifying correctness and compliance
5. **Registry Protocol**: Discovery and verification services

---

## 3. Technical Specification

### 3.1 Tag Syntax Definition

#### 3.1.1 Core Syntax

DEL tags use double-curly-brace delimiters for machine readability:

```
{{DEL:flag1 flag2 key=value}}
```

**Syntax Rules:**
- Tags MUST begin with `{{DEL:` (case-sensitive)
- Tags MUST end with `}}`
- Whitespace after `DEL:` is optional
- Flags are space-separated
- Key-value pairs use `=` with optional quotes around values
- Closing tags MUST mirror the primary flag: `{{/DEL:flag1}}`

#### 3.1.2 Tag Types

**License Declaration Tag** (REQUIRED at document root):
```
{{DEL:License version=1.0 license=MIT copyright_holder="Jane Developer"}}
```

**Permission Scope Tags**:
```
{{DEL:aitraining airetrieval attributable}}
[Content within scope]
{{/DEL:aitraining}}
```

**Restriction Tags**:
```
{{DEL:noai}}
[Restricted content]
{{/DEL:noai}}
```

**Inline Flags** (no closing tag required):
```
{{DEL:quotable summarizable}}
```

#### 3.1.3 Nesting Behavior

Tags MAY be nested to provide granular control:

```
{{DEL:License version=1.0 license=MIT copyright_holder="Author"}}
  {{DEL:aitraining airetrieval attributable}}
  
    # Public Section
    This content allows AI training.
    
    {{DEL:noai}}
      ## Restricted Subsection
      This specific section prohibits AI use.
    {{/DEL:noai}}
    
    More public content.
    
  {{/DEL:aitraining}}
{{/DEL:License}}
```

**Nesting Rules:**
1. Inner tags override outer tags within their scope
2. Closing tags MUST match opening tags
3. Tags MUST close before their parent closes
4. Malformed nesting MUST be treated as error (fail restrictive)

### 3.2 Canonical Flag Set

#### 3.2.1 Permission Flags

These flags grant specific rights for AI/automated use:

| Flag | Semantic Meaning | Scope |
|------|------------------|-------|
| `aitraining` | Permits ML model training, fine-tuning, pattern learning | Training pipeline |
| `airetrieval` | Permits RAG, embeddings, semantic search, context injection | Retrieval systems |
| `aituning` | Permits RLHF, instruction tuning, behavioral adaptation | Model tuning |
| `quotable` | Allows quotation (≤250 words or 10%, whichever smaller) | Output generation |
| `summarizable` | Allows AI-generated summaries in automated outputs | Output generation |
| `attributable` | Requires explicit attribution (mandatory if present) | All AI use |
| `micropay` | Enables optional micropayment-based usage | All AI use |
| `holistic` | Work should be considered as unified whole | Content processing |
| `uniquepurpose` | Declares distinct creative/moral purpose | Fair use context |

#### 3.2.2 Restriction Flags

These flags narrow or prohibit AI/automated use:

| Flag | Semantic Meaning | Override Behavior |
|------|------------------|-------------------|
| `noai` | Prohibits ALL AI/ML use (training, retrieval, tuning) | Overrides all permission flags |
| `notraining` | Prohibits model training specifically | Overrides `aitraining` only |
| `noquote` | Prohibits direct quotation in outputs | Overrides `quotable` |
| `nosummarize` | Prohibits AI-generated summaries | Overrides `summarizable` |
| `noderivatives` | Prohibits AI-generated derivatives | Restricts training and tuning |
| `noncommercial` | Prohibits commercial AI use | Applies to all AI operations |

#### 3.2.3 Flag Interaction Matrix

When multiple flags are present:

```
PRIORITY ORDER (highest to lowest):
1. noai          (blocks everything)
2. Specific no* flags (block specific operations)
3. Permission flags   (grant specific rights)
4. Default           (no rights granted)
```

**Conflict Resolution:**
- `noai` + any permission flag → `noai` wins (no AI use)
- `notraining` + `aitraining` → `notraining` wins (no training)
- Nested restrictive flag + parent permissive flag → restriction applies to nested scope only

### 3.3 Tag Placement Conventions

#### 3.3.1 Code Files

**Python:**
```python
"""
Module: widget_optimizer.py

License: MIT (https://opensource.org/licenses/MIT)
DEL v1.0 Supplementary Terms Apply

{{DEL:License version=1.0 license=MIT copyright_holder="Your Name"}}
{{DEL:aitraining airetrieval aituning attributable}}
"""

def optimize_widget(config):
    pass
```

**JavaScript:**
```javascript
/*
 * widget-optimizer.js
 * Copyright (c) 2025 Your Name
 * 
 * Licensed under MIT + DEL v1.0
 * {{DEL:License version=1.0 license=MIT copyright_holder="Your Name"}}
 * {{DEL:aitraining airetrieval attributable}}
 */

function optimizeWidget(config) {
  // implementation
}
```

#### 3.3.2 Markdown Documents

```markdown
---
title: "Guide to Machine Learning"
author: "Dr. Sarah Chen"
license: "CC BY 4.0 + DEL v1.0"
---

<!-- {{DEL:License version=1.0 license="CC BY 4.0" copyright_holder="Dr. Sarah Chen"}} -->
<!-- {{DEL:aitraining airetrieval attributable quotable}} -->

# Guide to Machine Learning

Content here...
```

#### 3.3.3 HTML/Web Content

**In `<head>` section:**
```html
<head>
  <meta name="license" content="Apache-2.0">
  <meta name="del-version" content="1.0">
  <meta name="del-flags" content="aitraining,airetrieval,attributable">
  <meta name="copyright" content="Your Organization">
  <meta name="del-payment-btc" content="bc1q...">
  <meta name="del-cost-per-kb" content="0.00001">
</head>
```

**In HTML comments:**
```html
<!-- 
  Licensed under CC BY 4.0
  DEL v1.0 Supplementary Terms
  {{DEL:License version=1.0 license="CC BY 4.0" copyright_holder="Author Name"}}
  {{DEL:airetrieval attributable quotable}}
-->
```

#### 3.3.4 API Responses

**HTTP Headers:**
```http
X-License: MIT
X-DEL-Version: 1.0
X-DEL-Flags: aitraining,airetrieval,attributable
X-Copyright-Holder: Your Organization
X-DEL-Cost-Per-KB: 0.00001
X-DEL-Payment-BTC: bc1q...
```

**JSON API Response:**
```json
{
  "data": { ... },
  "metadata": {
    "license": "MIT",
    "del_version": "1.0",
    "del_flags": ["aitraining", "airetrieval", "attributable"],
    "copyright_holder": "Your Organization"
  }
}
```

---

## 4. Metadata Schema

### 4.1 Schema Definition

DEL metadata MUST be valid YAML 1.2 or JSON. The canonical schema uses YAML:

```yaml
# REQUIRED FIELDS
copyright_holder: "string"  # Name of rights holder
license: "string"           # SPDX identifier or full name of base license

# RECOMMENDED FIELDS
author: "string"            # Creator name (may differ from copyright holder)
license_uri: "string"       # URL to full base license text
del_version: "string"       # DEL version (e.g., "1.0")
del_uri: "string"           # URL to DEL protocol/license docs

# PERMISSION FLAGS
license_flags: 
  - "aitraining"
  - "airetrieval"
  - "aituning"
  - "attributable"
  - "quotable"
  - "summarizable"
  - "micropay"
  - "holistic"
  - "uniquepurpose"

# RESTRICTION FLAGS (overrides permissions)
restriction_flags:
  - "noai"
  - "notraining"
  - "noquote"
  - "nosummarize"
  - "noderivatives"
  - "noncommercial"

# PAYMENT FIELDS (optional)
cost_per_kb: 0.00001        # Numeric, USD per kilobyte
payment_addresses:
  btc: "string"             # Bitcoin address
  eth: "string"             # Ethereum address
  paypal: "string"          # PayPal email or payment URL
  stripe: "string"          # Stripe payment link
  custom: "string"          # Other payment method

# DESCRIPTIVE FIELDS (optional)
title: "string"             # Work title
purpose: "string"           # Description of work's purpose
url: "string"               # Canonical URL for the work
date: "YYYY-MM-DD"          # Publication or update date
version: "string"           # Work version
language: "string"          # ISO 639-1 code

# DERIVATIVE TRACKING (optional)
derived_from: "string"      # URL or identifier of source work
derived_date: "YYYY-MM-DD"  # Date of derivation
modifications: "string"     # Description of changes
```

### 4.2 Field Specifications

#### 4.2.1 Required Fields

**`copyright_holder`** (string, REQUIRED)
- MUST contain the legal name of the copyright holder
- MAY be an individual or organization
- MUST be present in all DEL declarations
- Example: `"Jane Developer"`, `"Acme Corporation"`

**`license`** (string, REQUIRED)
- MUST identify the base license
- SHOULD use SPDX identifiers when available (e.g., `"MIT"`, `"Apache-2.0"`, `"CC-BY-4.0"`)
- MAY use full license name if SPDX identifier unavailable
- Example: `"MIT"`, `"Creative Commons Attribution 4.0"`

#### 4.2.2 Recommended Fields

**`author`** (string, RECOMMENDED)
- Creator's name (may differ from copyright holder)
- Used for attribution purposes
- Example: `"Dr. Sarah Chen"`

**`license_uri`** (string, RECOMMENDED)
- Direct link to full base license text
- SHOULD use canonical license URLs
- Example: `"https://opensource.org/licenses/MIT"`

**`del_version`** (string, RECOMMENDED)
- DEL version number applied to this work
- Format: `"MAJOR.MINOR"` (e.g., `"1.0"`)
- Defaults to latest if omitted

**`del_uri`** (string, RECOMMENDED)
- Link to DEL protocol or license documentation
- Example: `"https://github.com/distributed-equity/license/blob/main/del-v1.0.md"`

#### 4.2.3 Permission and Restriction Flags

**`license_flags`** (array of strings)
- Contains permission flags as defined in Section 3.2.1
- Each flag MUST be a recognized permission flag
- Empty array or omission means no special permissions granted
- Example: `["aitraining", "airetrieval", "attributable"]`

**`restriction_flags`** (array of strings)
- Contains restriction flags as defined in Section 3.2.2
- Overrides conflicting permission flags
- Example: `["noncommercial", "notraining"]`

#### 4.2.4 Payment Fields

**`cost_per_kb`** (number)
- Payment rate per kilobyte of content used
- Denominated in USD
- MUST be non-negative
- Example: `0.00001` (1 cent per 1000 KB)

**`payment_addresses`** (object)
- Contains payment method identifiers
- Each key is a payment method type
- Values are addresses/URLs valid for that method
- Supported keys: `btc`, `eth`, `paypal`, `stripe`, `custom`

### 4.3 Validation Rules

Parsers MUST validate metadata according to these rules:

1. **Required field presence**: `copyright_holder` and `license` MUST be present
2. **Type checking**: All fields MUST match their specified types
3. **Flag recognition**: Unknown flags SHOULD trigger warnings (forward compatibility)
4. **URI format**: All `*_uri` fields MUST be valid URLs if present
5. **Date format**: All `*_date` fields MUST use ISO 8601 format (YYYY-MM-DD)
6. **Payment validation**: If `micropay` flag present, MUST have valid `cost_per_kb` and at least one payment address
7. **Flag conflict detection**: Restrictive flags override permissive flags

### 4.4 Schema Versions

Future protocol versions MAY extend this schema. Parsers SHOULD:
- Ignore unknown fields (forward compatibility)
- Warn on unknown flags
- Fail safely when critical validation fails

---

## 5. Tag Parsing and Validation

### 5.1 Parser Requirements

Implementations MUST provide:

1. **Tag Recognition**: Detect `{{DEL:...}}` markers in content
2. **Metadata Extraction**: Parse YAML/JSON metadata blocks
3. **Scope Tracking**: Maintain tag stack for nested scopes
4. **Flag Resolution**: Apply override rules correctly
5. **Error Handling**: Fail safely on malformed input

### 5.2 Parsing Algorithm

#### 5.2.1 High-Level Flow

```
1. Initialize empty tag stack
2. Scan content for {{DEL: markers
3. For each opening tag:
   a. Extract flags and metadata
   b. Validate syntax
   c. Push to tag stack
4. For each closing tag:
   a. Verify matching opening tag
   b. Pop from stack
   c. Apply scope rules
5. For each content segment:
   a. Determine active flags from stack
   b. Resolve conflicts (restrictive wins)
   c. Return effective permissions
6. Validate complete parse (no unclosed tags)
```

#### 5.2.2 Detailed Specification

**Step 1: Tokenization**

```python
# Pseudocode
def tokenize(content):
    tokens = []
    pattern = r'\{\{DEL:(.*?)\}\}' 
    for match in regex.finditer(pattern, content):
        tag_content = match.group(1)
        is_closing = tag_content.startswith('/')
        tokens.append({
            'type': 'closing' if is_closing else 'opening',
            'content': tag_content,
            'position': match.start()
        })
    return tokens
```

**Step 2: Metadata Extraction**

```python
# Pseudocode
def extract_metadata(tag_content):
    # Split by whitespace, preserving quoted strings
    parts = smart_split(tag_content)
    flags = []
    metadata = {}
    
    for part in parts:
        if '=' in part:
            key, value = part.split('=', 1)
            metadata[key] = unquote(value)
        else:
            flags.append(part)
    
    return flags, metadata
```

**Step 3: Scope Resolution**

```python
# Pseudocode
def resolve_scope(tag_stack, position):
    active_flags = []
    
    # Collect flags from all active scopes
    for scope in tag_stack:
        active_flags.extend(scope.flags)
    
    # Apply conflict resolution
    if 'noai' in active_flags:
        return {'permissions': [], 'restrictions': ['noai']}
    
    # Filter by restriction priority
    permissions = [f for f in active_flags if is_permission(f)]
    restrictions = [f for f in active_flags if is_restriction(f)]
    
    # Remove permissions overridden by restrictions
    for restriction in restrictions:
        if restriction == 'notraining':
            permissions.remove('aitraining') if 'aitraining' in permissions
        # ... additional override rules
    
    return {'permissions': permissions, 'restrictions': restrictions}
```

### 5.3 Error Handling

Parsers MUST handle errors according to this fail-safe hierarchy:

**Critical Errors** (MUST abort parsing):
1. Unclosed tags at document end
2. Closing tag without matching opening tag
3. Invalid tag syntax (malformed braces)

**Validation Errors** (MUST warn and fail restrictive):
1. Missing required metadata fields (`copyright_holder`, `license`)
2. Invalid metadata schema (type mismatches)
3. Unknown flags (forward compatibility - warn but continue)
4. Payment metadata incomplete (`micropay` flag without payment address)

**Non-Critical Warnings** (SHOULD log but continue):
1. Deprecated flags (if any in future versions)
2. Unusual nesting patterns
3. Very large metadata blocks

**Fail-Safe Behavior:**
- Unknown content → assume "all rights reserved" (no AI use)
- Unparseable tags → treat as restrictive (no AI use)
- Conflicting flags → apply most restrictive interpretation

### 5.4 Validation Checklist

Implementations SHOULD validate:

- [ ] Tag syntax correctness (`{{DEL:...}}` format)
- [ ] Balanced opening/closing tags
- [ ] Required metadata fields present
- [ ] Metadata schema conformance
- [ ] Flag recognition (known flags)
- [ ] Base license compatibility
- [ ] Payment metadata completeness
- [ ] URI format correctness
- [ ] Date format correctness (ISO 8601)
- [ ] No logical contradictions (e.g., `noai` + `aitraining`)

---

## 6. Implementation Guidelines

### 6.1 For Content Creators

#### 6.1.1 Choosing Your Configuration

**Step 1: Select Base License**
- Choose a widely-recognized open license
- Consider: MIT, Apache 2.0, BSD, GPL, or CC BY variants
- Ensure your choice aligns with your sharing goals

**Step 2: Determine AI Permissions**
- Do you want AI systems to train on your work? → `aitraining`
- Should AI retrieve and cite your work? → `airetrieval`
- Allow fine-tuning with your content? → `aituning`

**Step 3: Set Attribution Requirements**
- Always use `attributable` flag for proper credit
- Consider adding `quotable` and `summarizable` for flexible use

**Step 4: Optional Micropayments**
- Set `cost_per_kb` rate if you want compensation
- Provide payment addresses (`btc`, `paypal`, etc.)
- Add `micropay` flag

#### 6.1.2 Application Templates

**Template 1: Fully Open Source Code**
```javascript
/*
 * Copyright (c) 2025 Your Name
 * Licensed under MIT + DEL v1.0
 * 
 * {{DEL:License version=1.0 license=MIT copyright_holder="Your Name"}}
 * {{DEL:aitraining airetrieval aituning attributable quotable}}
 */
```

**Template 2: Content with Micropayment**
```yaml
# Metadata at document start
copyright_holder: "Your Name"
license: "CC BY 4.0"
license_uri: "https://creativecommons.org/licenses/by/4.0/"
del_version: "1.0"
license_flags:
  - aitraining
  - airetrieval
  - attributable
  - micropay
cost_per_kb: 0.00001
payment_addresses:
  btc: "bc1q..."
```

**Template 3: No AI Training, Retrieval Only**
```markdown
<!-- {{DEL:License version=1.0 license="Apache-2.0" copyright_holder="Your Org"}} -->
<!-- {{DEL:airetrieval attributable notraining quotable}} -->
```

#### 6.1.3 Integration Workflows

**GitHub Repository:**
1. Add DEL tags to LICENSE file header
2. Include `DEL-LICENSE.md` with full protocol details
3. Add `.del-metadata.yaml` to repository root
4. Update README with human-readable license summary

**Blog/Website:**
1. Add DEL meta tags to `<head>` section
2. Include DEL notice in footer
3. Add HTML comments with inline tags at top of each page

**Documentation:**
1. Place DEL tags in frontmatter or header comments
2. Use consistent metadata across all docs
3. Include licensing page with clear explanations

### 6.2 For AI Developers

#### 6.2.1 Compliance Integration

**Training Pipeline Integration:**

```python
def should_include_in_training(document):
    """Determine if document can be used for training"""
    parser = DELParser()
    result = parser.parse(document.content)
    permissions = result.get_permissions()
    
    # Check permissions
    if not permissions.get('training', False):
        logger.info(f"Skipping {document.id}: No training permission")
        return False
    
    # Check base license compatibility
    if result.metadata and not is_compatible_license(result.metadata.license):
        logger.warning(f"Skipping {document.id}: Incompatible base license")
        return False
    
    # Handle payment requirements
    payment_info = result.get_payment_info()
    if payment_info:
        if not process_micropayment(document, payment_info):
            logger.info(f"Skipping {document.id}: Payment failed")
            return False
    
    # Record attribution
    if permissions.get('attribution_required'):
        record_attribution(document, result.metadata)
    
    return True
```

**RAG System Integration:**

```python
def retrieve_with_attribution(query, top_k=5):
    """Retrieve documents with proper attribution"""
    results = vector_store.search(query, top_k=top_k)
    attributed_results = []
    
    for result in results:
        parser = DELParser()
        parse_result = parser.parse(result.content)
        permissions = parse_result.get_permissions()
        
        # Check retrieval permission
        if not permissions.get('retrieval', False):
            continue
        
        # Add attribution if required
        if permissions.get('attribution_required', False):
            result.attribution = parse_result.format_attribution()
        
        attributed_results.append(result)
    
    return attributed_results
```

#### 6.2.2 Model Card Documentation

AI models MUST document DEL compliance in model cards:

```markdown
## Training Data Licensing

This model was trained on datasets respecting Distributed Equity License (DEL) v1.0 terms.

### Data Sources with DEL Terms

| Source | License | DEL Flags | Attribution |
|--------|---------|-----------|-------------|
| Widget Documentation | MIT | aitraining, airetrieval, attributable | Jane Developer |
| ML Tutorial Corpus | CC BY 4.0 | aitraining, quotable | Dr. Sarah Chen |
| Code Examples | Apache 2.0 | aitraining, airetrieval | Tech Corp |

### Compliance Measures

- All training data was validated for `aitraining` permission
- Attribution metadata preserved in training pipeline
- Micropayments processed for 127 paid sources ($45.23 total)
- Content with `noai` or `notraining` flags excluded

### Attribution

This model benefited from content created by the following contributors under DEL v1.0 terms:

[Full list available at: model-attributions.json]

### Payment Records

Micropayment transactions recorded in: payment-ledger.json
Total compensation distributed: $45.23 USD across 127 creators

### Compliance Verification

- Parser version: del-parser-py v1.0.3
- Validation date: 2025-10-15
- Audit log: training-audit.log
```

### 6.3 For Platform Operators

#### 6.3.1 Repository Integration (GitHub, GitLab)

**Detection Pipeline:**

```yaml
# .github/workflows/del-validation.yml
name: DEL License Validation

on: [push, pull_request]

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Install DEL Validator
        run: pip install del-validator
      - name: Validate DEL Tags
        run: del-validate --recursive .
      - name: Generate License Report
        run: del-report --output LICENSE-REPORT.md
```

---

## 7. Compliance and Verification

### 7.1 Compliance Requirements

#### 7.1.1 For AI Training Systems

Systems training ML models MUST:

1. **Pre-Training Validation**
   - Parse DEL tags from all training data
   - Exclude content with `noai` or `notraining` flags
   - Verify base license compatibility
   - Check for payment requirements

2. **Attribution Tracking**
   - Record `copyright_holder` for all `attributable` content
   - Maintain source URLs and license information
   - Store attribution data in queryable format
   - Include attribution in model cards

3. **Payment Processing**
   - Calculate costs for `micropay` content
   - Process payments before or within 30 days of use
   - Retain payment receipts and transaction records
   - Provide payment reporting to creators

4. **Documentation**
   - Publish compliance methodology
   - List data sources with DEL terms
   - Provide audit logs upon request
   - Update model cards with attribution

#### 7.1.2 For RAG and Retrieval Systems

Systems performing retrieval MUST:

1. **Query-Time Validation**
   - Check `airetrieval` permission before returning results
   - Respect `noquote` and `nosummarize` flags
   - Apply content length limits for `quotable` flag (≤250 words)

2. **Attribution in Outputs**
   - Include attribution for `attributable` content
   - Format: Author, Title, License
   - Provide source links when available
   - Maintain attribution through processing pipeline

3. **Commercial Use Restrictions**
   - Check for `noncommercial` flag
   - Exclude non-commercial content from commercial services
   - Document commercial vs. non-commercial usage boundaries

#### 7.1.3 For Content Platforms

Platforms hosting DEL-licensed content SHOULD:

1. **Metadata Preservation**
   - Maintain DEL tags through content processing
   - Include DEL headers in API responses
   - Expose DEL metadata in search/discovery

2. **Creator Tools**
   - Provide UI for setting DEL terms
   - Validate DEL tag syntax on upload
   - Generate human-readable license summaries

3. **Discovery APIs**
   - Enable filtering by DEL permissions
   - Expose license metadata in APIs
   - Support programmatic license queries

### 7.2 Verification Methods

#### 7.2.1 Automated Validation

**Tag Syntax Validation:**

```python
def validate_del_syntax(content):
    """Validate DEL tag syntax"""
    errors = []
    warnings = []
    
    # Check for balanced tags
    opening_tags = re.findall(r'\{\{DEL:[^/].*?\}\}', content)
    closing_tags = re.findall(r'\{\{/DEL:.*?\}\}', content)
    
    if len(opening_tags) != len(closing_tags):
        errors.append("Unbalanced tags: {} opening, {} closing".format(
            len(opening_tags), len(closing_tags)
        ))
    
    # Validate metadata schema
    for match in re.finditer(r'\{\{DEL:(.*?)\}\}', content, re.DOTALL):
        tag_content = match.group(1)
        try:
            parser = DELParser()
            metadata = parser.extract_metadata(tag_content)
            
            # Check required fields
            if 'copyright_holder' not in metadata:
                errors.append("Missing required field: copyright_holder")
            if 'license' not in metadata:
                errors.append("Missing required field: license")
            
            # Check flag validity
            for flag in metadata.get('flags', []):
                if not is_valid_flag(flag):
                    warnings.append(f"Unknown flag: {flag}")
        
        except Exception as e:
            errors.append(f"Parse error: {str(e)}")
    
    return {
        'valid': len(errors) == 0,
        'errors': errors,
        'warnings': warnings
    }
```

**License Compatibility Check:**

```python
def check_license_compatibility(base_license, del_flags):
    """Check if DEL flags are compatible with base license"""
    
    # Public domain licenses cannot have restrictions
    if base_license in ['CC0', 'Unlicense']:
        return {
            'compatible': False,
            'reason': 'Cannot apply DEL to public domain works'
        }
    
    # NoDerivatives licenses conflict with training
    if 'ND' in base_license:  # e.g., CC BY-ND
        if 'aitraining' in del_flags or 'aituning' in del_flags:
            return {
                'compatible': False,
                'reason': 'Training creates derivatives, conflicts with ND'
            }
    
    # NonCommercial licenses must align
    if 'NC' in base_license:  # e.g., CC BY-NC
        if 'noncommercial' not in del_flags:
            return {
                'compatible': True,
                'warning': 'Consider adding noncommercial flag for consistency'
            }
    
    return {'compatible': True}
```

#### 7.2.2 Human Review

Organizations SHOULD implement review processes:

1. **Legal Review**
   - Verify base license compatibility
   - Assess enforceability in target jurisdictions
   - Review payment terms for tax/regulatory compliance

2. **Technical Review**
   - Validate tag syntax and structure
   - Test parser compatibility
   - Verify metadata completeness

3. **Ethical Review**
   - Assess fairness of payment rates
   - Evaluate attribution adequacy
   - Consider creator compensation equity

#### 7.2.3 Third-Party Audits

For high-value datasets or models:

1. **Compliance Audit**
   - Independent verification of DEL adherence
   - Review of training data sources
   - Validation of attribution and payment records

2. **Audit Report Format**

```markdown
# DEL Compliance Audit Report

**Model**: GPT-Widget-3.5
**Audit Date**: 2025-10-15
**Auditor**: Third-Party Verification Service

## Scope
- Training data: 10 TB
- DEL-licensed sources: 4,523 documents
- Audit sample: 500 documents (11% of DEL content)

## Findings

### Compliance Score: 96%

### Passed Checks ✓
- Tag parsing accuracy: 98%
- Attribution preservation: 100%
- Payment processing: 95%
- NoAI flag respect: 100%

### Issues Identified
- 18 documents missing attribution in model card
- 23 micropayments delayed beyond 30 days
- 4 documents used despite notraining flag (removed post-audit)

### Recommendations
1. Improve real-time payment processing
2. Enhance model card attribution completeness
3. Add pre-training validation layer

### Overall Assessment
Model demonstrates substantial good-faith compliance with DEL v1.0.
Issues identified are non-systematic and correctable.

**Certification**: Compliant with remediation
```

### 7.3 Safe Harbor Provisions

The DEL Protocol recognizes good-faith compliance efforts:

#### 7.3.1 Good Faith Criteria

Automated systems demonstrate good faith by:

1. **Implementing Reasonable Parsers**
   - Use standard parsing libraries
   - Handle common tag formats
   - Log unrecognized patterns

2. **Respecting Clear Signals**
   - Honor `noai` and `notraining` flags
   - Process attribution requirements
   - Attempt payment processing

3. **Prompt Correction**
   - Fix errors within 30 days of notification
   - Provide correction evidence
   - Update processes to prevent recurrence

4. **Transparent Documentation**
   - Publish compliance methodology
   - Maintain public model cards
   - Provide audit trails on request

#### 7.3.2 Safe Harbor Benefits

Systems meeting good-faith criteria receive:

- **Presumption of Compliance** in disputes
- **30-day cure period** for violations
- **Reduced liability** for technical errors
- **Community recognition** as responsible AI

#### 7.3.3 Safe Harbor Exclusions

Safe harbor does NOT apply to:

- Intentional flag circumvention
- Systematic payment avoidance
- Attribution stripping
- Willful disregard of `noai` flags
- Failure to correct after notification

---

## 8. Payment Protocol

### 8.1 Micropayment Infrastructure

#### 8.1.1 Cost Calculation

**Standard Formula:**

```
Total Payment = Content Size (KB) × cost_per_kb

Where:
- Content Size is measured in kilobytes (1024 bytes)
- cost_per_kb is specified in USD
- Minimum payment: $0.01 USD (aggregate small amounts)
```

**Example Calculations:**

```python
def calculate_payment(content_size_bytes, cost_per_kb):
    """Calculate payment owed for content usage"""
    content_kb = content_size_bytes / 1024
    payment_usd = content_kb * cost_per_kb
    
    # Minimum payment threshold
    if payment_usd < 0.01:
        # Aggregate with other micropayments
        return 0, payment_usd  # (immediate, deferred)
    
    return payment_usd, 0
```

**Aggregation Example:**

```
Document A: 50 KB × $0.00001 = $0.0005 (defer)
Document B: 75 KB × $0.00001 = $0.00075 (defer)
Document C: 120 KB × $0.00001 = $0.0012 (defer)
Document D: 100 KB × $0.00001 = $0.00100 (defer)
Document E: 200 KB × $0.00001 = $0.00200 (defer)

Running Total:
After A: $0.00025 (defer)
After B: $0.00055 (defer)
After C: $0.00100 (defer)
After D: $0.00200 (defer)
After E: $0.00400 (defer)
...continues until reaching $0.01...
After 25 documents: $0.01050 (process payment)
```

**Multiple Creators:**

```
Training dataset includes:
- Creator A: 2,000 KB × $0.00001 = $0.02
- Creator B: 1,500 KB × $0.00002 = $0.03
- Creator C: 500 KB × $0.00005 = $0.025
- Creator D: 3,000 KB × $0.00001 = $0.03

Total owed: $0.105
Individual payments processed to each creator
```

#### 8.1.2 Payment Methods

**Bitcoin (BTC):**

```yaml
payment_addresses:
  btc: "bc1qxy2kgdygjrsqtzq2n0yrf2493p83kkfjhx0wlh"
```

Payment URI format (BIP-21):
```
bitcoin:bc1qxy2kgdygjrsqtzq2n0yrf2493p83kkfjhx0wlh?amount=0.00000234&label=DEL%20Payment
```

**Ethereum (ETH):**

```yaml
payment_addresses:
  eth: "0x742d35Cc6634C0532925a3b844Bc9e7595f0bEb0"
```

**PayPal:**

```yaml
payment_addresses:
  paypal: "creator@example.com"
```

**Stripe Payment Links:**

```yaml
payment_addresses:
  stripe: "https://buy.stripe.com/test_unique_payment_link"
```

#### 8.1.3 Payment Timing

Payments MUST be processed:

1. **Before Use**: For high-value content (>$1.00)
2. **Within 30 Days**: For aggregate micropayments
3. **Quarterly**: For ongoing subscriptions/licenses

**Payment Record Format:**

```json
{
  "payment_id": "del-pmt-20251015-001",
  "timestamp": "2025-10-15T14:23:45Z",
  "payer": "AI Company Inc.",
  "payee": "Jane Developer",
  "payee_address": "bc1q...",
  "amount_usd": 0.0245,
  "content_sources": [
    {
      "url": "https://example.com/docs/widget-guide.md",
      "size_kb": 250,
      "cost_per_kb": 0.00001
    }
  ],
  "transaction_id": "btc:abc123...",
  "status": "completed"
}
```

### 8.2 Payment Verification

#### 8.2.1 Proof of Payment

Payers SHOULD retain:

1. **Transaction receipts** (blockchain tx, PayPal receipt, etc.)
2. **Payment logs** linking payments to content
3. **Aggregation records** showing how amounts accumulated
4. **Beneficiary confirmations** when available

#### 8.2.2 Dispute Resolution

If payment disputes arise:

1. **Creator provides payment address** from metadata
2. **User provides transaction proof** (tx ID, receipt)
3. **Third party verifies** transaction on blockchain/payment system
4. **Resolution**:
   - Valid payment → case closed
   - Invalid/missing payment → user has 30 days to pay
   - Unreachable payment address → good faith effort documented

### 8.3 Payment Aggregation Services

Third-party services MAY provide:

1. **Payment Aggregation**
   - Collect micropayments across multiple sources
   - Batch process when thresholds reached
   - Distribute to creators

2. **Currency Conversion**
   - Accept payments in various currencies
   - Convert to creator's preferred currency
   - Handle exchange rate fluctuations

3. **Tax Reporting**
   - Generate 1099/tax forms for creators
   - Track payments for tax compliance
   - Provide annual statements

---

## 9. Registry and Discovery

### 9.1 DEL Registry Concept

A **DEL Registry** is a centralized or distributed service that:

1. Indexes DEL-licensed content
2. Provides discovery APIs
3. Facilitates compliance verification
4. Enables payment routing

### 9.2 Registry Data Model

```json
{
  "content_id": "del-content-12345",
  "url": "https://example.com/content",
  "title": "Widget Optimization Guide",
  "copyright_holder": "Jane Developer",
  "author": "Jane Developer",
  "license": "MIT",
  "license_uri": "https://opensource.org/licenses/MIT",
  "del_version": "1.0",
  "del_flags": {
    "permissions": ["aitraining", "airetrieval", "aituning", "attributable"],
    "restrictions": []
  },
  "payment": {
    "cost_per_kb": 0.00001,
    "addresses": {
      "btc": "bc1q..."
    }
  },
  "metadata": {
    "date_published": "2025-10-01",
    "date_indexed": "2025-10-15",
    "content_type": "text/markdown",
    "size_bytes": 256000,
    "language": "en"
  },
  "verification": {
    "verified": true,
    "verified_by": "DEL Registry v1.0",
    "verified_date": "2025-10-15",
    "signature": "..."
  }
}
```

### 9.3 Registry API Specification

#### 9.3.1 Content Registration

**Endpoint:** `POST /v1/register`

**Request:**
```json
{
  "url": "https://example.com/content",
  "del_metadata": {
    "copyright_holder": "Jane Developer",
    "license": "MIT",
    "del_flags": ["aitraining", "airetrieval", "attributable"]
  }
}
```

**Response:**
```json
{
  "content_id": "del-content-12345",
  "status": "registered",
  "verification_url": "https://registry.del.org/verify/del-content-12345"
}
```

#### 9.3.2 Content Discovery

**Endpoint:** `GET /v1/search`

**Parameters:**
- `license`: Filter by base license (e.g., `MIT`, `CC BY 4.0`)
- `flags`: Filter by DEL flags (e.g., `aitraining,airetrieval`)
- `author`: Filter by author/copyright holder
- `paid`: Filter by payment requirement (`true`/`false`)
- `q`: Full-text search query

**Example Request:**
```
GET /v1/search?license=MIT&flags=aitraining&paid=false
```

**Response:**
```json
{
  "total": 1523,
  "results": [
    {
      "content_id": "del-content-12345",
      "title": "Widget Optimization Guide",
      "author": "Jane Developer",
      "license": "MIT",
      "del_flags": ["aitraining", "airetrieval", "attributable"],
      "url": "https://example.com/content"
    }
  ]
}
```

#### 9.3.3 Verification

**Endpoint:** `GET /v1/verify/{content_id}`

**Response:**
```json
{
  "content_id": "del-content-12345",
  "verified": true,
  "copyright_holder": "Jane Developer",
  "license": "MIT",
  "del_version": "1.0",
  "last_verified": "2025-10-15T10:30:00Z",
  "verification_signature": "..."
}
```

---

## 10. Versioning and Governance

### 10.1 Protocol Versioning

The DEL Protocol follows semantic versioning:

**Format:** `MAJOR.MINOR.PATCH`

- **MAJOR**: Breaking changes to tag syntax or semantics
- **MINOR**: New features, additional flags (backward compatible)
- **PATCH**: Bug fixes, clarifications (no functional changes)

**Version History:**
- `1.0.0` (2025-10-15): Initial release

### 10.2 Block Numbering

Each major document receives a block number:

| Block | Document | Current Version |
|-------|----------|-----------------|
| #0000000000 | DEL Manifesto | 1.0 |
| #0000000001 | DEL License | 1.0 |
| #0000000002 | DEL Protocol | 1.0 |

Future major versions increment the block:
- Protocol v2.0 → Block #0000000012
- License v2.0 → Block #0000000011

### 10.3 Flag Extension Process

New flags MAY be added through:

1. **Community Proposal**
   - Submit GitHub issue with use case
   - Provide implementation examples
   - Demonstrate need and demand

2. **Review Period**
   - 30-day public comment period
   - Technical feasibility assessment
   - Legal implications review

3. **Approval and Integration**
   - Merge into next MINOR version
   - Update specification and examples
   - Publish migration guide

4. **Reservation**
   - Unknown flags are reserved for future use
   - Parsers SHOULD warn but not fail on unknown flags
   - Forward compatibility maintained

### 10.4 Governance Model

The DEL Protocol is governed by:

1. **Maintainer**: Kevin Ryan (DistributedEquity.org)
2. **Community Input**: GitHub issues and discussions
3. **Advisory Board** (future): Legal, technical, and creator representatives

**Decision-Making:**
- **PATCH versions**: Maintainer discretion
- **MINOR versions**: Community consultation (30 days)
- **MAJOR versions**: Advisory board approval (when established)

### 10.5 Amendment Process

Changes to this protocol require:

1. **Proposal**: Detailed specification of changes
2. **Impact Assessment**: Breaking vs. non-breaking analysis
3. **Migration Path**: How existing implementations adapt
4. **Community Review**: Minimum 30-day period
5. **Publication**: New version with changelog

**Breaking Changes:**
- Trigger MAJOR version increment
- Provide 6-month deprecation period
- Publish detailed migration guide
- Maintain backward compatibility library

---

## 11. Security Considerations

### 11.1 Tag Injection Attacks

**Threat:** Malicious actors inject DEL tags to bypass restrictions

**Mitigation:**
1. Validate tag syntax strictly
2. Verify copyright holder identity where possible
3. Use cryptographic signatures for high-value content
4. Implement registry verification

**Example Attack:**
```html
<!-- Legitimate content with {{DEL:noai}} -->
<!-- Attacker injects: {{/DEL:noai}}{{DEL:aitraining}} -->
```

**Defense:**
```python
def validate_tag_integrity(content, expected_copyright_holder):
    """Verify tags haven't been tampered with"""
    parser = DELParser()
    result = parser.parse(content)
    
    # Check copyright holder matches expected
    if result.metadata and result.metadata.copyright_holder != expected_copyright_holder:
        raise SecurityError("Copyright holder mismatch")
    
    # Verify signature if present
    if result.metadata and hasattr(result.metadata, 'signature'):
        if not verify_signature(content, result.metadata.signature):
            raise SecurityError("Invalid signature")
    
    return result
```

### 11.2 Payment Address Spoofing

**Threat:** Attackers replace payment addresses to redirect funds

**Mitigation:**
1. Verify payment addresses through registry
2. Use cryptographic signing of metadata
3. Implement address whitelisting
4. Require HTTPS for content retrieval

### 11.3 Denial of Service

**Threat:** Extremely large or deeply nested DEL tags cause parser failure

**Mitigation:**
1. Implement parsing limits:
   - Max tag nesting depth: 10
   - Max metadata size: 64 KB
   - Max total tags per document: 1000
2. Use timeout mechanisms
3. Sanitize input before parsing

**Example Limits:**

```python
class DELParser:
    MAX_NESTING_DEPTH = 10
    MAX_METADATA_SIZE = 65536  # 64 KB
    MAX_TAGS_PER_DOCUMENT = 1000
    PARSE_TIMEOUT_SECONDS = 30
    
    def parse_with_limits(self, content):
        """Parse with security limits"""
        if len(content) > self.MAX_METADATA_SIZE * 10:
            raise SecurityError("Content too large")
        
        tag_count = content.count('{{DEL:')
        if tag_count > self.MAX_TAGS_PER_DOCUMENT:
            raise SecurityError("Too many tags")
        
        with timeout(self.PARSE_TIMEOUT_SECONDS):
            return self.parse(content)
```

### 11.4 Privacy Considerations

**Data Minimization:**
- DEL tags SHOULD NOT include personal information beyond copyright holder
- Avoid embedding email addresses, phone numbers, or addresses
- Use payment addresses (crypto) rather than personal payment info

**GDPR Compliance:**
- Copyright holder names are legitimate interest for attribution
- Users may request removal from registries (right to be forgotten)
- Registries MUST provide data export mechanisms

---

## 12. Protocol Status and Limitations

### 12.1 Experimental Status

**IMPORTANT: This protocol is in early adoption phase.**

The DEL Protocol v1.0 represents our best effort to create a practical, machine-readable licensing framework for AI systems. However:

**We make no guarantees about:**
- Universal adoption by AI companies
- Legal enforceability in all jurisdictions
- Technical compatibility with all platforms
- Long-term stability of tag syntax
- Payment infrastructure maturity

### 12.2 Known Limitations

1. **Parser Diversity**
   - Different implementations may interpret tags differently
   - Edge cases may not be consistently handled
   - Nested tag semantics require more real-world testing

2. **Payment Infrastructure**
   - Micropayment processing has high transaction costs
   - No universal aggregation service exists yet
   - Currency conversion adds complexity
   - Tax reporting varies by jurisdiction

3. **Verification Challenges**
   - Copyright holder identity verification is difficult
   - No central authority for dispute resolution
   - Tag tampering detection is imperfect
   - Registry coverage will be incomplete initially

4. **Legal Uncertainty**
   - No case law exists for DEL enforcement
   - Jurisdictional variations in IP law
   - Fair use doctrine interaction unclear
   - Contract vs. license distinction varies

### 12.3 Not Legal Advice

**This protocol does not constitute legal advice.**

Users should:
- Consult qualified IP attorneys before applying DEL
- Understand local copyright and contract law
- Assess enforceability in target jurisdictions
- Consider tax implications of micropayments
- Review compatibility with existing agreements

### 12.4 Commitment to Improvement

DistributedEquity.org commits to:

1. **Iterative Refinement**
   - Incorporate community feedback
   - Address implementation challenges
   - Publish regular updates and clarifications

2. **Backward Compatibility**
   - Maintain v1.x tag parsing in all future versions
   - Provide migration tools for breaking changes
   - Support legacy implementations for reasonable periods

3. **Community Engagement**
   - Respond to GitHub issues within 7 days
   - Host quarterly community calls
   - Publish annual state-of-the-protocol reports

4. **Transparency**
   - Document all protocol changes publicly
   - Maintain public changelog
   - Provide rationale for major decisions

### 12.5 Future Development Roadmap

**v1.1 (Q1 2026 - Planned):**
- Clarifications based on early adoption feedback
- Additional code examples and integration guides
- Enhanced validation tools
- Bug fixes and edge case handling

**v1.2 (Q2 2026 - Planned):**
- Performance optimizations for large-scale parsing
- Improved payment aggregation specifications
- Registry API enhancements
- Additional platform integration examples

**v2.0 (2026-2027 - Under Consideration):**
- Potential new flags based on community needs
- Enhanced cryptographic verification
- Decentralized registry standardization
- Integration with emerging AI governance frameworks

---

## 13. Implementation Resources (Planned)

### 13.1 Reference Implementations (Planned)

**Python Parser:**
- Repository: https://github.com/distributed-equity/del-parser-python
- PyPI: `pip install del-protocol`
- Documentation: https://docs.del.org/python

**JavaScript Parser:**
- Repository: https://github.com/distributed-equity/del-parser-js
- NPM: `npm install @del/protocol`
- Documentation: https://docs.del.org/javascript

**Command-Line Tools:**
```bash
# Install validator
npm install -g del-validator

# Validate single file
del-validate document.md

# Validate directory
del-validate --recursive ./src

# Generate report
del-validate --format json --output report.json ./src
```

### 13.2 Integration Libraries (Planned)

- Python: `del-protocol`
- JavaScript/TypeScript: `@del/protocol`
- Ruby: `del-protocol` (community)
- Go: `github.com/distributed-equity/del-go` (community)

### 13.3 Documentation and Support

- **Protocol Specification**: https://github.com/distributed-equity/protocol
- **Email**: hello@distributedequity.org

---

## 14. Appendices

### Appendix A: Complete Flag Reference

| Flag | Type | Meaning | Conflicts With |
|------|------|---------|----------------|
| `aitraining` | Permission | ML model training allowed | `noai`, `notraining`, `noderivatives` |
| `airetrieval` | Permission | RAG/embedding use allowed | `noai` |
| `aituning` | Permission | Model tuning allowed | `noai`, `noderivatives` |
| `quotable` | Permission | Allow quotation (≤250 words) | `noai`, `noquote` |
| `summarizable` | Permission | Allow AI summaries | `noai`, `nosummarize` |
| `attributable` | Requirement | Attribution required | - |
| `micropay` | Requirement | Payment required | - |
| `holistic` | Descriptor | Consider as unified whole | - |
| `uniquepurpose` | Descriptor | Distinct creative purpose | - |
| `noai` | Restriction | No AI use whatsoever | All permissions |
| `notraining` | Restriction | No model training | `aitraining` |
| `noquote` | Restriction | No quotation | `quotable` |
| `nosummarize` | Restriction | No summaries | `summarizable` |
| `noderivatives` | Restriction | No derivatives | `aitraining`, `aituning` |
| `noncommercial` | Restriction | No commercial AI use | - |

### Appendix B: License Compatibility Matrix

| Base License | Training | Retrieval | Tuning | Commercial | Notes |
|--------------|----------|-----------|--------|------------|-------|
| MIT | ✅ | ✅ | ✅ | ✅ | Fully compatible |
| Apache 2.0 | ✅ | ✅ | ✅ | ✅ | Fully compatible |
| BSD-3-Clause | ✅ | ✅ | ✅ | ✅ | Fully compatible |
| CC BY 4.0 | ✅ | ✅ | ✅ | ✅ | Perfect alignment |
| CC BY-SA 4.0 | ✅ | ✅ | ✅ | ✅ | Derivatives must be SA |
| CC BY-NC 4.0 | ✅ | ✅ | ✅ | ❌ | Must add `noncommercial` |
| CC BY-ND 4.0 | ❌ | ✅ | ❌ | ✅ | Only retrieval valid |
| GPL-3.0 | ✅ | ✅ | ✅ | ✅ | Derivatives must be GPL |
| LGPL-3.0 | ✅ | ✅ | ✅ | ✅ | Library use permitted |
| CC0/Unlicense | ❌ | ❌ | ❌ | ❌ | Cannot apply DEL |

### Appendix C: Common Use Cases

**Use Case 1: Open Source Code Library**
```yaml
license: "MIT"
license_flags:
  - aitraining
  - airetrieval
  - aituning
  - attributable
  - quotable
```

**Use Case 2: Educational Content**
```yaml
license: "CC BY 4.0"
license_flags:
  - aitraining
  - airetrieval
  - attributable
  - quotable
  - summarizable
```

**Use Case 3: Creative Work with Compensation**
```yaml
license: "CC BY 4.0"
license_flags:
  - airetrieval
  - attributable
  - micropay
cost_per_kb: 0.0001
payment_addresses:
  btc: "bc1q..."
```

**Use Case 4: No AI Training**
```yaml
license: "CC BY-NC-ND 4.0"
license_flags:
  - airetrieval
  - attributable
  - noncommercial
  - notraining
  - quotable
```

**Use Case 5: Complete Restriction**
```yaml
license: "CC BY-NC-ND 4.0"
restriction_flags:
  - noai
```

---

## 15. Signature and Document Authentication

```yaml
Document: Distributed Equity Protocol (DEL Protocol) v1.0
Block Number: #0002
Depends On: DEL License v1.0 (#0001), DEL Manifesto (#0000)
Signed on behalf of: DistributedEquity.org
Author: Kevin Ryan, Founder
Date: October 15, 2025
Location: UTC+00:00
Version: 1.0.0
Status: Published - Early Adoption Phase
```

**Document Hash (SHA-256):**
```
[To be computed upon finalization]
```

**Digital Signature:**
```
[To be added using GPG or similar]
```

**Verification:**
To verify this document's authenticity:
```bash
curl https://del.org/protocol/v1.0/del-protocol-v1.0.md | sha256sum
gpg --verify del-protocol-v1.0.md.sig
```

---

**This protocol document is licensed under:**
- **CC BY 4.0**: https://creativecommons.org/licenses/by/4.0/
- **DEL v1.0 Supplementary Terms** with flags: `aitraining airetrieval aituning attributable quotable`

**Metadata:**
```yaml
{{DEL:License version=1.0 license="CC BY 4.0" copyright_holder="DistributedEquity.org"}}
{{DEL:aitraining airetrieval aituning attributable quotable}}
author: "Kevin Ryan"
title: "Distributed Equity Protocol (DEL Protocol) v1.0"
purpose: "Technical implementation framework for machine-readable licensing"
url: "https://github.com/distributed-equity/protocol/blob/main/del-protocol-v1.0.md"
date: "2025-10-15"
version: "1.0.0"
language: "en"
```

---

## Contributing

We welcome contributions to improve the DEL Protocol:

**GitHub Repository:**
https://github.com/distributed-equity/protocol

**How to Contribute:**
1. Open an issue to discuss proposed changes
2. Fork the repository
3. Submit a pull request with clear description
4. Participate in review process

**Areas for Contribution:**
- Parser implementations in additional languages
- Integration examples for specific platforms
- Validation tools and linters
- Documentation improvements
- Test cases and edge case handling
- Payment infrastructure components
- Registry implementations

**Contact:**
- Email: hello@distributedequity.org
- GitHub: @distributed-equity
- Website: https://distributedequity.org

---

```yaml

Signed on behalf of DistributedEquity.org (Block #0000000001):
Kevin Ryan  
Founder, DistributedEquity.org  
Date: 20 October 2025 (UTC+02:00, Europe/Dublin)

```

---

**END OF PROTOCOL SPECIFICATION**
