# Kiln: Product Requirements Document

*Working title. An AI-powered UI component marketplace where every component is certified, adapts to your codebase, and is usable by developers and AI agents alike. Advanced PRD.*

| Field | Value |
| --- | --- |
| Version | 1.0 (Draft for executive and engineering review) |
| Status | In review |
| Owner | Head of Product (to be assigned) |
| Contributors | Engineering, Design, Data/AI, Security, Legal, Marketplace Ops, Finance |
| Audience | Founders, investors, engineering leads, designers, partnerships, trust and safety |
| Review cadence | Every two weeks during Phase 0 and Phase 1 |
| Conventions | Priorities: **P0** launch blocker, **P1** fast follow, **P2** later. Requirement IDs use the pattern M{module}-{n}. All numeric targets are planning assumptions to be validated in Phase 0. |

---

## 1. Executive Summary

UI components are sold, shared and generated in ways that all fail developers in the same place: **the last mile**. A component that looks perfect on a preview page still has to be rewired to the buyer's framework, styling system, design tokens, lint rules and accessibility bar. Template marketplaces ship static zip files. Open-source copy-paste libraries ship one opinionated style. AI UI generators produce plausible code with no guarantee of accessibility, maintenance or provenance.

**Kiln is a marketplace built around the last mile.** Its thesis: as AI makes generic UI code nearly free, the scarce and valuable things become *trust, fit and upkeep*. Kiln therefore sells verified outcomes, not files.

| Pillar | What it means | Signature capability |
| --- | --- | --- |
| **Certified** | Every version is automatically tested and scored before and after listing | **Quality Passport** (accessibility, performance, security, compatibility, maintenance) |
| **Adaptive** | Components are installed into *your* repo, using *your* tokens and conventions | **Fit Engine** (opens a verified pull request, or refunds you) |
| **Agent-ready** | Components describe themselves in a machine-readable contract so AI coding agents can search, choose and install them correctly | **Component Manifest** and **Kiln MCP Server** |
| **Fair** | Creators are paid for real usage, including when AI composes their work into new output | **Attribution Ledger** and usage-weighted subscription pool |

**Tagline:** *Components that fit your codebase, proven before you buy.*

**18-month ambition (planning targets):** 150,000 registered developers; 3,000 listed components with at least 60% at Verified tier or above; 1,500 active creators; 40,000 weekly active developers; annualised gross merchandise value of USD 6 million; creator payouts above 80% of GMV.

---

## 2. Market Context and Opportunity

### 2.1 Why now

1. **AI code generation commoditises generic UI code.** A button, card or table is a prompt away. What remains scarce is code that is accessible, tested, maintained, secure and consistent with a team's system.
2. **Own-the-code distribution is normal.** Copy-paste registries trained developers to expect source in their repo rather than opaque packages, which suits an adaptive installer.
3. **AI agents are now component consumers.** Coding assistants pick libraries from training data. Components with machine-readable contracts will win agent selection; those without will be invisible.
4. **Accessibility regulation is tightening.** The European Accessibility Act has applied since June 2025, WCAG 2.2 is the working standard, and litigation risk is rising. Buyers will pay for demonstrable conformance.
5. **Design tokens are standardising.** A community format for design tokens makes cross-system theming feasible at scale.
6. **Supply-chain anxiety.** Teams are wary of unvetted dependencies; signed, scanned, provenance-attested components are a purchasing criterion.

### 2.2 Segments

| Segment | Buying behaviour | Primary value | Notes |
| --- | --- | --- | --- |
| Indie developers and startups | Self-serve, price sensitive, speed-driven | Ship polished UI fast | Volume and community engine |
| Agencies and freelancers | Multi-project, licence-sensitive | Reuse with clear client licensing | High repeat purchase |
| Product teams in scale-ups | Team plans, quality-driven | Consistency, accessibility, upkeep | Core revenue segment |
| Enterprises and design-system teams | Procurement, security review | Governance, private registry, audit | Highest contract value |
| AI-agent platforms and IDE vendors | Partnership and API | Reliable component supply for agents | Strategic distribution |
| Creators (designer-developers, studios, OSS maintainers) | Supply side | Income, audience, tooling | Must be treated as customers |

Market sizing will be built bottom-up in Phase 0 from developer population, framework share, current spend on templates and UI kits, and team-plan willingness to pay (see Section 20).

---

## 3. Problem Statement

| # | Problem | Affected | Consequence |
| --- | --- | --- | --- |
| P1 | Components do not fit the buyer's stack, tokens or conventions | Buyers | Hours to days of rewriting; abandoned purchases |
| P2 | Quality is unknowable before purchase (accessibility, performance, SSR, bundle size) | Buyers, teams | Hidden remediation cost and legal exposure |
| P3 | Marketplaces sell static files with no update path | Buyers | Drift, security debt, forked-and-forgotten code |
| P4 | AI generators produce unverified, unattributed code | Buyers, creators | Inconsistent output; creators' work absorbed without credit or pay |
| P5 | AI agents cannot reliably choose or use components | Agent users | Hallucinated APIs, mismatched props, generic UI |
| P6 | Teams cannot govern which components enter their codebase | Design-system leads, security | Shadow dependencies, inconsistent UX, licence risk |
| P7 | Creators face piracy, unfair revenue share, discovery lottery, and heavy support burden | Creators | Supply is thin and quality uneven |
| P8 | Licence terms are unclear for client work, SaaS, and AI-assisted use | Agencies, enterprise | Legal risk blocks adoption |

---

## 4. Users, Personas and Jobs-to-be-Done

| Persona | Profile | Core jobs-to-be-done | Success looks like |
| --- | --- | --- | --- |
| **Ravi, Frontend Engineer** | 5 years experience, React and Tailwind, tight sprint | When I need a data table, help me add an accessible, on-brand one without rewriting it | Merged PR in under 15 minutes |
| **Sara, Solo Founder** | Full-stack, no designer | When I build an MVP, give me a coherent, polished set of screens that look like one product | Whole dashboard themed consistently in an afternoon |
| **Elena, Design-System Lead** | Owns a 40-person product org's UI standards | When teams add UI, keep it compliant with our tokens, accessibility bar and licences | Zero unapproved components in production |
| **Tom, Agency Principal** | Delivers 12 client sites a year | When I reuse components, make licence and attribution clear per client | One licence, many client projects, audit-ready |
| **Mei, Creator** | Designer-developer with an audience | When I publish, protect my work, show its quality, and pay me fairly for use | Predictable monthly income, low support load |
| **Olivia, Security and Procurement** | Reviews third-party code | When we adopt a component source, give me provenance, SBOM, and policy controls | Approval in days, not months |
| **Agent, AI Coding Assistant (machine persona)** | Acts on a developer's behalf | When asked to build a screen, find, compare, preview and install the right components | Correct install, no invented props, human approves |
| **Curator, Marketplace Moderator** | Trust and safety staff | When submissions arrive, flag risk quickly and fairly | Fast, consistent, appealable decisions |

---

## 5. Vision, Principles and Positioning

**Vision:** Become the trusted supply layer for user interfaces, where any developer or AI agent can obtain a verified component that already fits the destination, and where the people who craft components are paid for the value they create.

**Positioning statement:** For product teams and AI-assisted developers who need production-grade UI fast, Kiln is the component marketplace that certifies quality, adapts to your codebase, and speaks to your AI tools, unlike template stores and generators that hand you unverified files.

### Principles

1. **Outcomes over files.** We sell a component that works in your repo, not a download.
2. **Proof before purchase.** Every claim (accessible, fast, SSR-safe) is measured and shown.
3. **Your code, your control.** Source lands in the buyer's repo; no lock-in runtime required.
4. **Humans approve, agents assist.** Agents can prepare installs; humans merge them.
5. **Creators are partners.** Transparent metrics, fair splits, strong protection, opt-in for AI uses.
6. **Open where possible.** Open manifest and registry formats; interoperate with existing registries and token standards.
7. **Secure by construction.** Treat every component as untrusted code until proven otherwise.
8. **Accessible by default.** The marketplace itself meets WCAG 2.2 AA; no exceptions.

---

## 6. Differentiation and Competitive Landscape

### 6.1 Landscape

| Category | Strengths | Gaps | Kiln's answer |
| --- | --- | --- | --- |
| Template and UI-kit marketplaces | Large catalogue, familiar buying | Static files, no fit, uneven quality, no updates | Fit Engine, Passport, update PRs |
| Open-source copy-paste libraries | Great developer experience, free, own-the-code | One style, limited commercial depth, no certification, no creator income | Multi-style catalogue, paid creators, governed registry (compatible with existing registry format) |
| Component libraries (design-system packages) | Mature, versioned, supported | Heavy runtime, hard to restyle, lock-in | Source-first, token-mapped, no mandatory runtime |
| AI UI generators | Instant, flexible | Unverified quality, no provenance, inconsistent systems | Grounded generation in certified parts; gated publishing; attribution |
| Design-tool kits | Strong visual craft | Not production code | Figma-to-code link through manifest and tokens |

### 6.2 Ten differentiators

| # | Differentiator | Why it is hard to copy |
| --- | --- | --- |
| 1 | **Fit Engine:** verified, adapted installs as pull requests | Needs repo-aware transforms plus build, type, lint, test and visual verification at scale |
| 2 | **Quality Passport:** continuous certification | Requires an expensive test harness (browsers, assistive-tech simulation, perf lab) and trusted methodology |
| 3 | **Component Manifest:** typed, agent-readable contract | Network effect: creators adopt it because agents and buyers demand it |
| 4 | **Kiln MCP Server:** agents search, preview and stage installs | Depends on manifest depth and safe-install design |
| 5 | **Brand-Fit Preview:** see any listing rendered with your tokens before buying | Needs a token engine and sandboxed rendering |
| 6 | **Attribution Ledger:** royalties when AI composes from multiple components | Needs lineage tracking and creator trust |
| 7 | **Update PRs with semantic diff:** API and visual diffs decide major, minor, patch | Prevents silent breakage; data-intensive |
| 8 | **Governed private registry:** policy, SBOM, drift detection | Enterprise-grade controls on top of a public marketplace |
| 9 | **Fit-or-refund guarantee:** failed adaptation triggers automatic credit | Operationally risky for competitors; Kiln's verification makes it viable |
| 10 | **Provenance and signing:** attested builds, per-licence fingerprints | Supply-chain trust as a feature |

---

## 7. Goals, Non-Goals and Success Metrics

### 7.1 Goals

- **G1:** Cut time from need to merged component to under 15 minutes.
- **G2:** Make quality visible and trustworthy through certification.
- **G3:** Become the default component source for AI coding agents.
- **G4:** Build a healthy two-sided marketplace with strong creator retention and income.
- **G5:** Win team and enterprise accounts through governance and compliance.
- **G6:** Maintain zero-tolerance security and IP standards.
- **G7:** Keep unit economics positive despite AI and compute costs.

### 7.2 Non-Goals (initial releases)

- Not a full app or website builder, and not a hosting platform.
- Not a proprietary runtime component library with mandatory dependencies.
- Not full-page templates in v1 (blocks and compositions arrive in Phase 3).
- Not native mobile in v1 (web frameworks first).
- Not a design tool; Kiln integrates with design tools rather than replacing them.

### 7.3 North Star and Metric Tree

**North Star: Merged Integrations per Week**, meaning component installs whose pull request is merged (or applied) and still present in the repo after 30 days.

| Layer | Metric | 6 months | 12 months | 18 months |
| --- | --- | --- | --- | --- |
| Demand | Weekly active developers | 5,000 | 20,000 | 40,000 |
| Demand | Search-to-install conversion | 4% | 7% | 10% |
| Fit | Fit Engine first-pass success (builds, types, lint, tests green) | 70% | 82% | 90% |
| Fit | Median time from click to PR | under 4 min | under 2 min | under 90 s |
| Quality | Share of GMV from Verified or higher | 40% | 60% | 75% |
| Quality | Post-install defect reports per 1,000 installs | under 25 | under 12 | under 6 |
| Supply | Active creators (published or updated in 90 days) | 150 | 700 | 1,500 |
| Supply | Median creator monthly payout (top half) | USD 300 | USD 800 | USD 1,500 |
| Agents | Share of installs initiated through MCP or CLI | 10% | 30% | 45% |
| Revenue | Annualised GMV | USD 0.5M | USD 2.5M | USD 6M |
| Retention | Team-plan net revenue retention | n/a | 105% | 115% |
| Trust | Confirmed piracy or malicious-component incidents reaching customers | 0 | 0 | 0 |

**Guardrail metrics:** refund rate under 6%; creator takedown dispute resolution under 7 days; marketplace accessibility audit pass; AI cost per install under 8% of net revenue.

---

## 8. Marketplace Economics and Business Model

### 8.1 Licensing and pricing models

| Model | Description | Typical buyer |
| --- | --- | --- |
| **Free (open licence)** | MIT or similar; creators gain reach, optional sponsorship | Everyone; funnel |
| **Single licence** | One developer, unlimited own projects, one product line | Indie, freelancers |
| **Team licence** | Up to N seats, per-seat renewals for updates | Product teams |
| **Agency licence** | Multiple client projects with transfer terms | Agencies |
| **Enterprise licence** | Org-wide, private registry, indemnity options | Enterprises |
| **Kiln Pro subscription** | Access to all Verified components plus AI Studio credits; revenue shared with creators via usage pool | Regular buyers, teams |

Licence terms are machine-readable (SPDX-style identifier plus Kiln licence schema), embedded in the manifest, and enforced by policy in the registry and CLI.

### 8.2 Creator revenue share

| Creator tier | Share of net sale | Qualifier |
| --- | --- | --- |
| Standard | 80% | Listed, Passport above minimum |
| Certified | 85% | Verified tier on 3 or more components, low defect rate |
| Gold Partner | 88% | Gold tier, sustained maintenance, strong support SLA |
| Founding Creator (first 12 months) | 90% | Invited cohort, plus guaranteed minimum payout for 6 months |

Payments are in local currency where supported, with payout thresholds, transparent fees, and monthly statements. Subscription-pool payouts are described in Appendix C.

### 8.3 Kiln revenue streams

1. Marketplace commission (see 8.2).
2. Pro and Team subscriptions (net of creator pool, target 70% distributed to creators).
3. Enterprise private registry and governance plans (annual contracts).
4. AI Studio credits and overage.
5. Partner programmes (agent platforms, IDE integrations, training and certification).

### 8.4 Unit economics guardrails

- Fit Engine compute plus AI cost per successful install below 8% of net revenue per install; deterministic transforms handle most cases before AI is invoked.
- Passport pipeline cost per version capped; heavy audits (assistive-tech simulation, cross-browser matrix) run on release candidates and nightly samples.
- Fit-or-refund reserve funded at 1.5% of GMV.

### 8.5 Marketplace health principles

- **Anti-concentration:** discovery ranking blends quality, freshness, fit rate and novelty so new creators are not buried.
- **Anti-spam:** deduplication and similarity detection; low-effort clones are delisted.
- **Quality floor:** below-threshold components cannot be sold, only improved.
- **Transparency:** creators see installs, fit rates, defect reports, refunds, and search impressions.

---

## 9. Product Surface Map

| Surface | Primary users | Purpose | Phase |
| --- | --- | --- | --- |
| **Web Marketplace** | Developers, teams | Discover, preview, compare, buy | 1 |
| **Live Playground** | Developers, creators | Interact with components in a secure sandbox, with your tokens | 1 |
| **Kiln CLI** | Developers, CI | Search, install, update, publish, verify | 1 |
| **GitHub and GitLab App** | Developers, teams | Repo scan, Fit Engine pull requests, update PRs, drift reports | 1 |
| **Creator Studio** | Creators | Publish, price, analyse, support, protect | 1 |
| **Kiln MCP Server** | AI agents and their users | Machine-readable search, preview, compatibility, staged install | 2 |
| **IDE Extensions** (VS Code, JetBrains) | Developers | In-editor search and install, inline Passport | 2 |
| **Figma Plugin** | Designers | Export tokens, find matching components, publish design specs | 2 |
| **AI Studio** | Developers, creators | Generate, remix, improve components, grounded in the catalogue | 2 |
| **Team Console** | Design-system leads, security | Private registry, policies, SBOM, seats, audit | 2 |
| **Admin and Trust Console** | Kiln staff | Moderation, takedowns, payouts, risk, support | 1 |
| **Public API and Webhooks** | Partners | Catalogue, Passport, installs, ledger data | 3 |

---

## 10. Functional Requirements

Each module lists requirements as **ID, Requirement, Priority, Acceptance Criteria**. Where a criterion states a number, it is a testable launch gate.

### M1. Discovery and Search

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M1-1 | Hybrid semantic and keyword search across components, manifests and docs | P0 | p95 latency under 300 ms; NDCG@10 of 0.70 or higher on the curated relevance set |
| M1-2 | Facets: framework and version, styling system, Passport tier, accessibility level, bundle size, SSR support, licence, price, freshness, token compatibility | P0 | All facets combinable; counts update in under 200 ms |
| M1-3 | **Brand-Fit Preview:** upload design tokens (JSON), paste from Figma variables, or connect a repo; all listings render themed | P0 | Preview renders in under 2 s; token mapping coverage shown (for example 14 of 16 tokens mapped) |
| M1-4 | Natural-language screen search: describe a screen and receive a proposed set of components | P1 | At least 4 of top 6 suggestions rated relevant by reviewers |
| M1-5 | Visual search from screenshot or Figma frame | P1 | Top-5 relevance of 60% or higher on benchmark set |
| M1-6 | Curated collections and coherent Kits (components designed to work together) | P1 | Kits show combined Passport and combined bundle cost |
| M1-7 | Side-by-side comparison of Passport, API, size, price, update history | P1 | Up to 4 components compared |
| M1-8 | Stack-aware recommendations using the user's Stack Profile | P1 | Incompatible components hidden by default, with a toggle |
| M1-9 | Indexable SEO pages for every listing with server-rendered preview and structured data | P0 | Core Web Vitals pass; pages crawlable |
| M1-10 | Saved lists, follow creators and components, update and price alerts | P2 | Notifications opt-in per type |

### M2. Listings and the Component Manifest

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M2-1 | Listing page: live preview, states and variants, code view, Passport summary, changelog, licence, support policy, creator profile, reviews | P0 | No purchase-critical information requires leaving the page |
| M2-2 | **Component Manifest** required to publish (schema in Appendix B) | P0 | Publish blocked unless schema validates and examples render |
| M2-3 | Auto-generated API documentation from TypeScript types and manifest | P0 | Props, slots, events, CSS variables, and default values all documented |
| M2-4 | **Interaction and accessibility contract:** roles, keyboard map, focus management, live-region behaviour | P0 | Contract is executable: Passport runs it as tests |
| M2-5 | **Token contract:** semantic tokens consumed, with fallbacks and allowed override points | P0 | Components using undeclared raw values fail lint with a Passport penalty |
| M2-6 | Composition hints: works-well-with graph and anti-patterns | P1 | Surfaced to buyers and agents |
| M2-7 | Versioning with **semantic diff**: API diff plus visual diff decide major, minor or patch | P0 | Mislabelled releases are blocked or auto-corrected with creator confirmation |
| M2-8 | Dependency disclosure: runtime packages, licences, size contribution | P0 | Shown before purchase; policy-checkable |
| M2-9 | Multi-framework adapters listed under one component identity | P1 | Adapter parity score displayed |
| M2-10 | Localisation and RTL declarations, verified by tests | P1 | Declared locales rendered in visual suite |

### M3. Live Playground and Sandbox

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M3-1 | Editable playground running in an isolated, cross-origin sandbox with no network access by default | P0 | Cold start under 2 s; CSP and permissions policy enforced; escape tests pass |
| M3-2 | Controls panel generated from props schema | P0 | Every documented prop controllable or marked non-interactive |
| M3-3 | Viewport and theme matrix: light, dark, high contrast, RTL, 200% text scaling | P0 | One-click toggles; state preserved |
| M3-4 | Reduced-motion and forced-colours simulation | P1 | Matches Passport tests |
| M3-5 | Live performance panel: render time, re-render count, DOM node count | P1 | Updates as props change |
| M3-6 | Accessibility overlay: focus order, landmarks, contrast checks, accessible-name inspector | P1 | Findings link to Passport rules |
| M3-7 | Shareable playground URLs that encode state | P1 | No personal data encoded |
| M3-8 | Try-with-my-data: sandbox with the user's tokens and sample JSON | P1 | Data stays in the browser |

### M4. Fit Engine (Adaptive Install)

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M4-1 | Repo connection through GitHub and GitLab apps with least-privilege scopes: read for scan, write only by pull request | P0 | No direct commits to default branch; scope list shown before consent |
| M4-2 | **Stack Profile** detection: framework and version, bundler, TypeScript config, styling system, token source, lint and format rules, test framework, i18n library, path aliases, package manager, monorepo layout | P0 | 95% or higher accuracy on a 200-repo benchmark; user can correct any field |
| M4-3 | **Tier 1: deterministic transforms**: import paths, aliases, file layout, utility classes, token mapping, dependency deduplication, naming conventions | P0 | Handles 60% or more of installs without AI |
| M4-4 | **Tier 2: AI-assisted adaptation** restricted to component files and declared extension points; every edit logged with reason | P1 | Edits outside allowed paths are rejected automatically |
| M4-5 | **Verification gate** in an ephemeral clone: install, type-check, lint, build, unit tests, accessibility tests, visual comparison against the preview | P0 | PR labelled Verified only when all gates pass; otherwise labelled Needs Review with failures listed |
| M4-6 | **Pull request package:** component source, token mapping file, tests, usage docs, licence file, install report, rollback steps | P0 | Install report explains every non-trivial change |
| M4-7 | **Fit-or-refund:** if verification cannot pass after bounded attempts, purchase is credited automatically | P0 | Credit issued within 1 minute; reason code logged |
| M4-8 | Pre-purchase Fit Preview: shows predicted files changed, token coverage, and estimated bundle impact without exposing paid source | P1 | Prediction accuracy within 10% on benchmark |
| M4-9 | CLI mode for local installs when repo access is not granted | P0 | Same transforms, run locally, no code uploaded |
| M4-10 | **Update PRs:** on new versions, open a PR using three-way merge that respects local modifications | P1 | Conflicts flagged inline; breaking changes called out |
| M4-11 | **Drift detection:** compare installed code with registry version; offer to upstream, re-sync, or mark as fork | P1 | Weekly drift report per repo |
| M4-12 | Multi-component installs (Kits) with shared token mapping and deduplicated dependencies | P1 | One PR per Kit |
| M4-13 | Clean uninstall PR | P1 | Removes files, tokens and unused dependencies |
| M4-14 | Privacy: repo content processed ephemerally; no retention beyond the run; never used for model training; diagnostics opt-in | P0 | Verified by third-party audit and documented data-flow |

### M5. AI Studio

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M5-1 | Prompt-to-component generation grounded in the catalogue, the user's Stack Profile and tokens | P1 | Generated component compiles in the target stack 90% of the time |
| M5-2 | Outputs bundled: component, draft manifest, tests, docs, preview | P1 | Manifest passes schema validation |
| M5-3 | **Remix:** fork a licensed component with enforced attribution lineage and creator remix permissions | P1 | Lineage recorded in the Attribution Ledger |
| M5-4 | Improve actions: add accessibility, add variants, add dark mode, convert framework, reduce bundle size | P1 | Before and after Passport scores shown |
| M5-5 | Generated output labelled **AI-assisted**; eligible for Kiln certification only after full Passport run | P1 | Label cannot be removed |
| M5-6 | **Verbatim-reproduction guard:** block output that matches catalogue code beyond a similarity threshold unless the user holds a licence | P0 (for any AI release) | False-negative rate under 1% on red-team set |
| M5-7 | Credits, quotas and spend caps per user and team | P1 | Hard caps enforceable |
| M5-8 | Prompt and output history with export | P2 | Retention controls available |

### M6. Quality Passport

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M6-1 | Automated pipeline on every version submission: build, static analysis, tests, accessibility, performance, compatibility, security, visual regression | P0 | Median completion under 15 minutes; reproducible logs |
| M6-2 | **Accessibility suite:** automated rules engine plus executable keyboard and focus scripts from the manifest contract; contrast across all themes; reduced motion; forced colours; reflow at 200% zoom | P0 | Zero critical violations to list; false-positive rate under 5% |
| M6-3 | Assistive-technology simulation and manual expert audit for Gold tier | P1 | Audit report attached; audit refreshed yearly |
| M6-4 | **Performance lab:** minified and compressed size, tree-shaking, render time, re-render counts, layout shift and interaction cost, mount and unmount leak tests | P0 | Declared bundle budget must hold within 5% |
| M6-5 | **Compatibility matrix:** evergreen browsers, framework version ranges, SSR, streaming and server components, strict mode | P0 | Matrix shown on listing; failures reduce score |
| M6-6 | **Security and supply chain:** vulnerability scan, malware heuristics, detection of eval, dynamic remote imports and undisclosed network calls, secret scan, licence compatibility, signed provenance | P0 | Any high-severity finding blocks listing |
| M6-7 | Visual regression across states, themes, viewports and browsers | P0 | Baselines versioned; diffs approved by creator |
| M6-8 | Maintenance health: update cadence, issue response times, SLA adherence | P1 | Feeds score and discovery ranking |
| M6-9 | Tiers: **Listed**, **Verified** (score 75 or higher, no gate failures), **Gold** (score 90 or higher, manual audit) | P0 | Public report per version |
| M6-10 | Continuous re-certification against new browser and framework releases | P1 | Regressions notify creators and demote after grace period |
| M6-11 | Creator dispute and re-test process | P1 | Response within 3 business days |
| M6-12 | Passport API for third-party consumption | P2 | Versioned, rate-limited |

### M7. Creator Studio

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M7-1 | Creator onboarding with identity, tax and payout verification | P0 | Compliant KYC in supported countries |
| M7-2 | Publish from Git repository (GitHub app) or CLI (`kiln publish`) | P0 | Tag-triggered releases supported |
| M7-3 | Manifest authoring assistant that infers props, accessibility contract and examples from source | P1 | 80% of fields correct without edits |
| M7-4 | Pre-publish Passport dry run with prioritised, actionable fixes | P0 | Each failure links to a fix guide |
| M7-5 | Pricing, licences, bundles, launch discounts, regional pricing | P0 | Changes audited and versioned |
| M7-6 | Analytics: impressions, previews, installs, fit rate, defect reports, refunds, revenue, search terms | P0 | Data latency under 1 hour |
| M7-7 | Support inbox with templates, issue triage and SLA indicators | P1 | Auto-routing of defect reports with logs attached |
| M7-8 | Semver enforcement via semantic diff | P0 | Breaking change cannot ship as patch |
| M7-9 | **AI controls:** opt in or out of catalogue grounding, remix permissions, ledger participation | P0 | Defaults are opt-in; changes take effect within 24 hours |
| M7-10 | Piracy dashboard: fingerprint matches, leak alerts, takedown tooling | P1 | Takedown filed in 3 clicks |
| M7-11 | Co-creator splits and organisation accounts | P1 | Payouts split automatically |
| M7-12 | Creator programme: tiers, founding cohort, grants | P1 | Eligibility automated from metrics |

### M8. Commerce, Licensing and Payouts

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M8-1 | Checkout with cards, wallets and regional methods; tax handled by a merchant-of-record or tax engine | P0 | Correct tax and invoice in all launch regions |
| M8-2 | Machine-readable licence issued with each entitlement (per developer, per seat, per project, agency transfer) | P0 | Licence embedded in installs and visible to policy engine |
| M8-3 | Entitlement service authorises CLI, registry and PR installs with scoped, revocable tokens | P0 | Revocation effective within 5 minutes |
| M8-4 | Refund policy: automatic credit for failed fit or confirmed defect; 30-day window for other cases | P0 | Self-serve; abuse detection on repeated claims |
| M8-5 | Monthly creator payouts, multi-currency, thresholds, tax forms, statements | P0 | Reconciles to the cent with ledger |
| M8-6 | Subscription-pool distribution engine (formula in Appendix C) | P1 | Transparent per-creator breakdown |
| M8-7 | **Attribution Ledger:** immutable, auditable record of component usage lineage and royalty allocation, including AI-composed output | P1 | Creators can export their ledger lines; disputes tracked |
| M8-8 | Coupons, bundles, student, OSS-maintainer and regional pricing | P1 | Stackable rules with caps |
| M8-9 | Fraud and chargeback controls: velocity checks, risk scoring, licence-sharing detection | P0 | Chargeback rate under 0.5% |
| M8-10 | Enterprise quotes, purchase orders, annual invoicing | P1 | Sales-assisted flow with approvals |
| M8-11 | Sponsorship and tipping for free components | P2 | Funds routed with the same payout engine |

### M9. Teams, Private Registry and Governance

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M9-1 | Organisations with roles (Owner, Admin, Maintainer, Member, Auditor); SSO via SAML and OIDC; SCIM provisioning | P1 | Deprovisioning removes access within 15 minutes |
| M9-2 | **Private registry** for internal components with the same Fit Engine and Passport | P1 | Standard registry protocol supported; private data never visible publicly |
| M9-3 | **Policy engine:** allowed licences, minimum Passport tier, banned dependencies, bundle budgets, required accessibility level, approved creators | P1 | Enforced in CLI, CI check, PR bot and MCP |
| M9-4 | Approval workflows for new components with reviewer comments | P1 | Approvals logged and reversible |
| M9-5 | SBOM export (SPDX, CycloneDX) and signed provenance attestations | P1 | Generated per install and per release |
| M9-6 | Audit log with SIEM export | P1 | Every install, policy decision, role change recorded |
| M9-7 | Seat management, usage and cost allocation by team | P1 | Monthly report; budget alerts |
| M9-8 | Organisation-wide token profile as the single source for Brand-Fit and Fit Engine | P1 | Versioned; changes trigger re-fit suggestions |
| M9-9 | Vulnerability alerts for installed components with auto-fix PRs | P1 | Alert within 1 hour of confirmed advisory |
| M9-10 | Data residency choices and dedicated tenancy | P2 | EU and US regions at minimum |
| M9-11 | Contribute internal components to the public marketplace after review | P2 | Redaction and licence checks enforced |

### M10. Integrations: CLI, MCP, IDE, Figma and CI

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M10-1 | CLI commands: login, search, info, add, update, verify, publish, doctor; JSON output; offline cache | P0 | Usable in CI without interactive prompts |
| M10-2 | **MCP Server** tools: search\_components, get\_manifest, preview\_with\_tokens, check\_compat, propose\_install, compose\_screen\_plan | P1 | Tool descriptions pass agent-compatibility tests with at least 3 major agent platforms |
| M10-3 | **Agent safety:** agent-initiated installs are staged as pull requests or local diffs and require human approval; manifest and README text is sanitised against instruction injection | P1 | Red-team prompt-injection suite passes; no auto-merge path exists |
| M10-4 | Agent attribution: installs tagged by originating agent platform for partner analytics | P1 | Aggregated, privacy-safe reports |
| M10-5 | IDE extensions with inline Passport, install, and update prompts | P1 | Works offline for cached components |
| M10-6 | **Figma plugin:** export variables to the token profile; match selected frames to catalogue components with confidence; designers attach specs | P1 | Match confidence shown; no design data stored without consent |
| M10-7 | CI action running policy and verification on pull requests | P1 | Fails build on policy violation |
| M10-8 | Standard registry endpoint so existing component CLIs can install from Kiln | P1 | Entitlements still enforced |
| M10-9 | Storybook and visual-testing tool interop for creator imports | P2 | Stories reused as examples |
| M10-10 | Public API and webhooks | P2 | Versioned; OAuth scopes; rate limits |

### M11. Trust, Safety and Intellectual Property

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M11-1 | Submission risk scoring with human review for first-time creators and high-risk flags | P0 | Median review time under 24 hours |
| M11-2 | **Similarity detection** (syntax tree, embeddings, visual fingerprint) against catalogue and public open-source code | P0 | Recall of 95% or higher on a planted-clone test set |
| M11-3 | Third-party code provenance declaration and licence scanning | P0 | Undeclared copyleft blocks listing |
| M11-4 | Per-licence fingerprinting of delivered source for leak tracing | P1 | Survives formatting and renaming transforms |
| M11-5 | Notice-and-takedown and counter-notice workflow with defined SLAs | P0 | Acknowledgement within 24 hours |
| M11-6 | **Kill switch:** revoke a version registry-wide, notify installers, and open removal or patch PRs | P0 | Revocation propagates in under 10 minutes |
| M11-7 | Review integrity: only verified installers can review; fake-review detection | P0 | Detection precision of 90% or higher |
| M11-8 | Creator conduct policy and appeals | P0 | Appeal decided within 7 days |
| M11-9 | Deceptive-pattern policy: components designed to mislead users (for example disguised opt-outs) are not listed | P1 | Reviewer guideline and automated heuristics |
| M11-10 | Enforcement of AI-use consent flags across search, grounding and generation | P0 | Audit shows zero use of opted-out components |

### M12. Community, Reviews and Support

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M12-1 | Verified-install reviews with sub-ratings for fit, quality, docs and support | P0 | Sub-ratings feed ranking |
| M12-2 | Per-component Q&A and issue tracker, linked to Passport findings | P1 | Creator response time visible |
| M12-3 | Buyer support with SLA, escalation to creator, and Kiln mediation | P1 | Resolution time tracked |
| M12-4 | Creator profiles, portfolios and following | P1 | Verified badges and tiers displayed |
| M12-5 | Documentation hub, tutorials, changelog | P0 | Searchable; versioned |
| M12-6 | Showcase of products built with Kiln components; community jams | P2 | Opt-in features |

### M13. Admin and Operations

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M13-1 | Role-based admin console with full audit trail | P0 | Every privileged action logged |
| M13-2 | Moderation queues with decision templates and escalation | P0 | Decision consistency audited quarterly |
| M13-3 | Feature flags and experimentation framework | P0 | Per-segment rollout; instant kill |
| M13-4 | Finance operations: payout reconciliation, reserves, tax reporting | P0 | Month-end close in under 3 business days |
| M13-5 | Catalogue curation: featuring, collections, taxonomy management | P0 | Editorial changes versioned |
| M13-6 | Incident tooling, status page, global kill switches | P0 | Runbooks tested quarterly |
| M13-7 | Support tooling with consent-gated impersonation | P1 | Customer consent recorded per session |
| M13-8 | Model and prompt registry with evaluation dashboards | P1 | No model change ships without passing gates |

### M14. Insights and Analytics

| ID | Requirement | Pri | Acceptance Criteria |
| --- | --- | --- | --- |
| M14-1 | Buyer and team insights: stack coverage, adoption, Passport drift | P1 | Exportable |
| M14-2 | **Demand Radar** for creators: searches with no good result, pricing benchmarks, trending needs | P1 | Aggregated and anonymised |
| M14-3 | Organisation reports: spend, policy compliance, vulnerability exposure | P1 | Scheduled delivery |
| M14-4 | Public State of UI Components quality index | P2 | Methodology published |

---

## 11. AI System Design

### 11.1 Capability Map

| Capability | Model role | Grounding | Guardrails | Primary evaluation |
| --- | --- | --- | --- | --- |
| Semantic and screen search | Embeddings, reranker | Manifests, docs, examples | Entitlement and AI-consent filters | NDCG@10, click-through |
| Visual search | Vision embeddings | Rendered previews | Rights-cleared index only | Top-5 relevance |
| Fit Engine AI tier | Code reasoning model within bounded edit budget | Stack Profile, manifest contract, verification feedback | Allowed-path sandbox, no network, bounded attempts | First-pass success, edit minimality |
| Manifest assistant | Code and type analysis | Component source and tests | Creator confirms every field | Field accuracy |
| AI Studio generation | Code generation | Licensed or opted-in catalogue, user tokens | Verbatim guard, Passport gate, ledger logging | Compile rate, Passport score |
| Similarity and clone detection | Embeddings plus structural analysis | Catalogue and public code | Human review on borderline | Recall on planted clones |
| Review and support triage | Classification, summarisation | Reviews, issues | No automated punishment | Precision, resolution time |
| Demand Radar | Clustering of queries | Anonymised search logs | Aggregation thresholds | Creator adoption |

### 11.2 Fit Engine Pipeline

1. **Scan:** read repo metadata and configuration (ephemeral, read-only).
2. **Profile:** build and confirm the Stack Profile and token map.
3. **Plan:** a deterministic planner lists required transforms, new files, dependencies, and risks; an estimate is produced for Fit Preview.
4. **Transform (Tier 1):** apply rule-based changes using a library of tested codemods keyed to component and stack.
5. **Repair (Tier 2):** if verification fails, an AI repair loop proposes minimal edits inside allowed paths, with at most 3 iterations and a fixed edit budget.
6. **Verify:** type-check, lint, build, tests, accessibility checks, and visual comparison in an isolated environment.
7. **Package:** open a pull request with install report, or trigger fit-or-refund.
8. **Learn:** frequent AI repairs are reviewed by engineers and promoted into deterministic codemods, lowering cost and raising reliability over time.

**Fit Cache:** verified transform results are cached by component version and Stack Profile fingerprint, so common stacks install instantly and cheaply.

### 11.3 Grounded Generation and Attribution

- Retrieval context includes only components the user is licensed to use or whose creators have opted in to grounding.
- Every generation records the components retrieved and the structural lineage of output, producing Attribution Ledger events.
- A similarity guard compares output with catalogue code; matches above threshold are rewritten, blocked or routed to purchase.
- Generated components must pass the Passport before they can be labelled certified or sold.

### 11.4 AI Safety and Security

- **Untrusted-input rule:** manifests, READMEs, component code, repo files and issue text are data, never instructions to agents or models; instruction-like content is stripped or flagged.
- **Output validation:** schema checks, static analysis and sandboxed execution before anything leaves the system.
- **Secrets protection:** automatic redaction of credentials found in repos; secrets are never sent to a model.
- **Data handling:** zero-retention terms with model providers; repo content is never used for training; customer opt-in required for any diagnostic sharing.
- **Human gate:** AI never merges code, publishes a component, issues refunds beyond policy, or penalises a creator without a human or rule-based decision.

### 11.5 Evaluation Programme

| Area | Benchmark | Release gate |
| --- | --- | --- |
| Fit success | 200 repos across 12 stack combinations x 100 components | 82% first-pass at Phase 2; 90% at 18 months |
| Edit minimality | Median lines changed outside component files | Zero outside allowed paths |
| Search relevance | 2,000 judged queries | NDCG@10 of 0.70 or higher |
| Generation quality | Compile, lint, Passport score on 500 prompts | 90% compile; median score of 75 or higher |
| Verbatim guard | Red-team set of 300 extraction attempts | Under 1% leakage |
| Prompt injection | Adversarial manifests, READMEs, repos | No policy bypass |
| Accessibility rules | Expert-labelled corpus | False-positive rate under 5% |
| Fairness in ranking | Exposure analysis by creator size and region | No unexplained exposure gap above 15% |

Evaluations run on every model, prompt or ruleset change, with regression dashboards visible to engineering and trust teams.

### 11.6 Model Strategy and Cost Control

- Tiered models: small and open-weight models for embeddings, classification and similarity; a frontier model only for repair and generation.
- Deterministic first, AI last; the Fit Cache and codemod promotion keep the AI share of installs falling over time.
- Per-user and per-team budgets, hard caps, and graceful degradation to deterministic-only mode.
- Provider redundancy and a pinned, versioned prompt registry to avoid silent behaviour change.

---

## 12. Technical Architecture

### 12.1 Architectural Principles

1. **Untrusted code by default:** all component code, from any creator, executes only inside isolation boundaries.
2. **Ephemeral compute:** builds, verification and Fit runs use short-lived, network-restricted environments destroyed after use.
3. **Content-addressed, signed artifacts:** what was tested is exactly what is delivered.
4. **Event-driven core:** state changes publish events; Passport, search indexing, notifications and ledger consume them.
5. **Open formats:** manifest, registry protocol and token format are documented and interoperable.
6. **Cost-aware design:** deterministic paths first, caches everywhere safe, AI behind budgets.

### 12.2 Logical Architecture

| Layer | Component | Responsibilities | Candidate technology |
| --- | --- | --- | --- |
| Edge | CDN and WAF | Caching, bot defence, TLS, regional routing | Managed CDN with WAF |
| Web | Marketplace web app | SEO-rendered catalogue, listing pages, checkout, dashboards | Next.js (React, TypeScript) with server rendering |
| API | Gateway and BFF | Auth, rate limiting, GraphQL for web, REST for CLI and partners | GraphQL plus REST, OpenAPI |
| Catalogue | Catalogue and Search | Components, versions, facets, hybrid search, recommendations | PostgreSQL, OpenSearch with vectors |
| Registry | Artifact Registry | Content-addressed bundles, signing, provenance, registry protocol endpoint | Object storage, Sigstore-style signing, SLSA provenance |
| Compute | Build and Passport Workers | Build, test, a11y, perf, security, visual regression | Firecracker or gVisor sandboxes, orchestrated by durable workflows |
| Compute | Preview Renderer | Bundles components for playground in-browser or edge; theme injection | esbuild or Wasm bundlers, per-component sandboxed origins |
| Compute | Fit Engine | Repo connectors, Stack Profiler, codemod runner, AI repair orchestrator, verifier | TypeScript AST tooling, PostCSS, language servers |
| Commerce | Checkout and Entitlements | Orders, licences, tokens, refunds, subscriptions | Payment platform with merchant-of-record option |
| Commerce | Ledger | Double-entry financial ledger; payouts | Dedicated ledger service on PostgreSQL |
| Trust | Attribution Ledger | Append-only, hash-chained usage and royalty events | PostgreSQL with hash chain; periodic external anchoring |
| AI | AI Gateway | Model routing, redaction, caching, budgets, prompt registry, tracing | Provider-agnostic gateway |
| Identity | Auth and Org | OIDC, SAML SSO, SCIM, RBAC, API tokens | Standards-based identity service |
| Eventing | Event Bus | Domain events, retries, dead-letter queues | Kafka-compatible streaming or NATS |
| Data | Analytics Platform | Product analytics, creator analytics, experimentation | Columnar warehouse and ClickHouse |
| Ops | Observability and Admin | Tracing, metrics, logs, cost dashboards, moderation tools | OpenTelemetry stack |

### 12.3 Core Flows

**Publish flow**

1. Creator pushes a tag or runs `kiln publish`.
2. Submission is hashed, scanned, and queued; Manifest validated.
3. Passport workers build and test in isolated sandboxes; results stored with reproducible logs.
4. Similarity and licence checks run; risk score decides auto-approval or human review.
5. Artifact is signed, provenance attestation attached, version published; search and previews update.

**Purchase and install flow**

1. Buyer previews with Brand-Fit tokens, then purchases; entitlement and licence issued.
2. Buyer chooses Install by PR (app) or CLI; Stack Profile confirmed.
3. Fit Engine plans, transforms, verifies; PR opens with install report (or fit-or-refund triggers).
4. Merge event confirms the integration, starts the 30-day retention measurement and ledger lines.

**Agent flow**

1. Agent calls MCP search and manifest tools using the developer's scoped token.
2. Agent requests `propose_install`; Kiln stages a PR or local diff.
3. Human reviews and merges; agent receives status but cannot merge or change policy.

### 12.4 Sandbox and Isolation Design

| Layer | Control |
| --- | --- |
| Browser preview | Cross-origin iframe per component origin; sandbox attribute; strict CSP; no network by default; permissions policy denies camera, microphone, geolocation, clipboard |
| Build and test | microVM or user-space kernel isolation; read-only base image; CPU, memory, time and disk quotas; egress allow-list for package registries via a caching proxy; no secrets present |
| Fit Engine | Customer repo cloned into ephemeral volume; scoped token minted per run; volume and token destroyed on completion |
| AI calls | Redaction and allow-listed file context only; no tools beyond sandboxed editor and test runner |
| Registry | Immutable artifacts; signature verification enforced by CLI and PR bot |

### 12.5 Core Data Model (Summary)

| Entity | Key fields |
| --- | --- |
| User, Org, Membership | identity, roles, plan, region, policies |
| Creator, CreatorTier | verification, payout account, tier, AI preferences |
| Component, Version | identity, semver, status, tier, manifest hash, artifact digest |
| Manifest, Adapter | schema version, props, contract, token contract, framework adapter links |
| PassportReport, Finding | version, scores per category, findings, logs, environment hash |
| License, Entitlement | terms, scope, seats, projects, expiry, token references |
| Order, Refund, Payout, LedgerEntry | amounts, currency, tax, status, reconciliation |
| RepoConnection, StackProfile | provider, scopes, detected stack, user overrides, fingerprint |
| FitRun, FitStep, FitCacheEntry | plan, transforms applied, AI edits, verification results, cache key |
| Install | component version, repo, PR link, merged at, retained at 30 days, drift state |
| TokenProfile | source, mapping, version, owner (user or org) |
| AttributionEvent, RoyaltyAllocation | lineage, weights, period, creator, hash link |
| Review, Issue, Report, Takedown | verified-install link, status, SLA timers |
| AgentSession, ToolCall | agent platform, scopes, actions, approval state |
| AuditLog, PolicyDecision | actor, action, object, outcome, timestamp |

### 12.6 API Surface (Illustrative)

- `GET /v1/search?q=&facets=&stack=` and `GET /v1/components/{id}/versions/{v}`
- `GET /v1/components/{id}/manifest` and `GET /v1/components/{id}/passport`
- `POST /v1/preview` with token profile reference returns a themed preview URL
- `POST /v1/fit/plan`, `POST /v1/fit/run`, `GET /v1/fit/runs/{id}`
- `POST /v1/orders`, `GET /v1/entitlements`, `POST /v1/refunds`
- `POST /v1/publish` and `GET /v1/submissions/{id}`
- `GET /v1/ledger/lines?creator=` and `POST /v1/ledger/disputes`
- `POST /v1/orgs/{id}/policies` and `GET /v1/orgs/{id}/sbom`
- Webhooks: `version.passport.completed`, `fit.run.completed`, `install.merged`, `vulnerability.confirmed`, `payout.paid`

### 12.7 Build, Buy and Open-Source Decisions

| Area | Decision | Rationale |
| --- | --- | --- |
| Payments and tax | Buy | Compliance complexity; consider merchant-of-record for global tax |
| Identity and SSO | Buy or adopt open standard service | Security-critical, commodity |
| Search | Adopt open-source engine | Control over hybrid ranking |
| Accessibility rules engine | Adopt open-source rules plus Kiln proprietary scripts | Credibility plus differentiation |
| Sandboxing | Adopt open-source isolation tech | Security maturity |
| Fit Engine, Passport methodology, Ledger | Build | Core differentiation and moat |
| Registry and manifest formats | Build on open specs, publish own | Interoperability and ecosystem pull |

---

## 13. Security, IP Protection and Compliance

### 13.1 Threat Model and Controls

| Threat | Example | Controls |
| --- | --- | --- |
| Malicious component | Exfiltrates tokens, injects tracking, cryptominer | Static and dynamic analysis, network-egress tests, sandboxed execution, human review for risk flags, signed artifacts, kill switch |
| Sandbox escape | Component attacks preview host | Cross-origin isolation, microVM builds, regular penetration tests, bug bounty |
| Repo token compromise | Attacker abuses Fit Engine app | Per-run scoped tokens, PR-only write, anomaly detection, rapid revocation |
| Prompt injection | Manifest or README instructs the agent to exfiltrate | Content sanitisation, instruction hierarchy, tool allow-lists, no secrets in context, human approval |
| Dependency confusion and typosquatting | Fake packages in manifests | Dependency allow-list proxy, name-similarity checks, lockfile pinning |
| Piracy and redistribution | Paid source leaked | Per-licence fingerprints, leak monitoring, takedown automation, licence-bound registry tokens |
| Payment fraud and chargebacks | Stolen cards, refund abuse | Risk scoring, velocity limits, device signals, reserve policies |
| Account takeover | Creator account hijack publishes malware | MFA required for creators, publish re-authentication, new-device holds |
| Creator impersonation | Fake brand listings | Verified identity, brand claim process, similarity detection |
| Data leakage | Customer repo content exposed | Ephemeral storage, encryption, zero-retention contracts, access logging |

### 13.2 Security Programme

- Encryption in transit (TLS 1.2 or higher) and at rest (AES-256), key management with rotation, field-level encryption for payout data.
- Least-privilege access, just-in-time admin elevation, mandatory MFA, hardware keys for staff with production access.
- Secure SDLC: threat modelling per feature, SAST, DAST, dependency scanning, secret scanning, mandatory code review.
- Annual third-party penetration tests, public vulnerability disclosure policy, and bug bounty from Phase 2.
- Incident response plan with 72-hour regulatory notification readiness and customer notification playbooks.
- SOC 2 Type II by month 12; ISO 27001 by month 18.

### 13.3 IP, Licensing and AI Policy

- **Creators retain copyright.** Kiln receives a limited licence to host, test, preview and distribute.
- **Licences are explicit and machine-readable.** Terms for client work, SaaS, redistribution, remix and AI-assisted use are stated per listing.
- **AI use is opt-in for creators.** Catalogue grounding and remix are off unless enabled; opt-outs are honoured across all systems, and Kiln does not train foundation models on paid components.
- **AI-assisted outputs are disclosed** and carry lineage metadata.
- **Takedown processes** follow applicable notice-and-takedown law, with counter-notice and repeat-infringer policy.
- **Indemnity** options are available for enterprise licences, backed by similarity checks and provenance records.

### 13.4 Regulatory and Compliance Map

| Area | Requirement | Approach |
| --- | --- | --- |
| Privacy | GDPR, UK GDPR, CCPA/CPRA, India DPDP Act | Data minimisation, consent management, DSR automation, regional processing options |
| Payments | Card-network and strong-customer-authentication rules | Hosted payment fields; no card data on Kiln systems |
| Tax | VAT, GST, sales tax | Tax engine or merchant-of-record; creator tax forms |
| Online platform duties | Notice mechanisms, transparency reporting, statement of reasons | Built into Trust console |
| AI transparency | Disclosure of AI-generated content; provider obligations | AI-assisted labels, documentation, risk assessments |
| Accessibility | Marketplace conforms to WCAG 2.2 AA; supports customers' regulatory needs | Annual audit; public conformance statement |
| Export and sanctions | Screening of buyers, creators and payouts | Automated screening; blocked regions where required |
| Open-source obligations | Licence compatibility | Scanner enforces; SBOM output |

---

## 14. UX and Design Requirements

### 14.1 Experience Principles

- **Show the proof.** Passport, fit preview and live demos appear above the fold on every listing.
- **Your tokens everywhere.** After the first token upload, every page is shown in the user's brand unless they turn it off.
- **Install is a conversation, not a download.** The flow explains what will change in the repo before anything changes.
- **Calm density.** Developer-grade information density with strong hierarchy and no marketing noise.
- **Honest empty states.** If nothing fits, say why and offer next steps (adapt, generate, request).

### 14.2 Signature Screens

| Screen | Key elements |
| --- | --- |
| Search results | Live thumbnail previews themed to the user, Passport badges, fit confidence, price, filters |
| Listing | Interactive preview, state matrix, Passport report summary, Fit Preview, code view, changelog, licence, reviews |
| Playground | Controls, viewport and theme matrix, accessibility overlay, performance panel |
| Install wizard | Stack Profile confirmation, token mapping review, predicted diff, consent, progress, PR link |
| PR install report | Plain-language changes, verification results, rollback |
| Creator Studio | Publish pipeline status, Passport fixes, analytics, Demand Radar, payouts |
| Team Console | Policy builder, approval queue, SBOM, drift and vulnerability dashboards |
| Ledger view | Usage lineage, allocations, disputes |

### 14.3 Interaction and Visual Requirements

- Design system built on tokens; the marketplace dogfoods Kiln components and Passport.
- Keyboard-first navigation, command palette, and consistent shortcuts.
- Light, dark and high-contrast themes; reduced-motion respected.
- Responsive from 320 px; mobile optimised for discovery, review, approvals and payout checks, with install actions available as handoff to desktop.
- Internationalisation: UI localisation from Phase 2; right-to-left support; local currency and tax display.
- Performance budgets for the site itself: Largest Contentful Paint under 2.5 s (p75), Interaction to Next Paint under 200 ms.

### 14.4 Onboarding Targets

| Persona | Target |
| --- | --- |
| Developer | First verified install within 10 minutes of landing; first search result themed within 90 seconds |
| Creator | First publish dry run within 30 minutes of signup; first Passport report within 15 minutes of submission |
| Team lead | Policy and registry configured within 1 day |

---

## 15. Non-Functional Requirements

| Category | Requirement |
| --- | --- |
| Availability | 99.9% for marketplace and registry; 99.5% for Fit Engine and Passport workers; status page and public postmortems |
| Performance | Search p95 under 300 ms; listing page LCP under 2.5 s; preview cold start under 2 s; Fit run p50 under 90 s and p95 under 5 min; Passport median under 15 min |
| Scalability | 100,000 components, 1 million monthly active users, 50,000 Fit runs per day, 5,000 Passport runs per day at the 18-month horizon |
| Reliability | Idempotent workflows, retry with backoff, dead-letter handling, multi-AZ deployment; RPO under 5 minutes and RTO under 1 hour for core data |
| Security | See Section 13; zero critical vulnerabilities open beyond 7 days; high beyond 30 days |
| Privacy | Data minimisation; deletion within 30 days of request; separate stores for customer repo artifacts with strict TTL |
| Compatibility | Latest two versions of evergreen browsers; Node LTS versions; major package managers and bundlers; GitHub and GitLab at launch |
| Accessibility | WCAG 2.2 AA across the entire product |
| Observability | Distributed tracing on every request and workflow; per-install cost attribution; AI quality dashboards |
| Maintainability | 80% automated test coverage on core logic; contract tests for CLI, MCP and registry protocol; infrastructure as code |
| Cost | Gross margin target of 75% or higher at 18 months; compute and AI costs below 15% of net revenue |
| Data quality | Catalogue freshness checks; automatic delisting of components failing re-certification after grace period |

---

## 16. Go-to-Market and Cold Start

### 16.1 Strategy: Quality Anchor, Then Flywheel

The flywheel: **more certified supply, more successful installs, more buyer trust, more creator income, more certified supply.** The cold start is solved by seeding quality first and demand through zero-friction free tools.

### 16.2 Supply Plan

| Lever | Description | Target |
| --- | --- | --- |
| **Kiln Core Set** | In-house, Gold-tier set of foundational components (forms, tables, navigation, overlays, charts, feedback) for the launch stack, setting the quality bar | 120 components at launch |
| **Founding Creators** | Invited cohort with 90% revenue share, guaranteed minimum payout for 6 months, co-marketing | 60 creators before public beta |
| **Import programme** | Tooling to convert existing open-source and marketplace components, with free Passport audit and manifest drafting | 400 components in first 6 months |
| **Demand Radar bounties** | Paid bounties for unmet searches | 10 per month |
| **Passport for OSS** | Free public scoring of popular open-source components, driving credibility and creator awareness | 300 components scored |

### 16.3 Demand Plan

| Channel | Tactic |
| --- | --- |
| Free tools | **Fit Check:** paste a repository URL, see Stack Profile and which components would fit; **Accessibility Debt Scanner** for existing UI |
| Programmatic SEO | Server-rendered listing pages with live previews and Passport data |
| Viral loop | Shareable themed galleries (see the marketplace in your brand), Passport badges for creators' own sites |
| Agent distribution | MCP directories, coding-agent partnerships, documentation snippets agents retrieve |
| Content | Accessibility teardowns, State of UI Components report, build-in-public engineering notes |
| Communities and education | Bootcamps, university programmes, developer conferences, creator jams |
| Enterprise | Design-system lead outreach, three-month pilots with success criteria, security whitepaper, ROI calculator based on rework hours saved |

### 16.4 Launch Sequence

1. **Closed alpha:** 40 creators and 300 developers; validate Fit Engine and Passport on one stack.
2. **Open beta:** public catalogue, free components, paid listings with fit-or-refund; waitlist converts.
3. **General availability:** payouts live, Pro subscription, public Passport reports, CLI 1.0.
4. **Agent launch:** MCP Server with 3 or more agent-platform partners.
5. **Team launch:** private registry and governance for design-system teams.

### 16.5 Positioning Against Free Alternatives

Kiln complements free copy-paste libraries rather than fighting them: it can install from compatible registries, score open-source components, and add what free libraries lack (certification, creator income, governance, fit verification). The message is **free is great; verified, adapted and maintained is better**.

---

## 17. Roadmap and Release Plan

| Phase | Timing | Scope | Exit Criteria |
| --- | --- | --- | --- |
| **Phase 0: Prove the hard parts** | Months 0 to 2 | Fit Engine spike on React with Tailwind across 50 repos; Passport pipeline prototype (accessibility, size, visual); sandbox security review; manifest v0; 30 developer and 20 creator interviews; unit-economics model | First-pass fit rate of 60% or higher; sandbox review clear; 20 creators commit to publish |
| **Phase 1: MVP** | Months 3 to 7 | M1 core, M2, M3 core, M4 (P0 set) for React with Tailwind, M6 (P0 set), M7 (P0 set), M8 (P0 set), M11 (P0 set), M13 (P0 set), CLI, GitHub app, 120 Core Set components plus 200 creator components | 5,000 weekly active developers; fit first-pass 70% or higher; zero security incidents; 150 active creators |
| **Phase 2: Agents, AI and Teams** | Months 8 to 12 | MCP Server, IDE extensions, Figma plugin, AI Studio, Attribution Ledger v1, Update PRs, drift detection, Team Console with private registry, Vue and Svelte adapters, Kiln Pro subscription and pool, GitLab, localisation | 30% of installs via CLI or MCP; 5 enterprise pilots; SOC 2 audit window open; 700 active creators |
| **Phase 3: Platform and Scale** | Months 13 to 18 | Kits and screen compositions, Angular support, Public API and webhooks, Passport API, Demand Radar, data residency, SBOM and policy at scale, partner programme, iOS and Android component support exploration | USD 6M annualised GMV; 40,000 weekly active developers; net revenue retention of 115% for teams |
| **Phase 4: Ecosystem** | Months 19 and beyond | Full-page blocks and templates with Fit Engine, design-to-code partnerships, creator marketplace for services (custom components), regional expansion, certification programme for developers | Ecosystem partners generate over 20% of installs |

### 17.1 Critical Path and Dependencies

1. Fit Engine verification harness (blocks fit-or-refund and credibility).
2. Passport accessibility methodology validated by external accessibility experts.
3. Sandbox isolation security review and penetration test (blocks public creator code).
4. Payments, tax and payout compliance in launch regions.
5. Manifest v1 specification published and stable (blocks creator onboarding at scale).

### 17.2 Indicative Team (Phase 1)

| Function | Headcount |
| --- | --- |
| Product and design | 4 (PM, 2 designers, 1 content designer) |
| Frontend and full-stack | 5 |
| Platform, infra and security | 4 |
| Fit Engine and compilers | 3 |
| AI and data | 3 |
| Accessibility and quality engineering | 2 |
| Trust and marketplace operations | 2 |
| Developer relations and creator success | 2 |

---

## 18. Analytics, Experimentation and Operations

- **Event taxonomy:** search, preview, token upload, purchase, Fit plan, Fit run result, PR opened, PR merged, 30-day retained, refund, defect report, publish, Passport result, payout, policy decision, agent tool call.
- **Core dashboards:** Merged Integrations (North Star), funnel from search to retained install, fit success by stack, Passport distribution, creator health, AI cost per install, marketplace liquidity (search with at least one good result), trust and safety metrics.
- **Marketplace liquidity target:** at least 90% of top-1,000 searches return a Verified component that fits the searcher's stack.
- **Experimentation:** ranking weights, onboarding, pricing, preview defaults, install wizard copy. Guardrails prevent tests that reduce fit success or creator exposure fairness.
- **Data governance:** no repository source code in analytics; token profiles stored as user data with deletion rights; creator data export at any time.
- **Operational SLAs:** support first response under 4 hours (paid) and 24 hours (free); moderation review under 24 hours; payout accuracy 100%.

---

## 19. Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
| --- | --- | --- | --- |
| AI generation commoditises components, reducing willingness to pay | High | High | Sell trust, fit, maintenance and governance, not code; grounding makes AI output better when paired with the catalogue; Passport applies to generated output |
| Fit Engine reliability below promise, creating refund losses | Medium | High | Narrow stack at launch; benchmark gates; fit-or-refund reserve; promote AI repairs to deterministic codemods |
| Malicious or compromised component reaches customers | Low | Very High | Layered analysis, sandboxing, signing, kill switch, bug bounty, MFA for creators |
| Free open-source alternatives capture mindshare | High | Medium | Interoperate, score, and import; add paid-only value (certification, upkeep, governance) |
| Cold start: thin catalogue or buyers | Medium | High | Core Set, Founding Creators, free tools, agent distribution |
| Creator distrust of AI features | Medium | High | Opt-in defaults, ledger transparency, creator advisory council, audit rights |
| Piracy erodes creator income | Medium | Medium | Fingerprinting, licence-bound tokens, takedown automation; source delivered as PRs with licence files |
| Framework fragmentation inflates cost | High | Medium | Canonical source plus adapters; staged framework rollout; adapter parity scores |
| Legal uncertainty on AI training, remix and licensing | Medium | High | Clear licences, counsel review, conservative defaults, indemnity only with provenance evidence |
| High compute cost for Passport and Fit runs | Medium | Medium | Tiered testing, sampling, Fit Cache, budgets, spot capacity |
| Passport methodology disputed by creators | Medium | Medium | Open methodology, reproducible logs, dispute process, external accessibility advisory board |
| Supply concentration in a few top creators | Medium | Medium | Concentration cap in pool, novelty boost, curated discovery |
| Dependence on one model provider | Medium | Medium | Provider-agnostic gateway, evaluation-gated switching |
| Platform dependency on GitHub and GitLab policies | Low | Medium | CLI path without repo access; additional providers in Phase 3 |

---

## 20. Open Questions and Decision Log

| # | Decision | Options | Current recommendation | Owner | Needed by |
| --- | --- | --- | --- | --- | --- |
| D1 | Launch stack | React with Tailwind only vs. plus Vue | React with Tailwind only, Vue in Phase 2 | Product and Eng | Month 1 |
| D2 | Merchant of record | Direct with tax engine vs. merchant of record | Merchant of record for global tax simplicity at launch | Finance | Month 2 |
| D3 | Registry protocol | Adopt existing open registry spec vs. new | Extend existing spec with Kiln manifest and entitlements | Eng | Month 2 |
| D4 | Subscription pool share | 60%, 70% or 80% to creators | 70% with concentration cap, revisit at month 12 | Finance and Marketplace | Month 5 |
| D5 | AI Studio launch timing | Phase 1 vs. Phase 2 | Phase 2, after Passport and ledger are proven | Product | Month 4 |
| D6 | Enterprise indemnity | Offer at launch vs. later | Phase 2 pilots, only for Gold and Core Set | Legal | Month 6 |
| D7 | Free-component policy | Open to all vs. quality floor | Quality floor applies to free and paid alike | Marketplace | Month 3 |
| D8 | Component licence set | Create Kiln licences vs. adapt existing | Small, plain-language set plus SPDX mapping, counsel reviewed | Legal | Month 3 |
| D9 | Initial regions | Global vs. staged | Global sales; payouts in staged countries | Finance and Legal | Month 4 |
| D10 | Market sizing | Bottom-up study | Complete in Phase 0 and update targets | Product and Finance | Month 2 |

---

## Appendix A: Quality Passport Scoring and Discovery Ranking

### A.1 Passport Score

**Score = sum of (category weight x category score from 0 to 100).** Category scores come from automated tests, with expert audits adjusting the Gold tier.

| Category | Weight | Key signals |
| --- | --- | --- |
| Accessibility | 25% | Rule violations by severity, keyboard and focus scripts, contrast in all themes, reflow, reduced motion, forced colours, name-role-value correctness |
| Performance | 15% | Size against declared budget, tree-shaking, render time, re-renders, layout stability, leak tests |
| Compatibility | 15% | Browser matrix, framework version ranges, SSR and hydration, strict mode |
| Code quality and types | 10% | Type coverage, lint cleanliness, test coverage, API stability |
| Security and supply chain | 10% | Dependency health, licence compatibility, behaviour scan, provenance |
| Theming, responsiveness, i18n | 10% | Token contract adherence, dark and high-contrast support, RTL, text expansion |
| Documentation and manifest | 10% | Completeness, examples that render, composition hints |
| Maintenance health | 5% | Release cadence, response times, re-certification history |

**Hard gates (any failure blocks listing):** critical accessibility violation; high-severity vulnerability; undeclared network call, dynamic remote import or eval; licence conflict; build failure on declared matrix; invalid manifest; declared bundle budget exceeded by more than 5%.

**Tiers:** Listed (gates pass, score of 60 or higher); Verified (75 or higher); Gold (90 or higher, manual accessibility audit, and 6 months of maintenance history).

### A.2 Discovery Ranking (initial weights)

| Signal | Weight |
| --- | --- |
| Query relevance | 30% |
| Predicted fit success on the searcher's stack | 20% |
| Passport score | 20% |
| Freshness and maintenance | 10% |
| Verified-install reviews and defect rate | 10% |
| Novelty boost for new creators (decays over 90 days) | 5% |
| Price and licence fit | 5% |

**No pay-to-rank.** Promotion slots are clearly labelled, limited, and never alter organic ranking.

## Appendix B: Component Manifest (Illustrative Example)

```yaml
manifest: kiln/1.0
id: acme/data-table
version: 2.3.0
category: data-display
summary: Sortable, filterable, virtualised data table
frameworks:
  - name: react
    range: '>=18 <20'
    styling: [tailwind-v3, tailwind-v4, css-modules]
    ssr: true
    server-components: client-only
licence:
  spdx: LicenseRef-Kiln-Team
  client-work: allowed
  redistribution: forbidden
  ai-grounding: opt-in
  remix: allowed-with-attribution
budget:
  max-gzip-kb: 14
props:
  columns: 'ColumnDef[]  # required'
  rows: 'Row[]  # required'
  density: "'compact' | 'comfortable'  # default comfortable"
events: [onSortChange, onSelectionChange]
slots: [toolbar, emptyState, rowActions]
states: [loading, empty, error, selected, expanded]
tokens:
  required: [color.surface, color.border, color.text.primary, space.2, radius.md]
  optional: [color.accent, motion.duration.fast]
a11y:
  role: grid
  keyboard:
    - 'Arrow keys move cell focus'
    - 'Enter or Space activates row actions'
    - 'Home and End jump to row start and end'
  announcements: [sort-change, selection-count]
  reduced-motion: respected
locales: [en, de, ar-rtl, ja]
composition:
  works-with: [pagination, search-input, filter-bar]
  avoid: [nested-tables]
agent-hints:
  use-when: 'Tabular data with sorting, filtering or selection'
  avoid-when: 'Fewer than 5 static rows; use a simple list'
support:
  sla-hours: 48
  issues: https://example.com/issues
```

## Appendix C: Subscription Pool and Attribution Ledger

### C.1 Subscription Pool (v1)

- **Pool for month t** = 70% of net subscription revenue in month t (after taxes, payment fees, refunds).
- **Weight of a component version v** = Merged Integrations in the month (retained at 30 days) x Tier multiplier (Listed 0.6, Verified 1.0, Gold 1.25) x Fit success rate x (1 + 0.1 x Freshness index).
- **Creator payout** = Pool x (sum of weights of the creator's components) / (sum of weights of all components).
- **Concentration cap:** no creator receives more than 15% of the pool; excess is redistributed pro rata.
- **Floor:** every Verified component with at least 10 merged integrations earns a minimum micro-payment.
- Components already purchased under a direct licence are excluded from pool weight for that customer, preventing double payment.

### C.2 Attribution Ledger for AI Composition (v1)

- Each AI generation logs retrieved components and structural lineage, producing contribution weights **w\_i** that sum to 1.
- **If the user lacks a licence** for a component that materially contributes (similarity above threshold), the output is withheld pending purchase.
- **Retrieval-influenced contributions** below the similarity threshold earn a royalty from AI credit revenue: 25% of credit revenue for the generation is allocated across opted-in components in proportion to **w\_i**.
- Ledger entries are hash-chained, exportable, and disputable; periodic digests are anchored externally for tamper evidence.

## Appendix D: Glossary

| Term | Meaning |
| --- | --- |
| Quality Passport | Automated, versioned certification report and score for a component version |
| Fit Engine | Service that adapts a component to a buyer's repo and verifies the result before opening a pull request |
| Stack Profile | Detected description of a repo's framework, styling, tokens and tooling |
| Brand-Fit Preview | Rendering of any listing using the user's design tokens |
| Component Manifest | Machine-readable contract describing a component's API, behaviour, tokens, accessibility and licence |
| Kiln MCP Server | Interface allowing AI agents to search, inspect and stage installs |
| Attribution Ledger | Auditable record of component usage lineage and royalties |
| Kit | A set of components designed to work together |
| Fit-or-refund | Guarantee that failed adaptation triggers automatic credit |
| Drift | Divergence between installed code and registry version |
| Merged Integration | Install whose pull request is merged and still present after 30 days |

## Appendix E: Launch Readiness Checklist

| Area | Gate |
| --- | --- |
| Security | Penetration test passed; sandbox escape suite green; kill switch drilled |
| Quality | Fit first-pass success of 70% or higher on benchmark; Passport false-positive rate under 5% |
| Trust and Legal | Licences, takedown process and creator terms approved by counsel; AI consent flags enforced end to end |
| Commerce | Payments, tax, refunds and payouts reconciled in test and live-money pilot |
| Reliability | Load test at 3x forecast; disaster recovery test; on-call rotation staffed |
| Accessibility | Marketplace audit with no critical issues; public conformance statement drafted |
| Supply | At least 300 components listed, 60% Verified or higher, all launch categories covered |
| Support | Documentation hub live; support runbooks; creator onboarding guide |
| Analytics | North Star and guardrail dashboards live; experimentation framework ready |
