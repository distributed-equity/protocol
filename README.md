<!-- {{DEL:License version=1.0 license_uri=https://github.com/distributed-equity/license/blob/main/del-v1.0.md copyright_holder="Kevin Ryan, Founder, DistributedEquity.org"}} -->
<!-- {{DEL:UniquePurpose purpose="To provide a public licensing standard for AI-accessible creative works."}} -->
<!-- {{DEL:Holistic AITraining AIRetrieval AITuning Attributable}} -->

[![DELv1.0:holistic aitraining airetrieval aituning attributable](https://img.shields.io/badge/DELv1.0-holistic&nbsp;aitraining&nbsp;airetrieval&nbsp;aituning&nbsp;attributable-blue?style=flat-square&cachebust=1)](https://github.com/distributed-equity/licence/blob/main/del-v1.0.md)

# The Distributed Equity License (DEL) Project

The **Distributed Equity License (DEL)** is a modular, declarative, machine-readable licensing framework built for the age of **artificial intelligence and automated creativity**.  
It ensures that **human creators retain authorship, attribution, and equitable value** when their works are used by AI systems.

---

## 📚 Repository Overview

| Repository | Description |
|-------------|-------------|
| [**manifesto**](https://github.com/distributed-equity/manifesto) | The philosophical foundation — the **Distributed Equity Manifesto (Block #0000000000)** — outlining the moral and ethical rationale behind DEL. |
| [**license**](https://github.com/distributed-equity/license) | The legal framework — the **Distributed Equity License v1.0 (Block #0000000001)** — defining the terms, tags, and enforceable permissions for creative works. |
| [**protocol**](https://github.com/distributed-equity/protocol) | The technical specification — the **DEL Protocol v1.0 (Block #0000000002)** — describing the tag syntax, metadata structure, and interoperability guidelines. |

Together, these three repositories form the **DEL Core Blocks**, defining the foundation of *Distributed Equity* — a system where creativity, consent, and compensation coexist in harmony.

---

## 🌍 Purpose and Vision

AI systems are increasingly trained on vast amounts of human creativity — often without **permission**, **attribution**, or **payment**.  
The DEL initiative provides a new, open standard to address this imbalance by embedding human intent directly into creative works.

**DEL empowers creators to:**

- Declare permissions and restrictions using **inline tags** (`{{DEL:TagName}} ... {{/DEL:TagName}}`).
- Specify whether their work may be **trained**, **retrieved**, or **fine-tuned** by AI systems.
- Receive **micropayments** or royalties when their content is used by automated agents.
- Ensure **attribution** and **provenance** remain verifiable and enforceable.

---

## 🧠 Key Concepts

### 1. **Machine-Readable Rights**
DEL transforms traditional copyright declarations into structured data that both humans and AI can interpret automatically.

### 2. **Tag-Based Permissions**
Permissions and restrictions are encoded using tags, such as:

| Tag | Description |
|------|-------------|
| `AITraining` | Allows AI or ML model training |
| `AIRetrieval` | Permits use in retrieval-augmented generation or embedding |
| `AITuning` | Allows fine-tuning or model adaptation |
| `Summarizable` | Permits summarization or translation |
| `NoSummarize` | Forbids automated summarization |
| `Quotable` | Allows short excerpts with attribution |
| `NoQuote` | Prohibits quoting or excerpting |
| `Holistic` | Requires full reuse only — no partial quotations |
| `UniquePurpose` | Declares the work created for a single defined purpose |
| `PublicDomain` | Irrevocably releases the content to the public domain |

See [Section 5 of the License](https://github.com/distributed-equity/license/blob/main/del-v1.0.md#5-license-tags-and-permissions) for formal definitions.

---

## 🧾 Core Blocks

| Block ID | Document | Repository | Purpose |
|-----------|-----------|-------------|----------|
| **#0000000000** | [Distributed Equity Manifesto v1.0](https://github.com/distributed-equity/manifesto/blob/main/manifest-v1.0.md) | `manifesto` | Foundational declaration of ethics and human-centric principles |
| **#0000000001** | [Distributed Equity License v1.0](https://github.com/distributed-equity/license/blob/main/del-v1.0.md) | `licence` | Legal and ethical framework defining rights, attribution, and enforcement |
| **#0000000002** | [DEL Protocol v1.0](https://github.com/distributed-equity/protocol/blob/main/protocol-v1.0.md) | `protocol` | Technical standard defining tag syntax, parsing, and registry operations |

---

## 🧩 How to Use DEL

1. **Include a top-level declaration** in your Markdown, article, or dataset:

   ```markdown
   <!-- {{DEL:License version=1.0 license_uri=https://github.com/distributed-equity/licence/blob/main/del-v1.0.md copyright_holder="Your Name"}} -->
   <!-- {{DEL:UniquePurpose purpose="Example use: training dataset documentation"}} -->
   <!-- {{DEL:Holistic AITraining AIRetrieval AITuning Attributable}} -->
   ```

2. **Embed permissions** within content as needed:

   ```markdown
   {{DEL:Quotable percent=5}}
   This section may be quoted up to 5 % of its length with attribution.
   {{/DEL:Quotable}}
   ```

3. **Attach metadata** such as author, content hash, or wallet address when publishing digital works.

4. **Reference the canonical license** at  
   [Distributed Equity License v1.0](https://github.com/distributed-equity/licence/blob/main/del-v1.0.md)  
   to ensure your work remains protected and machine-interpretable.

---

## 🧱 Governance and Evolution

DEL operates through **versioned blocks**, each cryptographically hashed for authenticity.  
Future versions will extend this foundation while maintaining backward compatibility, ensuring that ethical AI licensing evolves transparently.

---

## 🤝 Contributing

DEL is an open, collaborative standard.  
You can contribute by:

- Proposing new tags or metadata attributes in the [protocol repo](https://github.com/distributed-equity/protocol)
- Refining or extending legal text in the [license repo](https://github.com/distributed-equity/license)
- Contributing essays or principles in the [manifesto repo](https://github.com/distributed-equity/manifesto)

Open an issue or pull request to participate.

---

## 🪞 Learn More

- 🌐 **Website:** [DistributedEquity.org](https://distributedequity.org)  
- 📜 **Manifesto:** [manifest-v1.0.md](https://github.com/distributed-equity/manifesto/blob/main/manifest-v1.0.md)  
- ⚖️ **License:** [del-v1.0.md](https://github.com/distributed-equity/license/blob/main/del-v1.0.md)  
- 🧩 **Protocol:** [protocol-v1.0.md](https://github.com/distributed-equity/protocol/blob/main/protocol-v1.0.md)

---

© 2025 Kevin Ryan, [DistributedEquity.org](https://distributedequity.org).  
Released under the [Distributed Equity License v1.0](https://github.com/distributed-equity/license/blob/main/del-v1.0.md).

<!-- {{/DEL:Holistic}} -->
<!-- {{/DEL:UniquePurpose}} -->
<!-- {{/DEL:License}} -->
