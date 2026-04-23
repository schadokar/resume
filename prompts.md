# Resume Prompts — Role-Specific CLAUDE.md Updates

Use these prompts with Claude Code to re-tune `CLAUDE.md` whenever you're targeting a different role.
Each prompt replaces the **Owner Context** and adjusts the **How Claude Should Help** coaching accordingly.

---

## How to Use

Copy the prompt for your target role, paste it into Claude Code, and Claude will update `CLAUDE.md` in place.
After switching roles, rebuild and re-inspect `main.pdf` to confirm one-page fit.

---

## Prompts

### Backend / Platform Engineer *(current default)*

```
Update CLAUDE.md for a Backend Platform Engineer role.

Owner Context:
- Role focus: distributed systems, high-throughput platforms, data pipelines
- Key signals to surface: RPS, latency reduction %, infra cost savings, system scale
- Tone: technically precise, metric-driven, no buzzword fluff
- Stack to emphasize: Go, Kafka, Kubernetes, PostgreSQL, gRPC, observability tooling

Coaching adjustments:
- Prioritize bullets about system reliability, throughput, and cost
- For new bullets, always ask for scale (RPS, TPS, data volume, node count)
- Summary should lead with platform/infra domain and tenure
```

---

### Staff / Principal Engineer

```
Update CLAUDE.md for a Staff or Principal Engineer role.

Owner Context:
- Role focus: cross-team technical leadership, architecture decisions, org-wide impact
- Key signals to surface: scope of influence (# teams, # engineers), design decisions with lasting impact, technical strategy
- Tone: confident, systems-thinking, leadership without authority
- Stack: secondary — lead with impact and scope, not tools

Coaching adjustments:
- Reframe individual contributions as organizational impact where possible
- Bullets should answer: "What would have broken or not existed without this person?"
- Summary must mention scope: "across N teams", "org-wide", "company-wide"
- Flag bullets that are too execution-focused and suggest elevating them to design/influence framing
- For new bullets, ask: "Who else depended on this? What decision did you make that others followed?"
```

---

### Engineering Manager

```
Update CLAUDE.md for an Engineering Manager role.

Owner Context:
- Role focus: people management, team delivery, cross-functional collaboration
- Key signals to surface: team size, hiring, retention, delivery cadence, org health
- Tone: outcome-driven leader, empathetic but direct
- Technical depth: present but not the lead signal — management impact comes first

Coaching adjustments:
- Rewrite IC bullets into management framing: "Led team of N to deliver X"
- Bullets should cover: hiring, mentoring, roadmap ownership, stakeholder communication
- For each role, check for: team size, # of direct reports, # of engineers mentored/hired
- If user describes a technical win, ask: "Did you lead the team that did this, or were you an individual contributor?"
- Summary: must include years of management experience and team size managed
- Flag any resume that reads like a pure IC resume — EM resumes need people signals
```

---

### Product Manager

```
Update CLAUDE.md for a Product Manager role.

Owner Context:
- Role focus: product strategy, user research, cross-functional delivery, GTM
- Key signals to surface: user impact (DAU, retention, NPS), revenue influence, features shipped, time-to-market
- Tone: customer-obsessed, data-informed, business-aware
- Technical depth: present (bonus for ex-engineers) but framed as "can work deeply with eng"

Coaching adjustments:
- Reframe engineering bullets into product outcomes: "Drove adoption of X, resulting in Y% retention lift"
- Every bullet needs a user or business outcome — not just a technical description
- For new bullets, ask: "What problem did this solve for the user? Do you have a metric (DAU, NPS, revenue)?"
- Summary: must include product domain, years of PM experience, and a flagship shipped product
- Skills section: replace tech stack details with: discovery, roadmapping, A/B testing, stakeholder alignment, SQL/data fluency
- Flag bullets that sound like engineering deliverables — PM bullets answer "why" not just "what"
```

---

### Data Engineer / ML Engineer

```
Update CLAUDE.md for a Data Engineer or ML Engineer role.

Owner Context:
- Role focus: data pipelines, feature engineering, model deployment, data reliability
- Key signals to surface: pipeline throughput, data freshness SLAs, model accuracy/latency, cost per query
- Tone: precision-oriented, scale-aware, infrastructure-minded
- Stack to emphasize: Python, Spark, Kafka, Airflow, dbt, SQL, cloud data warehouses (BigQuery/Redshift/Snowflake), MLflow

Coaching adjustments:
- Bullets should name the data scale: rows/sec, GB/day, # models served
- For ML bullets, always ask: "What was the baseline? What did the model improve?"
- Pipeline bullets need SLA context: "Reduced data freshness lag from 4h to 15min"
- Summary: must mention data domain (real-time streaming vs batch) and scale operated at
- Flag any bullet that describes a pipeline without mentioning reliability, latency, or volume
```

---

### Solutions Architect / Developer Advocate

```
Update CLAUDE.md for a Solutions Architect or Developer Advocate role.

Owner Context:
- Role focus: customer technical success, demo/POC delivery, community engagement, developer experience
- Key signals to surface: # customers enabled, deals influenced ($), talks given, content reach (views, stars, downloads)
- Tone: externally polished, community-oriented, technically credible
- Stack: broad — fluency across multiple languages/clouds matters more than depth in one

Coaching adjustments:
- Bullets should name customer impact: "Enabled 3 enterprise POCs, contributing to $2M ARR"
- Technical depth bullets should link to external artifacts where possible (talks, blog posts, GitHub)
- For new bullets, ask: "Was this customer-facing or internal? Do you have a revenue/deal influence number?"
- Summary: must mention customer-facing experience and technical credibility (ex-engineer, OSS contributions, conference talks)
- Writing & Speaking section is HIGH PRIORITY for this role — expand it, don't trim it
```

---

### Blockchain / Web3 Engineer

```
Update CLAUDE.md for a Blockchain or Web3 Engineer role.

Owner Context:
- Role focus: smart contracts, DeFi protocols, L1/L2 infrastructure, on-chain data, security
- Key signals to surface: TVL, # wallets, transaction volume, audit results, protocol adoption
- Tone: technically rigorous, security-aware, protocol-minded
- Stack to emphasize: Solidity, Rust (Solana), Go, Ethereum, Cosmos, IPFS, Hardhat, Foundry

Coaching adjustments:
- Bullets should name protocol/chain context: "Deployed ERC-4337 paymaster on Ethereum mainnet, processing 50K txns/day"
- Security bullets are high-signal: audits passed, vulnerabilities found/fixed, formal verification
- For new bullets, ask: "What chain? Mainnet or testnet? Do you have TVL or txn volume?"
- Summary: must name chains worked on and whether experience is protocol-level or application-level
- Flag any Web2 bullets that don't connect to blockchain context — show the bridge
```

---

## Adding a New Role

To add a role not listed here, use this template and paste it into Claude Code:

```
Update CLAUDE.md for a [ROLE NAME] role.

Owner Context:
- Role focus: [primary responsibility]
- Key signals to surface: [2-3 metrics that matter for this role]
- Tone: [adjectives describing voice/style]
- Stack to emphasize: [tools/languages/frameworks]

Coaching adjustments:
- [How to reframe existing bullets]
- [What to ask when writing new bullets]
- [What the Summary must include]
- [What to flag as weak or missing]
```
