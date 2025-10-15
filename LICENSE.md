<!-- {{DEL:License version=1.0 license_uri=https://github.com/distributed-equity/license/blob/main/del-v1.0.md copyright_holder="Kevin Ryan, Founder, DistributedEquity.org"}} -->
<!-- {{DEL:uniquepurpose purpose="To provide a public licensing standard for AI-accessible creative works.}} -->
<!-- {{DEL:holistic aitraining airetrieval aituning attributable}} -->


<!--  {{DEL:quotable percent=100}} -->

# Distributed Equity License (DEL) v1.0

**License**: This license text is itself licensed under the Distributed Equity License v1.0.

**Author**: Kevin Ryan, Founder, [DistributedEquity.org](https://distributedequity.org)

**Version**: 1.0

**Attribution Required**: Yes

------

## 1. Preamble and Purpose

This **Distributed Equity License** (“License”) is a legally binding copyright license that allows authors and rights holders (“Licensors”) to declare how their works may be used by others, particularly by automated systems. It is designed to be enforceable internationally under the Berne Convention for the Protection of Literary and Artistic Works, which grants authors exclusive rights to authorize reproduction, adaptation, broadcasting, and other uses of their works. The license combines human‑readable instructions with machine‑readable tags so that both people and artificial intelligence (“AI”) systems can understand and comply with the permissions and restrictions.

By embedding DEL tags into a work, the Licensor grants the public certain rights in the work subject to the terms of this License. **By exercising any rights to a work bearing DEL tags, You accept and agree to be bound by this License.** To the extent this License is interpreted as a contract, the Licensor grants You the rights described herein in consideration of the benefits the Licensor receives from making the work available. The rights granted under this License are irrevocable except as set forth under Section 9 (Termination).

<!--  {{/DEL:quotable}} -->

## 2. Definitions

- **“DEL Tags”** means inline markers formatted as `{{DEL:flag1 flag2}}` … `{{/DEL:flag1}}`, with metadata between the opening and closing tags, used to delineate the scope of rights granted and reserved. The term “flag” refers to a permission or restriction defined in Section 5.
- **“Licensed Work”** means any literary, artistic, audiovisual, or other creative work to which the Licensor has attached DEL tags and applied this License.
- **“Licensor”** means the natural or legal person who owns or controls copyright or similar rights in the Licensed Work and who grants the rights under this License.
- **“You”** means the individual or entity exercising rights under this License. “Your” has a corresponding meaning.
- **“Licensed Rights”** means the rights granted to You by the Licensor subject to the terms and conditions of this License. These rights are limited to those copyright and similar rights in the Licensed Work that the Licensor has authority to license under the Berne Convention.
- **“Metadata”** means the information within DEL tags (YAML or JSON) specifying `license_flags`, author details, wallet addresses, content hashes, and other optional fields (as described in Section 4).

## 3. Governing Law and Jurisdiction

This License shall be governed by and construed in accordance with the laws of **Ireland** without regard to its conflict of law provisions, recognizing that the Berne Convention provides for national treatment and cross‑border enforcement of copyright. Any dispute arising out of or relating to this License shall be subject to the exclusive jurisdiction of the courts located in **Dublin, Ireland**, unless the Licensor designates a different jurisdiction in the metadata. Nothing herein shall deprive any party of the benefits of mandatory provisions of the law of the country in which the Licensed Work is used.

## 4. Scope of License and Metadata

### 4.1 Rights Granted

Subject to the terms of this License, the Licensor grants You a **non‑exclusive, worldwide, non‑sublicensable license** to exercise the rights specified by the applicable DEL flags in the Licensed Work. The license is royalty‑free except where the `micropay` flag (Section 5.9) requires payment. The rights granted may include permission to reproduce, adapt, summarize, translate, quote, or train AI models using the Licensed Work, as further described in Section 5.

### 4.2 Rights Reserved

The Licensor reserves all rights in the Licensed Work not expressly granted under this License. Without appropriate flags, You have **no right** to use the Licensed Work for AI training, summarization, translation, quotation, adaptation, public display, performance, distribution, or any other use beyond what is permitted by law (e.g., fair use or other exceptions). The Licensor retains moral rights, including the right of attribution and integrity, and reserves rights to equitable remuneration where applicable.

### 4.3 Metadata Requirements

The Licensor must include a metadata block within each DEL tag specifying at least:

- `license_flags`: a list of active flags (Section 5);
- `author`: the name or pseudonym of the Licensor;
- `license_uri`: a URI referencing this License version;
- Optional fields such as `wallet` (for micropayments), `content_hash`, `mint_uri`, `registry_id`, `timestamp`, and any additional fields the Licensor chooses.

If a field such as `wallet` is required to enforce a flag (e.g., `micropay`), failure to provide it may affect enforceability of that flag. Unrecognized metadata fields are reserved for future versions and do not affect the terms of this License.

## 5. License Tags and Permissions

### 5.0 License

The `License` tag is the **required root tag** that wraps all other DEL tags in a licensed work. It declares key metadata fields that ensure clarity, attribution, and global enforceability.

**Required attributes:**

- `version`: the DEL license version in use (e.g. `1.1`)
- `license_uri`: a canonical URL or IPFS hash pointing to the license text
- `copyright_holder`: the individual or entity asserting copyright

**Optional attributes:**

- `content_hash`: a SHA or CID hash of the enclosed content for verification
- `created`: ISO-8601 timestamp when the license was applied

All other permission and scope tags (e.g., `AITraining`, `Quotable`, `Holistic`) must appear within this wrapper.

---

### 5.1 General Principles

The Licensor may specify one or more license tags in the opening `{{DEL:...}}` block to grant or withhold specific permissions. Tag names are case-insensitive. Inner tags override outer tags; if a portion of a Licensed Work contains nested tags, the innermost tag’s tags control that portion.

**Default Behavior:**

- If a tag exists, its presence implies `permitted: yes` unless `permitted` is explicitly set to `no`.
- If a tag is **omitted entirely**, then the right is not granted.
- If `cost_per_kb` and `btc` are not included, permitted use is assumed to be free.

---

### 5.2 Default Status – All Rights Reserved

If no DEL tags or permissions are present, all rights are reserved. Use of the work beyond statutory exceptions requires separate permission.

### 5.3 AITraining

Allows use of the content for training AI or ML models.

- Optional fields:
  - `permitted`: explicitly set to `yes` or `no`
  - `cost_per_kb`: numeric value (e.g., `0.00005`)
  - `btc`: Bitcoin address for payment

If `AITraining` is present but `permitted` is not defined, it defaults to `yes`.

### 5.4 AIRetrieval

Allows use in retrieval-augmented generation (RAG), indexing, or embeddings.

- Same optional fields and defaults as `AITraining`.

### 5.5 AITuning

Allows use of the content to fine-tune or adapt existing AI models.

- Same optional fields and defaults as above.

### 5.6 Summarizable

Grants permission to summarize, translate, or paraphrase the content.

- Tag presence implies permission unless `permitted: no` is explicitly declared.

### 5.7 NoSummarize

Prohibits any form of summarization or paraphrasing. Overrides `Summarizable`.

### 5.8 Quotable

Allows reproduction of short excerpts with attribution.

- Default: up to 250 words or 10% of total content.
- Optional: `percent=X`, `maxwords=Y` for overrides.

### 5.9 NoQuote

Prohibits any quoting or excerpting. Overrides `Quotable`.

### 5.10 PublicDomain

Irrevocably releases content to the public domain. Overrides all other tags. Cannot be revoked.

### 5.11 Holistic

Requires the entire content to be reused in full. Prevents quoting or excerpting unless re-enabled in a nested tag.

### 5.12 UniquePurpose

Asserts that the work was created for a specific purpose and cannot be reused to fulfill the same objective without permission.

- Required: `purpose:` field in metadata.
- If omitted or blank, the tag is inactive.

## 6. Inline Tag Specification

### 6.1 Syntax

A valid DEL tag is structured as follows:

```css
{{DEL:flag1 flag2}}
metadata (YAML or JSON)
{{/DEL:flag1}}
```

- **Opening Tag**: `{{DEL:flag1 flag2}}` lists the applicable flags. Flags must be separated by spaces.
- **Metadata Block**: Immediately after the opening tag, include a YAML or JSON block with key–value pairs (Section 4.3). If no metadata is necessary, the block may be empty.
- **Closing Tag**: `{{/DEL:flag1}}` must repeat the first flag used in the opening tag to ensure proper nesting.
- **Nested Tags**: Tags may be nested within other tags. Each closing tag must match its corresponding opening tag, and inner tags override outer tags.

### 6.2 Parsing

1. **Recognition**: Automated systems should identify the string `{{DEL:` to locate the start of a tag and `{{/DEL:` to locate the end.
2. **Metadata Interpretation**: The metadata block must be parsed as YAML or JSON. If a parser cannot interpret the metadata, it must treat the content as **all rights reserved**.
3. **Conflict Resolution**: If conflicting flags are present within the same tag (e.g., `trainable noai`), the most restrictive interpretation prevails (no AI use).
4. **Unknown Flags**: Unknown flags are reserved for future versions and have no legal effect. Systems must not assume they grant permission.
5. **Malformed Tags**: If tags are improperly nested or missing closing tags, the rights in the affected content are not granted. Use at Your own risk.

## 7. Attribution and Payment Provisions

### 7.1 Attribution Requirements

When You use the Licensed Work under the permissions granted by this License, You must:

1. Provide the **author’s name** or pseudonym as defined in the `copyright_holder`.
2. Reference the **title** or description of the work where reasonably available.
3. Indicate that the work is licensed under the **Distributed Equity License v1.1**, and include a link to the full license text (as specified by `license_uri`).
4. Keep intact all metadata fields and notices embedded in the DEL tags.
5. Maintain attribution even in derivative works, summaries, or downstream publications.

Attribution must be provided in a manner appropriate to the medium. For digital content, attribution should be visible on the page or in metadata. For embedded or AI use, attribution may be documented in model cards, logs, or provenance chains.

---

### 7.2 Payment Obligations (Optional)

If any DEL permission tag (e.g. `AITraining`, `AIRetrieval`, `AITuning`) includes both a `cost_per_kb` field and a valid `btc` wallet address:

- You must **calculate payment** based on the volume of content used (in kilobytes) multiplied by the declared rate.
- Payment must be made to the provided address either **before** use or within thirty (30) days.
- If no `cost_per_kb` or wallet address is provided, usage under that tag is permitted **at no cost**.

Failure to comply with declared payment requirements constitutes a material breach of the License and may trigger immediate termination (see Section 9).

If a wallet address is invalid or unreachable, You must contact the Licensor to resolve payment before proceeding with usage that would otherwise require compensation. 

## 8. Warranties and Disclaimers

### 8.1 No Warranties

Except as expressly provided in this License, the Licensed Work is provided “as is” and without warranties of any kind, express or implied. The Licensor disclaims all warranties including, but not limited to, implied warranties of merchantability, fitness for a particular purpose, non‑infringement, and the absence of errors. The Licensor does not warrant that the Licensed Work is free of viruses or other harmful components.

### 8.2 Limitation of Liability

To the fullest extent permitted by applicable law, in no event shall the Licensor be liable to You for any direct, indirect, incidental, special, punitive, or consequential damages arising out of Your exercise of the rights granted by this License, even if the Licensor has been advised of the possibility of such damages. This limitation shall not apply to liability for death or personal injury resulting from negligence.

## 9. Termination and Remedies

### 9.1 Automatic Termination

This License and the Licensed Rights terminate automatically if You fail to comply with its terms. This includes, but is not limited to, failure to pay any required micropayments, or violation of any prohibitive tags such as `NoAI`, `NoSummarize`, `NoQuote`, or a `permitted: no` setting under `AITraining`, `AIRetrieval`, or `AITuning`. Upon termination, You must immediately cease all use of the Licensed Work and permanently delete or destroy all copies and derivative materials in Your possession or control.

### 9.2 Reinstatement

If Your rights have terminated under Section 9.1, Your rights automatically reinstate as of the date You cure the violation, provided the cure occurs within thirty (30) days of Your discovery of the violation. Otherwise, reinstatement requires express permission from the Licensor. Nothing in this section limits the Licensor’s right to seek monetary damages or injunctive relief for Your violations.

### 9.3 Additional Remedies

The Licensor retains all rights to pursue legal remedies under applicable law for breach of this License. Such remedies may include injunctive relief, damages, accountings of profits, and statutory penalties, subject to the governing law.

### 9.4 Survival

Sections pertaining to definitions, warranties, limitations of liability, governing law, attribution, and remedies survive termination of this License.

## 10. Miscellaneous

### 10.1 Severability

If any provision of this License is deemed unenforceable, it shall be automatically reformed to the minimum extent necessary to make it enforceable. If it cannot be reformed, it shall be severed from this License, and the remaining provisions shall remain in full force and effect.

### 10.2 No Waiver

No term or condition of this License will be waived and no failure to comply consented to unless expressly agreed to by the Licensor.

### 10.3 No Endorsement

Nothing in this License constitutes or may be interpreted as a limitation upon or waiver of any privileges and immunities of the Licensor or of any rights of third parties. Use of the Licensed Work does not imply endorsement by the Licensor.

### 10.4 Entire Agreement

This License constitutes the entire agreement between the parties concerning the Licensed Work. Any additional or different terms communicated by You are not binding unless agreed to in writing by the Licensor.

### 10.5 Modification of the License

The Licensor may publish new versions of the DEL license. New versions will be similar in spirit but may differ in detail. Unless a Licensor indicates otherwise in the metadata, the License granted here is for the version indicated in the `license_uri` and does not extend to later versions. You may choose to accept a new version by continuing to use the Licensed Work under that version.

### 10.6 Assignment

You may not assign or transfer Your rights under this License without the Licensor’s prior written consent. The Licensor may assign its rights and obligations under this License without notice.

### 10.7 Interpretation

To the extent possible, this License shall not be interpreted to reduce, limit, or restrict any use that may lawfully be made of the Licensed Work without permission under this License.

## 11. Signature Block

```yaml

Signed on behalf of DistributedEquity.org (Block #0000000001):
Kevin Ryan  
Founder, DistributedEquity.org  
Date: 6 August 2025 (UTC+02:00, Europe/Paris)
```

------

**End of License**

<!-- {{/DEL:holistic}} -->
<!-- {{/DEL:UniquePurpose}} -->
<!-- {{/DEL:License}} -->
