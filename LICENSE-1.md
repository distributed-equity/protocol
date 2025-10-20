<!-- 
Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0)
https://creativecommons.org/licenses/by/4.0/

DEL v1.0 Supplementary Terms for AI and Automated Systems
https://github.com/distributed-equity/license/blob/main/del-v1.0.md

{{DEL:License version=1.0 license="CC BY 4.0" copyright_holder="Kevin Ryan, DistributedEquity.org"}}
{{DEL:aitraining airetrieval aituning attributable quotable summarizable holistic uniquepurpose}}

author: "Kevin Ryan"
title: "Distributed Equity License (DEL) v1.0"
purpose: "Legal framework establishing machine-readable supplementary licensing terms for AI systems, enabling creators to declare permissions and restrictions for automated use while maintaining compatibility with existing open licenses"
url: "https://github.com/distributed-equity/license/blob/main/del-v1.0.md"
date: "2025-10-15"
version: "1.0"
language: "en"
del_version: "1.0"
del_uri: "https://github.com/distributed-equity/license/blob/main/del-v1.0.md"
license_uri: "https://creativecommons.org/licenses/by/4.0/"
block_number: "0000000001"
-->

# Distributed Equity License (DEL) v1.0
## Supplementary Terms for AI and Automated Systems

---
**Release Notes - DEL v1.0**

This is the initial experimental release of the Distributed Equity License framework.
We welcome feedback, questions, and contributions from the community.

**Status**: Early adoption phase  
**Stability**: Experimental - API may change in v2.0  
**Seeking**: Legal review, implementation feedback, adoption reports

See Section 15 for important limitations and disclaimers.

---

**License**: This license text is itself licensed under CC BY 4.0 and DEL v1.0.

**Author**: Kevin Ryan, Founder, [DistributedEquity.org](https://distributedequity.org)

**Version**: 1.0 (Extension Framework)

**Attribution Required**: Yes

---

## 1. Preamble and Purpose

The **Distributed Equity License v1.0** ("DEL" or "Supplementary Terms") is designed to work **alongside** existing open licenses—including MIT, Apache 2.0, BSD, GPL, and Creative Commons licenses—to provide machine-readable clarification for AI and automated system usage.

DEL v1.0 is **not a standalone license**. It functions as **supplementary metadata** that:
- Extends and clarifies existing license permissions for AI-specific use cases
- Provides machine-readable tags for automated systems
- Enables attribution tracking and optional micropayment mechanisms
- Does not contradict or override the base license terms

### 1.1 Legal Relationship

DEL v1.0 operates under the following principles:

1. **The Base License governs all general use** - Your chosen license (MIT, CC BY, etc.) remains the primary legal instrument
2. **DEL clarifies AI-specific permissions** - These supplementary terms provide additional clarity for machine learning, training, retrieval, and automated systems
3. **In case of conflict, the Base License prevails** - DEL cannot restrict rights granted by the Base License
4. **DEL may narrow permissions** - Where the Base License is permissive, DEL may add specific restrictions for AI use (e.g., requiring attribution or payment)
5. **DEL is legally binding** - These supplementary terms are enforceable under the same copyright framework as the Base License

### 1.2 Scope of Application

DEL v1.0 applies specifically to:
- AI and machine learning model training
- Retrieval-augmented generation (RAG) systems
- Embedding and vector databases
- Fine-tuning and model adaptation
- Automated summarization and synthesis
- Any computational system that processes the Work for pattern learning or automated output generation

Traditional human use (reading, editing, sharing, modifying) remains governed solely by the Base License.

---

## 2. Definitions

- **Base License**: The primary open license under which the Work is released (e.g., MIT, Apache 2.0, CC BY 4.0, GPL-3.0, BSD-3-Clause).
- **Work**: The creative work, code, documentation, or other content covered by both the Base License and these Supplementary Terms.
- **Licensor**: The individual or entity who applies both the Base License and DEL to the Work.
- **You** or **Your**: The individual, organization, or automated system exercising rights under the Base License and DEL.
- **DEL Tags**: Machine-readable inline markers in the format `{{DEL:...}}` that declare AI-specific permissions or restrictions.
- **Metadata**: Structured data in YAML or JSON format accompanying DEL Tags.
- **AI Training**: Using the Work as training data for machine learning models, including but not limited to: neural network training, fine-tuning, transfer learning, and model adaptation.
- **AI Retrieval**: Using the Work in retrieval systems including: RAG systems, semantic search, embedding generation, vector databases, and context injection.
- **AI Tuning**: Adapting or reinforcing model behavior using the Work, including: RLHF (Reinforcement Learning from Human Feedback), instruction tuning, and behavioral alignment.
- **Automated System**: Any software system that processes content without direct human review of each output, including but not limited to: AI models, chatbots, code generators, and content synthesizers.
- **Attribution**: Acknowledgment of the Licensor and source of the Work as specified in Section 7.
- **Micropayment**: Optional small payment for automated usage as specified in metadata.

---

## 3. How DEL v1.0 Works with Base Licenses

### 3.1 Extension, Not Replacement

DEL v1.0 **supplements** your Base License by:
- Adding machine-readable metadata for automated systems
- Clarifying ambiguous AI-related permissions
- Enabling optional attribution tracking and micropayments
- Providing clear signals to AI companies and automated crawlers

### 3.2 Compatibility Matrix

| Base License | DEL Compatibility | Notes |
|--------------|-------------------|-------|
| MIT, Apache 2.0, BSD | ✅ Excellent | DEL adds AI-specific clarity to already-permissive terms |
| CC BY 4.0 | ✅ Perfect | Attribution requirements align naturally |
| CC BY-SA 4.0 | ✅ Good | Ensure DEL doesn't contradict ShareAlike requirements |
| GPL-3.0, LGPL | ⚠️ Use carefully | Ensure DEL respects copyleft provisions |
| CC BY-NC | ⚠️ Limited | DEL must not allow commercial AI use |
| CC BY-ND | ⚠️ Very limited | AI training creates derivatives; use only for retrieval |
| Public Domain (CC0, Unlicense) | ❌ Incompatible | Cannot assert rights over public domain works |

### 3.3 Conflict Resolution

If any DEL term conflicts with the Base License:
1. The Base License always prevails for general use
2. For AI-specific use, the **most restrictive** interpretation applies
3. If DEL attempts to grant permissions not available under the Base License, those DEL permissions are **void**
4. If DEL attempts to restrict permissions explicitly granted by the Base License for general use, those restrictions are **void**

**Example**: If your Base License is CC BY-ND (No Derivatives), DEL cannot permit AI training (which creates derivatives). Only retrieval and quotation would be valid.

---

## 4. License Grant

Subject to the terms of your Base License and these Supplementary Terms, the Licensor grants You the following **additional clarifications** for AI and automated systems:

1. **Explicit Permission Flags**: Where DEL tags declare permissions (e.g., `aitraining`, `airetrieval`, `aituning`), You may exercise those rights for automated systems within the scope of both the Base License and DEL.

2. **Machine-Readable Signals**: Automated systems should respect DEL tags as clear, enforceable declarations of the Licensor's intent regarding AI use.

3. **Attribution and Payment**: Where specified in DEL metadata, automated use may require attribution, payment, or both, even if the Base License does not explicitly require these for general use.

4. **Scope Limitation**: All uses outside the scope of both the Base License and DEL tags are prohibited.

---

## 5. Rights Flags and Restrictions

### 5.1 Permission Flags

These flags **clarify** that the following uses are permitted under the Base License:

- **`aitraining`** — Permits use of the Work for AI/ML model training, fine-tuning, or pattern learning
- **`airetrieval`** — Permits inclusion in RAG systems, embeddings, vector databases, and semantic search
- **`aituning`** — Permits use for model tuning, RLHF, instruction following, and behavioral adaptation
- **`quotable`** — Allows quotation of limited excerpts (≤ 250 words or 10%, whichever is smaller)
- **`summarizable`** — Allows AI-generated summaries in automated outputs
- **`attributable`** — Requires explicit attribution (see Section 7)
- **`micropay`** — Enables optional micropayment-based usage (see Section 7.2)
- **`holistic`** — Indicates the Work should be considered as a complete, unified creation (not fragmented)
- **`uniquepurpose`** — Declares the distinct moral, social, or creative purpose of the Work

### 5.2 Restriction Flags

These flags **narrow** the permissions granted by the Base License for AI-specific use:

- **`noai`** — Prohibits all AI/ML training, retrieval, and tuning (does not affect human use)
- **`notraining`** — Prohibits AI model training specifically (retrieval may still be allowed)
- **`noquote`** — Prohibits direct quotation in AI outputs
- **`nosummarize`** — Prohibits AI-generated summaries
- **`noderivatives`** — Prohibits AI-generated derivative works (aligned with CC BY-ND)
- **`noncommercial`** — Prohibits commercial use by AI systems (aligned with CC BY-NC)

### 5.3 Flag Interactions

- **Restrictive flags always override permissive flags** in the same or parent scope
- **Example**: `{{DEL:aitraining noai}}` resolves to `noai` (no AI use permitted)
- **Nested tags override parent tags** (see Section 6.1)
- **Unknown flags are reserved** for future versions and have no current legal effect

### 5.4 Metadata Schema

DEL tags may include structured metadata in YAML or JSON format:

```yaml
author: "Your Name"
copyright_holder: "Your Name or Organization"
license: "MIT"  # Your base license
license_uri: "https://opensource.org/licenses/MIT"
del_version: "1.0"
del_uri: "https://github.com/distributed-equity/license/blob/main/del-v1.0.md"
license_flags:
  - aitraining
  - airetrieval
  - aituning
  - attributable
cost_per_kb: 0.000001  # Optional
btc: "bc1q..."  # Optional Bitcoin address
purpose: "Educational resource on widget optimization"
```

**Required fields:**
- `copyright_holder` — Name of the rights holder
- `license` — Name of the Base License (e.g., "MIT", "CC BY 4.0")

**Optional fields:**
- `license_uri` — Link to full Base License text
- `del_version` — DEL version number
- `cost_per_kb` — Micropayment rate per kilobyte
- `btc` or other payment addresses
- `purpose` — Description of the Work's purpose

---

## 6. Inline Tag Specification

### 6.1 Syntax and Structure

DEL tags use double-curly-brace syntax for machine readability:

```
{{DEL:License version=1.0 license=MIT copyright_holder="Jane Developer"}}
{{DEL:aitraining airetrieval aituning attributable}}

[Your content here]

{{/DEL:aitraining}}
```

**Opening Tag**: `{{DEL:flag1 flag2 key=value}}` 
- Lists applicable flags separated by spaces
- May include key=value pairs for metadata
- First flag should identify the tag type (e.g., `License`, `aitraining`)

**Metadata Block** (optional):
```yaml
author: "Jane Developer"
license: "MIT"
license_uri: "https://opensource.org/licenses/MIT"
```

**Closing Tag**: `{{/DEL:flag1}}`
- Must repeat the first flag from the opening tag
- Defines the scope of application

### 6.2 Nesting and Scope

Tags may be nested to provide granular control:

```markdown
{{DEL:License license=MIT copyright_holder="Developer"}}
{{DEL:aitraining airetrieval attributable}}

# Chapter 1: Public Content
This content can be used for AI training.

{{DEL:noai}}
## Section 1.1: Restricted Content
This specific section prohibits AI use.
{{/DEL:noai}}

More public content continues here.

{{/DEL:aitraining}}
{{/DEL:License}}
```

**Nesting Rules:**
1. Inner tags override outer tags for their scope
2. Closing tags must match their opening tag
3. All nested tags must close before parent tags close
4. Malformed nesting results in undefined behavior (use with caution)

### 6.3 Parsing Guidelines

Automated systems should:

1. **Recognize DEL tags** by searching for `{{DEL:` markers
2. **Parse metadata** as YAML or JSON when present
3. **Respect nesting** by maintaining a tag stack
4. **Apply restrictions** when flags conflict (most restrictive wins)
5. **Fail safely** by treating unparseable content as "all rights reserved"
6. **Ignore unknown flags** (reserved for future versions)
7. **Verify base license compatibility** before exercising DEL permissions

### 6.4 Placement Guidelines

**For code files** (Python, JavaScript, etc.):
```python
"""
Module documentation

License: MIT (https://opensource.org/licenses/MIT)
DEL v1.0 Supplementary Terms Apply

{{DEL:License version=1.0 license=MIT copyright_holder="Your Name"}}
{{DEL:aitraining airetrieval attributable}}
"""
```

**For Markdown/HTML documents**:
```html
<!--
Licensed under CC BY 4.0: https://creativecommons.org/licenses/by/4.0/
DEL v1.0 Supplementary Terms: Machine-readable AI permissions below
-->

<!-- {{DEL:License version=1.0 license="CC BY 4.0" copyright_holder="Author Name"}} -->
<!-- {{DEL:aitraining airetrieval aituning attributable quotable}} -->
```

**For website headers**:
```html
<head>
    <meta name="license" content="Apache-2.0">
    <meta name="del-version" content="1.0">
    <meta name="del-flags" content="aitraining,airetrieval,attributable">
    <meta name="copyright" content="Your Organization">
</head>
```

---

## 7. Attribution and Payment Provisions

### 7.1 Attribution Requirements

When the `attributable` flag is present, You must:

1. **Provide author information** from the `copyright_holder` field
2. **Reference the Work's title** or description where available
3. **Cite both licenses**:
   - The Base License (e.g., "MIT License")
   - DEL v1.0 Supplementary Terms
4. **Include links** to both license texts where feasible
5. **Maintain attribution in derivatives** including AI-generated outputs, summaries, and model documentation

**Attribution Format Examples:**

For code:
```
Based on [Work Title] by [Author Name]
Licensed under MIT + DEL v1.0
Source: [URL]
```

For AI model cards:
```
Training data includes content from:
- [Work Title] by [Author Name]
- License: Apache 2.0 + DEL v1.0 Supplementary Terms
- Usage: Training and retrieval with attribution
```

For chatbot responses:
```
[Response text]

Sources:
- [Author Name], "[Work Title]" (CC BY 4.0 + DEL v1.0)
```

### 7.2 Micropayment Provisions (Optional)

If DEL metadata includes both `cost_per_kb` and a valid payment address (e.g., `btc`, `eth`, `paypal`):

**Payment Obligations:**
1. Calculate payment: `(Content Size in KB) × (cost_per_kb rate)`
2. Payment must be made **before use** or within **30 days** of use
3. Payment must be sent to the specified address in the metadata
4. Retain proof of payment for your records

**Example Calculation:**
```
Content used: 250 KB
Rate: 0.00001 USD per KB
Total: 250 × 0.00001 = $0.0025 (0.25 cents)
```

**Non-Payment Consequences:**
- Failure to pay constitutes breach of these Supplementary Terms
- License rights terminate automatically (see Section 9)
- Licensor may pursue legal remedies under applicable law

**No Payment Required If:**
- No `cost_per_kb` field is present in metadata
- No valid payment address is provided
- The Base License explicitly prohibits such requirements (in which case this provision is void)

**Invalid Payment Information:**
- If payment address is unreachable or invalid, You must contact Licensor
- Use may not proceed until payment method is resolved
- Good faith effort to pay must be documented

### 7.3 Payment Address Types

Supported payment address types:
- `btc` — Bitcoin address
- `eth` — Ethereum address  
- `paypal` — PayPal email or link
- `stripe` — Stripe payment link
- Custom fields for other payment systems

---

## 8. Application and Implementation

### 8.1 How to Apply DEL v1.0 to Your Work

**Step 1**: Choose your Base License
```
Example: MIT License
```

**Step 2**: Add DEL v1.0 declaration in comments/headers
```javascript
/*
 * Copyright (c) 2025 Your Name
 * 
 * Licensed under the MIT License
 * https://opensource.org/licenses/MIT
 * 
 * Supplementary AI Terms: DEL v1.0
 * https://github.com/distributed-equity/license/blob/main/del-v1.0.md
 * 
 * {{DEL:License version=1.0 license=MIT copyright_holder="Your Name"}}
 * {{DEL:aitraining airetrieval aituning attributable}}
 */
```

**Step 3**: Include both licenses in your LICENSE file
```
MIT License
[Full MIT license text]

---

Supplementary Terms for AI and Automated Systems (DEL v1.0)
[Link to DEL v1.0 or include full text]
```

**Step 4**: Add human-readable notice
```markdown
## Licensing

This project is dual-licensed:
- **MIT License** for general use
- **DEL v1.0 Supplementary Terms** for AI/ML systems

AI systems may use this work for training and retrieval with attribution.
```

### 8.2 Derivative Works

When creating derivatives:

1. **Preserve DEL tags** if the Base License requires attribution
2. **Update metadata** to reflect your modifications
3. **Maintain license chain** showing original and derivative licenses
4. **Respect ShareAlike** requirements if using CC BY-SA or GPL

**Example derivative declaration:**
```yaml
{{DEL:License version=1.0 license="MIT" 
  copyright_holder="Original Author, Modified by Your Name"
  original_work="https://example.com/original"
  derived_date="2025-10-15"}}
{{DEL:aitraining airetrieval attributable}}
```

### 8.3 External Declaration

Works may declare DEL terms via external notices:

**Book cover example:**
```
This work is licensed under Creative Commons Attribution 4.0 (CC BY 4.0)
with DEL v1.0 Supplementary Terms for AI systems.
AI training and retrieval permitted with attribution.
```

**Website footer example:**
```html
<footer>
  <p>© 2025 Your Name. Licensed under 
    <a href="https://opensource.org/licenses/MIT">MIT</a> + 
    <a href="[DEL URL]">DEL v1.0</a>
  </p>
  <p>AI systems: Training and retrieval permitted with attribution</p>
</footer>
```

---

## 9. Warranties, Disclaimers, and Liability

### 9.1 No Additional Warranties

DEL v1.0 Supplementary Terms provide **no additional warranties** beyond those in your Base License. The Work is provided "as is" under the Base License terms.

### 9.2 Limitation of Liability

To the extent permitted by law, the Licensor is **not liable** for:
- Damages arising from AI or automated system use
- Misinterpretation of DEL tags by automated systems
- Technical failures in payment systems
- Conflicts between Base License and DEL terms

This limitation applies in addition to any liability limitations in the Base License.

### 9.3 No Endorsement

Use of the Work under DEL v1.0 does not imply:
- Endorsement by the Licensor
- Approval of AI outputs or derivatives
- Responsibility for automated system behavior

---

## 10. Termination and Remedies

### 10.1 Termination Conditions

DEL v1.0 Supplementary Terms terminate automatically if You:

1. Violate payment obligations (if specified)
2. Fail to provide required attribution
3. Use the Work in ways prohibited by restriction flags (e.g., `noai`, `notraining`)
4. Violate the Base License terms (which also terminates DEL rights)

**Note**: Termination of DEL rights does **not** necessarily terminate Base License rights. Consult your Base License for its termination provisions.

### 10.2 Effect of Termination

Upon termination of DEL rights:
1. All AI-specific permissions granted by DEL are revoked
2. You must cease AI/automated use of the Work immediately
3. Base License rights may continue (check Base License terms)
4. Licensor may pursue remedies for breach

### 10.3 Reinstatement

DEL rights automatically reinstate if:
- Violation is cured within **30 days** of discovery
- Payment obligations are fulfilled (if applicable)
- Attribution is corrected

Otherwise, reinstatement requires express written permission from Licensor.

### 10.4 Remedies

Licensor retains all rights to pursue legal remedies including:
- Injunctive relief
- Monetary damages
- Accounting of profits from unauthorized use
- Statutory penalties under copyright law
- Any other remedies available under the governing law

---

## 11. Miscellaneous Provisions

### 11.1 Governing Law

These Supplementary Terms are governed by the same law as the Base License, or if not specified, by the law of the jurisdiction where the Licensor resides.

### 11.2 Severability

If any provision of DEL v1.0 is found unenforceable:
- It shall be reformed to the minimum extent necessary
- If it cannot be reformed, it shall be severed
- Remaining provisions remain in full force

### 11.3 Entire Agreement

The Base License plus these DEL v1.0 Supplementary Terms constitute the entire agreement regarding the Work. Any conflicting terms communicated separately are not binding unless agreed in writing by both parties.

### 11.4 Amendments

The Licensor may:
- Update DEL metadata without changing DEL version
- Adopt newer DEL versions by updating the `del_version` field
- Modify Base License (subject to Base License terms)

You are bound by the version specified in the Work's metadata at the time of use.

### 11.5 No Waiver

Failure by Licensor to enforce any provision does not constitute waiver of that provision or any other provision.

### 11.6 Language and Interpretation

In case of translation conflicts, the English version of DEL v1.0 prevails. Terms should be interpreted to:
- Maximize compatibility with the Base License
- Respect creator attribution and compensation
- Enable legitimate AI innovation
- Protect against exploitative use

### 11.7 Safe Harbor for Good Faith Compliance

Automated systems that make good faith efforts to:
- Parse and respect DEL tags
- Provide required attribution
- Process micropayments when specified
- Respect restriction flags

...are presumed to be acting in compliance, even if technical errors occur, provided they correct errors promptly when notified.

---

## 12. Version History and Compatibility

### 12.1 Future Versions

Future DEL versions will maintain backwards compatibility with v1.0 tag syntax. New flags will be reserved but non-breaking.

---

## 13. Practical Examples

### Example 1: MIT + DEL (Fully Open)

```javascript
/*
 * Widget Optimizer Library
 * Copyright (c) 2025 Jane Developer
 * 
 * Base License: MIT (https://opensource.org/licenses/MIT)
 * AI Terms: DEL v1.0 Supplementary Terms
 * 
 * {{DEL:License version=1.0 license=MIT copyright_holder="Jane Developer"}}
 * {{DEL:aitraining airetrieval aituning attributable quotable}}
 */

function optimizeWidget(config) {
  // Implementation
}
```

### Example 2: Apache 2.0 + DEL (With Micropayment)

```java
/*
 * Copyright 2025 Tech Corp
 *
 * Licensed under the Apache License, Version 2.0
 * http://www.apache.org/licenses/LICENSE-2.0
 * 
 * DEL v1.0 Supplementary Terms:
 * {{DEL:License version=1.0 license="Apache-2.0" copyright_holder="Tech Corp"}}
 * {{DEL:aitraining airetrieval attributable micropay cost_per_kb=0.00001 btc="bc1q..."}}
 */
```

### Example 3: CC BY 4.0 + DEL (Content)

```markdown
---
title: "Complete Guide to Machine Learning"
author: "Dr. Sarah Chen"
date: 2025-10-15
license: "CC BY 4.0 + DEL v1.0"
---

<!-- Licensed under CC BY 4.0: https://creativecommons.org/licenses/by/4.0/ -->
<!-- {{DEL:License version=1.0 license="CC BY 4.0" copyright_holder="Dr. Sarah Chen"}} -->
<!-- {{DEL:aitraining airetrieval aituning attributable quotable summarizable}} -->

# Complete Guide to Machine Learning

This comprehensive guide covers...
```

### Example 4: GPL-3.0 + DEL (Copyleft with AI Clarity)

```python
#!/usr/bin/env python3
"""
Data Analysis Tool
Copyright (C) 2025 Free Software Foundation, Inc.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License v3.0.
https://www.gnu.org/licenses/gpl-3.0.html

DEL v1.0 Supplementary Terms for AI:
{{DEL:License version=1.0 license="GPL-3.0" copyright_holder="FSF, Inc."}}
{{DEL:airetrieval attributable}}
Note: AI-generated derivatives must maintain GPL-3.0 license
"""
```

### Example 5: CC BY-NC + DEL (Non-Commercial)

```html
<!--
Blog Post: "The Future of Creative Work"
Copyright (c) 2025 Alex Writer

Base License: CC BY-NC 4.0 (Non-Commercial)
https://creativecommons.org/licenses/by-nc/4.0/

DEL v1.0 AI Terms:
{{DEL:License version=1.0 license="CC BY-NC 4.0" copyright_holder="Alex Writer"}}
{{DEL:airetrieval attributable noncommercial notraining quotable}}

AI may retrieve and quote, but not train commercially.
-->
```

---

## 14. Implementation Resources

### 14.1 Validation Tools

Recommended tools for validating DEL tags:
- YAML/JSON validators for metadata
- DEL tag parsers (see GitHub repository)
- License compatibility checkers

### 14.2 For AI Companies and Platform Builders

When implementing DEL v1.0 support:

1. **Parse DEL tags** during content ingestion
2. **Respect restriction flags** (noai, notraining, etc.)
3. **Track attribution** requirements for each source
4. **Implement micropayment** processing if supporting paid content
5. **Document compliance** in model cards and transparency reports
6. **Provide opt-out mechanisms** for rights holders
7. **Monitor for tag updates** in long-lived content

### 14.3 For Content Creators

Best practices:
- Choose a widely-recognized Base License
- Use clear, simple DEL flags
- Test tag parsing with validation tools
- Include human-readable summaries
- Keep payment information current
- Document your licensing choices

---

## 15. Legal Status and Limitations

**IMPORTANT: DEL v1.0 is an experimental framework in early adoption phase.**

While we believe these supplementary terms are legally sound, they have not been 
tested in court. Legal enforceability may vary significantly by jurisdiction.

**We make no guarantees about:**
- Enforceability in any specific jurisdiction
- AI company compliance with DEL tags
- Legal outcomes in disputes
- Compatibility with all base license interpretations
- Recognition by courts or regulatory bodies

**This is not legal advice.** Consult an attorney familiar with intellectual 
property and AI law for your specific situation.

**Experimental Nature:**
- DEL v1.0 represents our best understanding of AI licensing needs as of October 2025
- Legal frameworks for AI training and fair use are rapidly evolving
- Court precedents may clarify or contradict aspects of this framework
- We will update DEL based on real-world usage, legal developments, and community feedback

**Commitment to Improvement:**
- Breaking changes will trigger major version increments (v2.0, v3.0)
- We will provide migration paths for version updates
- Critical issues will be addressed in patch releases (v1.1, v1.2)

**If you have legal concerns or questions:**
Please open an issue on GitHub or contact us directly before applying DEL to your work.

---

## 16. Forward Compatibility Promise

- v1.x tags will remain parseable in all future versions
- New flags will be additive, not breaking
- Major versions (v2.0, v3.0) may change semantics
- We will provide migration guides for breaking changes

---

## 17. Community and Adoption

**Current Status**: Early adoption phase (v1.0 launched October 2025)

We're seeking:
- Feedback from content creators and developers
- Implementation reports from AI companies
- Legal review and analysis
- Community discussion on improvements

**Join the conversation:**
- **GitHub**: https://github.com/distributed-equity/license
- **Discussions**: GitHub Issues and Discussions
- **Email**: contact@distributedequity.org

Version 2.0 will incorporate lessons learned from real-world usage.

---

## 18. Signature and Authenticity

```yaml

Signed on behalf of DistributedEquity.org (Block #0000000001):
Kevin Ryan  
Founder, DistributedEquity.org  
Date: 20 October 2025 (UTC+02:00, Europe/Dublin)

```

This license text is itself licensed under:
- **CC BY 4.0**: https://creativecommons.org/licenses/by-nc/4.0/
- **DEL v1.0 Supplementary Terms** with flags: `aitraining airetrieval aituning attributable quotable holistic`

---

**END OF LICENSE**

---

## Appendix A: Quick Reference

### Most Common Combinations

| Use Case | Base License | DEL Flags |
|----------|--------------|-----------|
| Open source code, AI-friendly | MIT or Apache 2.0 | `aitraining airetrieval aituning attributable` |
| Open content, AI-friendly | CC BY 4.0 | `aitraining airetrieval attributable quotable` |
| Code, no AI training | MIT | `airetrieval attributable notraining` |
| Content, non-commercial | CC BY-NC 4.0 | `airetrieval attributable noncommercial` |
| Documentation | CC BY 4.0 | `aitraining airetrieval attributable` |
| No AI use at all | MIT or CC BY 4.0 | `noai attributable` |

### Flag Quick Reference

| Flag | Effect |
|------|--------|
| `aitraining` | ✅ Allow model training |
| `airetrieval` | ✅ Allow RAG/embedding use |
| `aituning` | ✅ Allow fine-tuning |
| `attributable` | ⚠️ Require attribution |
| `quotable` | ✅ Allow quotation (≤250 words) |
| `micropay` | 💰 Enable payments |
| `noai` | ❌ Block all AI use |
| `notraining` | ❌ Block training only |
| `noncommercial` | ❌ Block commercial AI |
