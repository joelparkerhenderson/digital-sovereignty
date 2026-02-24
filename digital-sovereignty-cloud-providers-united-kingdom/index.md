# Digital sovereignty - cloud providers - United Kingdom

Summary: I'm researching digital sovereignty options for cloud providers for United Kingdom software engineering. My research is starting with a a lightweight experiment of how to create a simple virtual private server (VPS) to deploy a simple web application. The purpose is to increase direct technical knowledge, such that it helps shape better-informed positions on data sovereignty.

## Findings thus far

This is a work in progress. This table of cloud providers is ranked by my personal preference, based on my direct experience thus far.

<<<<<<< HEAD
| Company | Owners | UK/EU | UK VPS? | Alignment? | Account? | Pros | Cons |
|-----------------|-----------------|--------|---------|------------|----------|-----------------------------------------------------|---------------------------------------------------------|
| **Krystal.io** | 🇬🇧 UK | 🇬🇧 UK | ✅ | ✅ | ✅ | UK home. London VPS. B-Corp. Superb sustainability. CEO help. | UK and Amsterdam, no other geographies. BYO emailer. |
| **Civo** | 🇬🇧 UK? | 🇬🇧 UK? | ✅ | ✅ | ✅ | UK home. London VPS. London HQ. | Setup failed due to UX glitches. |
| **Coolify** | 🇬🇧 UK | 🇬🇧 UK | ✅ | ✅ | ✅ | UK meta-provider for distributed deploys. | Requires hosting delegation, such as to Krystal.io. |
| **UpCloud** | 🇫🇮 Finland | 🇪🇺 EU | ✅ | ✅ | ✅ | Looks great for bare-knuckle engineering. | None yet. |
| **server.net** | 🇮🇹 Italy | 🇪🇺 EU | ✅ | 🔶 | ❌ | London VPS. Superb chat support. | Owners are not UK citizens. HQ leads to Italy not UK. |
| **OVH** | 🇫🇷 France | 🇪🇺 EU | 🔶 | ❌ | ✅ | Largest best offerings similar to AWS, GC, MS. | Currently completely sold out of UK VPS offerings. |
| **Scaleway** | 🇫🇷 France | 🇪🇺 EU | 🚫 | ✅ | ❌ | Extensive Rust work, great blogs. | Signup/FTUX broke. |
| **AWS EU** | 🇩🇪 Germany | 🇪🇺 EU | 🚫 | 🔶 | ✅ | AWS Sovereign EU - different than AWS US. | AWS confusion with US. |
| **Hetzner** | 🇩🇪 Germany | 🇪🇺 EU | 🚫 | ❌ | ❌ | Best customer ratings. Excellent prices. | Limited cloud offerings. |
| **Elastx** | 🇸🇪 Sweden | 🇪🇺 EU | 🚫 | ✅ | ❌ | OpenStack purity, which is amazing. | Data centres only in Sweden. |
| **Exoscale** | 🇨🇭 Switzerland | 🇪🇺 EU | 🚫 | ✅ | ✅ | Swiss data protections. | Intermixes Swiss law vs EU law. |
| **Cyso Cloud** | 🇳🇴 Norway | 🇪🇺 EU | ❓ | ✅ | ❓ | OpenStack semi-purity, which is pretty good. | Unknown. |
| **Gridscale** | 🇩🇪 Germany | 🇪🇺 EU | ❓ | ❓ | ❓ | Unknown. | Unknown. |
| **IONOS** | 🇩🇪 Germany | 🇪🇺 EU | ❓ | ❓ | ❓ | German market leader. SECA API. EuroStack member. | Documentation primarily in German. |
| **Orange** | 🇫🇷 France | 🇪🇺 EU | ❓ | ❓ | ❓ | EU telco leader. Extensive digital teams. | No obvious way to sign up for consumer VPS. |
| **AWS EU** | TBD | 🇪🇺 EU | ❓ | ❓ | ❓ | AWS EU digital sovereign cloud work in progress. | Not yet released. |
| **StackIT** | 🇩🇪 Germany | 🇪🇺 EU | ❓ | ❓ | ❓ | Backed by Schwarz group - Germanys largest retailer (Lidl & Kaufland) | Reported problems with price changes |
| \*\*Clevercloud\*\* | TBD | ❓ | ❓ | ❓ | ❓ | TODO

## Compare Cloud Providers

### Prompt work in progress

Compare cloud providers:

- Krystal, Coolify, Server.net, Scaleway, OVHcloud, AWS Sovereign EU, UpCloud, Exoscale, Gridscale, Elastx, Cyso, IONOS.
- Explain key features, strengths, considerations, digital sovereignty.
- Output as architecture decision record.

### Key Highlights

**Providers Analyzed:**

- **Krystal** (UK) - Independent UK hosting, B Corp certified, excellent support
- **Coolify** - Open-source self-hosting platform (not a provider, but deployment tool)
- **Scaleway** (France) - European AI leader, NVIDIA H100 GPUs, sovereign innovation
- **OVHcloud** (France) - Largest European provider, SecNumCloud certified, 44 data centers
- **UpCloud** (Finland) - Performance leader, zero egress fees, 100% SLA
- **Exoscale** (Switzerland) - Swiss sovereignty, maximum privacy, GDPR exemplary
- **IONOS** (Germany) - German market leader, SECA API co-creator, EuroStack member
- **Orange** (France) - TODO
- **AWS EU** (Pending) - New AWS EU digital sovereign cloud, coming soon.
- **StackIT** (TODO) - TODO
- **Clevercloud** (TODO) - TODO

**Critical Findings:**

- All providers offer **zero US CLOUD Act exposure** (European jurisdiction)
- **75% of enterprises will need digital sovereignty strategies by 2030** (Gartner)
- **30-60% cost savings** vs US hyperscalers for European workloads
- **OVHcloud** is the only provider with SecNumCloud v3.2 certification
- **UpCloud** eliminates egress fees entirely (since 2024)
- **Scaleway** leads European AI infrastructure with 1,000+ H100 GPUs

**Strategic Recommendations:**

1. **Enterprise/Regulated**: OVHcloud (SecNumCloud + scale)
2. **SME/Startups**: UpCloud (performance + zero egress + support)
3. **AI/ML**: Scaleway (European AI leadership)
4. **Maximum Control**: Coolify on European infrastructure
5. **Swiss Requirements**: Exoscale (Swiss law)

The ADR includes detailed comparisons, implementation roadmap, risk assessment, and success metrics.

[View your Architecture Decision Record](computer:///mnt/user-data/outputs/ADR-European-Cloud-Provider-Comparison.md)

# Architecture Decision Record: European Cloud Provider Selection

**Status:** Proposed  
**Date:** 2025-11-20  
**Decision Makers:** Infrastructure Team  
**Context:** Cloud provider selection with emphasis on digital sovereignty, GDPR compliance, and European data residency

---

## Executive Summary

This ADR evaluates European cloud providers and deployment platforms with a focus on digital sovereignty, compliance, performance, and cost-effectiveness. The analysis covers infrastructure providers (Krystal, Scaleway, OVHcloud, UpCloud, Exoscale, IONOS, Server.net, Gridscale, Elastx, Cyso) and includes Coolify as a self-hosting platform option.

**Key Finding:** Digital sovereignty is no longer optional—75% of enterprises outside the U.S. are expected to have a digital sovereignty strategy by 2030, with European providers offering viable alternatives to U.S. hyperscalers.

---

## Context and Problem Statement

Organizations face increasing pressure to maintain control over their digital infrastructure due to:

- **Regulatory Requirements**: GDPR, EU AI Act, SecNumCloud, and emerging data sovereignty laws
- **Geopolitical Risks**: Extraterritorial reach of U.S. CLOUD Act and FISA
- **Vendor Lock-in**: High egress fees and proprietary ecosystems
- **Cost Predictability**: Unpredictable cloud bills from traditional providers
- **Critical Infrastructure**: Need for sovereign solutions in defense, healthcare, finance, and public sector

**Decision Required:** Select cloud infrastructure that balances performance, compliance, sovereignty, and cost.

---

## Provider Categories

### Category A: Infrastructure-as-a-Service (IaaS) Providers

Full-stack cloud providers offering compute, storage, networking, and managed services.

### Category B: Self-Hosting Platform

Coolify - deployment automation for self-managed infrastructure.

---

## Detailed Provider Analysis

### 1. Krystal (UK)

**Type:** UK-based web hosting and cloud provider  
**Founded:** 2002  
**Headquarters:** London, UK

#### Key Features

- **Katapult Cloud Platform**: Custom-built public cloud infrastructure
- **UK Data Centers**: Netwise (primary), previously operated The Bunker (MOD facility)
- **LiteSpeed Web Server**: With LSCache for 6x faster WordPress performance
- **Green Hosting**: 100% renewable energy, B Corporation certified
- **ISO 27001 Certified**: Security management
- **All-NVMe Storage**: High-performance storage across all plans

#### Strengths

- 🇬🇧 **UK Sovereignty**: Largest independent UK hosting provider
- 🌱 **Sustainability Leader**: First B Corp certified web host (2023), 1% for the Planet member
- 💚 **Outstanding Support**: 24/7 UK-based support, highly rated on Trustpilot
- 🔒 **Security Focus**: ISO 27001, DDoS protection (2.0 Tbps)
- 💰 **Transparent Pricing**: Clear pricing with 60-day money-back guarantee

#### Considerations

- **Geographic Limitation**: Primary focus on UK market with limited global presence
- **Smaller Scale**: Less extensive than continental European providers
- **Service Scope**: Stronger in web hosting than enterprise IaaS
- **Best For**: UK-based SMEs, agencies, and WordPress users requiring UK data residency

#### Digital Sovereignty Profile

**Jurisdiction:** UK law (post-Brexit, not subject to EU regulations but maintains GDPR alignment)  
**Data Location:** UK-based data centers  
**Ownership:** Independent UK company, no US ownership  
**SecNumCloud/Equivalent:** ISO 27001, working toward UK-specific certifications  
**CLOUD Act Exposure:** ❌ None (UK jurisdiction)

**Sovereignty Score:** ⭐⭐⭐⭐ (4/5) - Strong UK sovereignty, limited by smaller scale

---

### 2. Coolify (Self-Hosting Platform)

**Type:** Open-source Platform-as-a-Service (PaaS)  
**Founded:** 2021  
**License:** Open Source

#### Key Features

- **Self-Hosted PaaS**: Heroku/Netlify/Vercel alternative you control
- **Docker-Based**: Deploy containers, Docker Compose, or git repositories
- **Git Integration**: GitHub, GitLab, Bitbucket, Gitea support
- **One-Click Apps**: 280+ pre-configured services
- **Auto SSL**: Let's Encrypt integration
- **API-First**: Full REST API for automation
- **Zero Vendor Lock-in**: All configurations saved on your servers

#### Strengths

- 🆓 **Zero Cost**: Free open-source software (only pay for servers)
- 🔐 **Maximum Control**: Complete data and infrastructure ownership
- 🚀 **Easy Deployment**: Simplified server management with GUI
- 🔄 **Flexible Infrastructure**: Works on any server (VPS, bare metal, cloud)
- 🛠️ **Developer-Friendly**: Terraform, CLI, SDK support

#### Considerations

- **Not a Cloud Provider**: Requires underlying infrastructure (use with other providers)
- **Self-Management**: You're responsible for server maintenance and updates
- **Technical Expertise**: Requires system administration knowledge
- **No SLA**: Support depends on community or self-management
- **Best For**: Developers wanting maximum control, startups minimizing costs, organizations with in-house DevOps

#### Digital Sovereignty Profile

**Jurisdiction:** Your choice (depends on underlying infrastructure)  
**Data Location:** Your choice (wherever you deploy)  
**Ownership:** Full ownership of all infrastructure and data  
**Compliance:** Achievable based on chosen infrastructure  
**CLOUD Act Exposure:** ❌ None (if deployed on non-US infrastructure)

**Sovereignty Score:** ⭐⭐⭐⭐⭐ (5/5) - Ultimate sovereignty when deployed correctly

**Recommended Use Case:** Deploy Coolify on European providers (Scaleway, OVHcloud, UpCloud, Exoscale) for maximum sovereignty and control.

---

### 3. Scaleway (France)

**Type:** European cloud and AI infrastructure provider  
**Founded:** 1999  
**Parent Company:** Iliad Group  
**Headquarters:** Paris, France

#### Key Features

- **Europe's AI Cloud Leader**: NVIDIA H100 GPU clusters, Nabuchodonosor supercomputer
- **Multi-Region**: Paris, Amsterdam, Warsaw (9 Availability Zones across 3 regions)
- **Global VPS**: 65 cities across 52 countries
- **Generative APIs**: Drop-in OpenAI alternative, 100% European
- **Dedibox**: Bare metal and elastic metal servers
- **Managed Services**: Kubernetes, databases, object storage (S3-compatible)
- **RISC-V Servers**: World-first sovereign processors
- **AI Focus**: Training, inference, and deployment for European AI startups (Mistral, Kyutai, "H")

#### Strengths

- 🇪🇺 **European AI Leadership**: Largest AI GPU capacity in Europe
- 🏆 **Digital Sovereignty**: Strong focus on European technological independence
- ♻️ **Sustainability**: 100% renewable energy, transparent PUE monitoring
- 💡 **Innovation**: RISC-V processors, sovereign AI models
- 🌍 **Global Reach**: Expanding VPS to 65 cities worldwide
- 💼 **Enterprise Ready**: 25,000+ businesses, multi-AZ redundancy

#### Considerations

- **AI-Centric**: Heavy investment in AI may overshadow traditional cloud services
- **Pricing Complexity**: More complex pricing than some competitors
- **English Documentation**: Primarily French-focused, though English available
- **Best For**: AI/ML workloads, European startups, sovereign AI requirements

#### Digital Sovereignty Profile

**Jurisdiction:** French law, EU GDPR compliant  
**Data Location:** Paris, Amsterdam, Warsaw (European Union)  
**Ownership:** French company (Iliad Group subsidiary)  
**Certifications:** ISO 27001, working toward SecNumCloud  
**CLOUD Act Exposure:** ❌ None (European jurisdiction)

**Sovereignty Score:** ⭐⭐⭐⭐⭐ (5/5) - Exemplary European sovereignty, AI leadership

---

### 4. OVHcloud (France)

**Type:** Global cloud provider, European leader  
**Founded:** 1999 (IPO 2021)  
**Headquarters:** Roubaix, France  
**Stock:** Euronext Paris

#### Key Features

- **Massive Scale**: 450,000+ servers, 44 data centers across 4 continents
- **Vertically Integrated**: Designs and manufactures own servers
- **SecNumCloud Certified**: French sovereign cloud qualification (v3.2)
- **3-AZ Regions**: Paris (France), Milan (Italy, 2025)
- **Bare Metal Pod**: Ultra-secure, physically isolated infrastructure
- **Global Reach**: 1.6M customers in 140+ countries
- **On-Prem Cloud Platform (OPCP)**: Disconnected sovereign cloud for partners
- **GDPR Native**: Built with European data protection at core

#### Strengths

- 🌍 **Largest European Provider**: Leading market position (€1B+ revenue)
- 🔒 **Maximum Security**: SecNumCloud, Bare Metal Pod, ISO 27001
- 🏭 **Vertical Integration**: Controls entire value chain (design to data center)
- 🇪🇺 **True Sovereignty**: Structural separation between US and global operations
- ♻️ **Sustainable**: Best PUE ratios in industry
- 📈 **Accelerating Momentum**: Growing demand for sovereign solutions

#### Considerations

- **VMware Costs**: Affected by Broadcom license increases
- **Complex Portfolio**: Wide range of services can be overwhelming
- **Best For**: Large enterprises, regulated industries (finance, healthcare, government), organizations requiring SecNumCloud

#### Digital Sovereignty Profile

**Jurisdiction:** French law, EU GDPR compliant  
**Data Location:** Multiple EU data centers + global (customer choice)  
**Ownership:** Independent French company (publicly traded)  
**Certifications:** SecNumCloud v3.2, ISO 27001/27701, C5 (Germany), ACN (Italy), HDS  
**CLOUD Act Exposure:** ❌ None (structural separation from US entity)  
**Special Note:** OVH US is legally separate entity; no technical/hierarchical link to prevent US authorities accessing EU customer data

**Sovereignty Score:** ⭐⭐⭐⭐⭐ (5/5) - Sovereign cloud reference, SecNumCloud certified

---

### 5. UpCloud (Finland)

**Type:** Finnish cloud infrastructure provider  
**Founded:** 2012  
**Headquarters:** Helsinki, Finland

#### Key Features

- **MaxIOPS Storage**: Fastest storage in industry
- **Zero Egress Fees**: No internet transfer costs (since 2024)
- **Global Presence**: 12 data centers across 4 continents
- **100% SLA**: Uninterrupted service guarantee
- **Developer-Focused**: Comprehensive API, CLI, Terraform, Pulumi support
- **AMD EPYC Turin**: First to market with next-gen processors (30-40% performance boost)
- **Managed Services**: Kubernetes, databases (MySQL, PostgreSQL)
- **VPN Gateway**: Secure multi-cloud connectivity

#### Strengths

- ⚡ **Performance Leader**: MaxIOPS storage, fastest deployments
- 💰 **Cost Predictable**: Zero egress fees, transparent pricing
- 🇫🇮 **Nordic Sovereignty**: Finnish ownership, EU data governance
- 🏆 **Customer Satisfaction**: 92.6% satisfaction, NPS 52
- 🔧 **24/7 Support**: 46-second average response time (2024)
- ♻️ **Sustainability**: 70% renewable energy data centers

#### Considerations

- **Narrower Service Portfolio**: Focus on core IaaS (compute, storage, network, Kubernetes)
- **No CDN Yet**: Despite global presence (expected addition)
- **Best For**: Developers, startups, SMEs needing performance and predictable costs

#### Digital Sovereignty Profile

**Jurisdiction:** Finnish law, EU GDPR compliant  
**Data Location:** European data centers (Helsinki, Frankfurt, Amsterdam, Madrid, London, Warsaw) + global  
**Ownership:** Finnish private company  
**Certifications:** ISO 27001, GDPR compliant, CISPE member  
**CLOUD Act Exposure:** ❌ None (European jurisdiction)  
**Special Advocacy:** Publicly critical of Finnish government using AWS for electoral system

**Sovereignty Score:** ⭐⭐⭐⭐⭐ (5/5) - Strong Nordic sovereignty, sovereignty advocate

---

### 6. Exoscale (Switzerland)

**Type:** Swiss sovereign cloud provider  
**Founded:** 2011  
**Parent Company:** A1 Digital (A1 Group)  
**Headquarters:** Lausanne, Switzerland

#### Key Features

- **Swiss Data Privacy**: Subject to strict Swiss data protection laws
- **European Data Centers**: Switzerland, Austria, Germany, Croatia, Bulgaria
- **Geo-Locking**: Workloads started in Austria stay in Austria (guaranteed)
- **S3-Compatible Storage**: European object storage
- **Managed Kubernetes**: Cloud-native orchestration
- **GPU Instances**: NVIDIA RTX 3080 Ti, RTX A5000, A30, A40
- **Pay-As-You-Go**: Second-level billing
- **Sustainable**: Focus on renewable energy and efficiency

#### Strengths

- 🇨🇭 **Swiss Sovereignty**: Not subject to EU or US law
- 🔐 **Privacy-First**: Strictest data protection standards
- 🏔️ **Neutral Jurisdiction**: Swiss neutrality benefits
- 🤝 **EuroStack Supporter**: Active in European sovereignty initiatives
- 🌱 **Environmental Focus**: Low CO₂ footprint
- 📊 **Transparent**: Simple pricing, sovereignty reports

#### Considerations

- **Smaller Scale**: Less extensive service catalog than hyperscalers
- **Premium Positioning**: Swiss quality at Swiss prices
- **Best For**: Regulated industries (finance, healthcare), privacy-sensitive workloads, Swiss/Austrian/German markets

#### Digital Sovereignty Profile

**Jurisdiction:** Swiss law (not EU, but GDPR-aligned)  
**Data Location:** Switzerland, Austria, Germany, Croatia, Bulgaria  
**Ownership:** A1 Digital (Austrian/European ownership)  
**Certifications:** ISO 27001, CSA, ISO 27018, GDPR compliant  
**CLOUD Act Exposure:** ❌ None (Swiss/European jurisdiction)  
**Special Status:** Swiss legal framework provides additional protection

**Sovereignty Score:** ⭐⭐⭐⭐⭐ (5/5) - Premium sovereignty, Swiss neutrality

---

### 7. IONOS (Germany)

**Type:** German cloud and hosting provider  
**Founded:** 1998 (as 1&1)  
**Parent Company:** United Internet AG  
**Headquarters:** Karlsruhe, Germany

#### Key Features

- **Europe's #1 Digitalisation Partner**: 8M+ customer contracts
- **SECA API**: Co-creator of Sovereign European Cloud API standard
- **EuroStack Member**: Active in European cloud standardization
- **Data Centre Designer**: Visual infrastructure configuration tool
- **Stackable Data Platform**: Managed data analytics platform
- **German Data Centers**: 9 EU data centers, 100% renewable energy
- **Nextcloud Partnership**: Sovereign Microsoft 365 alternative (2025 launch)
- **AI Infrastructure**: NVIDIA DGX H200 systems deployed

#### Strengths

- 🇩🇪 **German Market Leader**: Dominant position in German SME market
- 🤝 **Open Standards**: SECA API, Gaia-X, Sovereign-X leadership
- 💼 **Enterprise Ready**: Decades of experience, comprehensive services
- 🌱 **100% Renewable**: All EU data centers powered by renewable energy
- 🔓 **Interoperability**: Fighting vendor lock-in through open standards
- 📊 **SME Focused**: Purpose-built for German businesses

#### Considerations

- **German Language**: Documentation primarily in German
- **Geographic Focus**: Strongly German/European-centric
- **Best For**: German SMEs, public sector, organizations requiring German data residency

#### Digital Sovereignty Profile

**Jurisdiction:** German law, EU GDPR compliant  
**Data Location:** Germany and EU  
**Ownership:** German company (United Internet AG)  
**Certifications:** ISO 27001, German data protection standards  
**CLOUD Act Exposure:** ❌ None (German jurisdiction)  
**Special Initiatives:** SECA API, EuroStack, Gaia-X, Nextcloud Workspace partnership

**Sovereignty Score:** ⭐⭐⭐⭐⭐ (5/5) - German sovereignty champion, standards leader

---

### 8. Server.net, Gridscale, Elastx, Cyso (Brief Overview)

**Note:** Limited recent public information available for these providers. They represent smaller European alternatives worth investigating based on specific regional requirements.

#### Server.net (Netherlands)

- Dutch infrastructure provider
- Focus on reliability and performance
- European data sovereignty

#### Gridscale (Germany)

- German cloud infrastructure
- Developer-friendly platform
- GDPR compliant

#### Elastx (Sweden)

- Swedish OpenStack-based cloud
- Scandinavian data centers
- Focus on privacy and compliance

#### Cyso (Netherlands)

- Dutch managed hosting
- Enterprise solutions
- European infrastructure

**Recommendation:** Request detailed information directly from these providers if their regional presence aligns with your requirements.

---

## Digital Sovereignty Comparison Matrix

| Provider     | Jurisdiction | SecNumCloud | ISO 27001 | CLOUD Act | Ownership      | Sustainability | Score      |
| ------------ | ------------ | ----------- | --------- | --------- | -------------- | -------------- | ---------- |
| **Krystal**  | UK           | ❌          | ✅        | ❌ None   | UK Independent | ⭐⭐⭐⭐⭐     | ⭐⭐⭐⭐   |
| **Coolify**  | Your Choice  | Your Choice | N/A       | ❌ None   | Open Source    | N/A            | ⭐⭐⭐⭐⭐ |
| **Scaleway** | FR/EU        | 🔄 Pending  | ✅        | ❌ None   | FR (Iliad)     | ⭐⭐⭐⭐⭐     | ⭐⭐⭐⭐⭐ |
| **OVHcloud** | FR/EU        | ✅ v3.2     | ✅        | ❌ None   | FR Public      | ⭐⭐⭐⭐⭐     | ⭐⭐⭐⭐⭐ |
| **UpCloud**  | FI/EU        | ❌          | ✅        | ❌ None   | FI Private     | ⭐⭐⭐⭐       | ⭐⭐⭐⭐⭐ |
| **Exoscale** | CH/EU        | ❌          | ✅        | ❌ None   | AT (A1)        | ⭐⭐⭐⭐       | ⭐⭐⭐⭐⭐ |
| **IONOS**    | DE/EU        | ❌          | ✅        | ❌ None   | DE Public      | ⭐⭐⭐⭐⭐     | ⭐⭐⭐⭐⭐ |

**Legend:**

- ✅ Certified/Yes
- ❌ Not Applicable/None
- 🔄 In Progress

---

## Key Decision Factors

### 1. Digital Sovereignty Requirements

**HIGH SECURITY (Government, Defense, Critical Infrastructure):**

- **Primary Choice:** OVHcloud (SecNumCloud certified, Bare Metal Pod)
- **Alternative:** Exoscale (Swiss law, maximum privacy)
- **Self-Hosted:** Coolify on OVHcloud/Exoscale

**REGULATED INDUSTRIES (Finance, Healthcare, Legal):**

- **Primary Choice:** OVHcloud, Exoscale, IONOS
- **Alternative:** UpCloud (strong compliance, performance)

**GENERAL BUSINESS (SME, Startups):**

- **Primary Choice:** UpCloud (performance, zero egress)
- **Alternative:** Scaleway (AI/innovation), IONOS (German market)
- **UK-Specific:** Krystal (UK sovereignty, support)

### 2. Technical Requirements

**AI/ML WORKLOADS:**

- **Winner:** Scaleway (H100 GPUs, Generative APIs, European AI leadership)
- **Alternative:** IONOS (DGX H200), Exoscale (GPU instances)

**HIGH PERFORMANCE:**

- **Winner:** UpCloud (MaxIOPS, AMD EPYC Turin)
- **Alternative:** Scaleway (bare metal), OVHcloud (dedicated servers)

**DEVELOPER EXPERIENCE:**

- **Winner:** UpCloud (zero egress, simple pricing, fast support)
- **Alternative:** Coolify (self-hosted PaaS)

**MULTI-CLOUD / HYBRID:**

- **Winner:** IONOS (SECA API, interoperability focus)
- **Alternative:** Coolify (cloud-agnostic deployment)

### 3. Cost Optimization

**PREDICTABLE COSTS:**

- **Winner:** UpCloud (zero egress fees)
- **Alternative:** Coolify (only server costs)

**BUDGET-CONSCIOUS:**

- **Winner:** Coolify + any provider
- **Alternative:** UpCloud, Scaleway

**ENTERPRISE SCALE:**

- **Winner:** OVHcloud (competitive pricing at scale)
- **Alternative:** Scaleway, IONOS

### 4. Geographic Requirements

**UK PRESENCE REQUIRED:**

- **Winner:** Krystal (UK-based, UK data centers)

**FRENCH/EU PUBLIC SECTOR:**

- **Winner:** OVHcloud (SecNumCloud)
- **Alternative:** Scaleway

**GERMAN MARKET:**

- **Winner:** IONOS (German leader, German support)
- **Alternative:** OVHcloud

**SWISS REQUIREMENTS:**

- **Winner:** Exoscale (Swiss law)

**NORDIC REGION:**

- **Winner:** UpCloud (Finnish, Nordic focus)
- **Alternative:** Elastx (Swedish)

---

## Strategic Recommendations

### Recommendation 1: Multi-Provider Strategy

**Rationale:** No single provider excels at everything. Gartner predicts 75% of enterprises will need digital sovereignty strategies by 2030.

**Approach:**

```
PRIMARY WORKLOADS → European provider (based on requirements)
SELF-HOSTED APPS → Coolify on European infrastructure
DEVELOPMENT/TESTING → UpCloud (zero egress, fast deployment)
HIGH-SECURITY → OVHcloud (SecNumCloud) or Exoscale (Swiss law)
AI/ML → Scaleway (GPU infrastructure)
```

### Recommendation 2: Start with Coolify

**For Organizations With:**

- In-house DevOps expertise
- Cost sensitivity
- Maximum control requirements
- Ability to manage infrastructure

**Implementation:**

1. Deploy Coolify on 2-3 European providers (risk mitigation)
2. Use European VPS providers as base infrastructure
3. Maintain full sovereignty and portability
4. Eliminate egress fees and vendor lock-in

### Recommendation 3: Tiered Approach

**Tier 1 - Critical/Regulated Data:**

- OVHcloud Bare Metal Pod (SecNumCloud)
- Exoscale (Swiss law)

**Tier 2 - Business Applications:**

- UpCloud (performance, support)
- IONOS (German market)

**Tier 3 - Development/Staging:**

- Coolify on any provider
- Scaleway Dedibox

---

## Implementation Roadmap

### Phase 1: Assessment (Weeks 1-2)

- [ ] Audit current cloud usage and data classification
- [ ] Identify sovereignty requirements by jurisdiction
- [ ] Map workloads to sovereignty tiers
- [ ] Calculate current costs (including hidden egress fees)

### Phase 2: Pilot (Weeks 3-6)

- [ ] Deploy Coolify test environment on 2 European providers
- [ ] Migrate non-critical workload to chosen provider
- [ ] Test performance, support, and compliance
- [ ] Validate cost model

### Phase 3: Migration (Weeks 7-16)

- [ ] Develop migration plan by workload tier
- [ ] Migrate Tier 3 (development) workloads
- [ ] Migrate Tier 2 (business) workloads
- [ ] Migrate Tier 1 (critical) workloads with extensive testing
- [ ] Implement monitoring and governance

### Phase 4: Optimization (Ongoing)

- [ ] Monitor costs and performance
- [ ] Optimize resource utilization
- [ ] Review compliance and audit logs
- [ ] Evaluate new European provider services
- [ ] Update sovereignty strategy quarterly

---

## Cost-Benefit Analysis

### Traditional US Hyperscaler

- **Egress Fees:** $0.08-0.12/GB = €73-110/TB
- **Vendor Lock-in:** High (proprietary services)
- **CLOUD Act Risk:** Yes (extraterritorial access)
- **Compliance Cost:** €1.3M annually (mid-sized firm average)
- **Support Quality:** Tier-1 outsourced

### European Sovereign Provider (e.g., UpCloud)

- **Egress Fees:** €0 (zero egress)
- **Vendor Lock-in:** Low (standard APIs, open source)
- **CLOUD Act Risk:** None (European jurisdiction)
- **Compliance Cost:** Lower (native GDPR alignment)
- **Support Quality:** Direct, expert, 46s response

### Self-Hosted (Coolify)

- **Egress Fees:** €0 (your infrastructure)
- **Vendor Lock-in:** None (portable)
- **CLOUD Act Risk:** None (your choice of infrastructure)
- **Compliance Cost:** Dependent on infrastructure choice
- **Support Quality:** Self-managed + community

**Estimated Savings:** 30-60% compared to US hyperscalers for European workloads

---

## Risk Assessment

### Technical Risks

| Risk                 | Impact | Mitigation                                   |
| -------------------- | ------ | -------------------------------------------- |
| Provider outage      | High   | Multi-provider strategy, multi-AZ deployment |
| Migration complexity | Medium | Phased approach, extensive testing           |
| Skill gaps           | Medium | Training, documentation, support contracts   |
| Performance issues   | Low    | Pilot testing, benchmark validation          |

### Business Risks

| Risk               | Impact     | Mitigation                                        |
| ------------------ | ---------- | ------------------------------------------------- |
| Vendor viability   | Low-Medium | Choose established providers (OVHcloud, Scaleway) |
| Regulatory changes | Medium     | Monitor EU regulations, flexible architecture     |
| Cost overruns      | Low        | Fixed pricing, zero egress models                 |
| Compliance failure | High       | Use certified providers (SecNumCloud, ISO 27001)  |

### Strategic Risks

| Risk                       | Impact | Mitigation                                         |
| -------------------------- | ------ | -------------------------------------------------- |
| US hyperscaler retaliation | Low    | Already occurring (pricing, feature restrictions)  |
| Geopolitical shifts        | Medium | Diversify across multiple EU jurisdictions         |
| Technology lag             | Low    | European providers innovating rapidly (AI, RISC-V) |

---

## Success Metrics

### Technical Metrics

- **Uptime:** ≥99.95% (target: 100% SLA)
- **Response Time:** <50ms latency improvement
- **Deployment Speed:** <5 minutes for new instances
- **Support Response:** <60 seconds initial response

### Business Metrics

- **Cost Reduction:** 30-50% vs previous provider
- **Compliance Score:** 100% GDPR audit pass rate
- **Vendor Lock-in:** 0 proprietary services
- **Egress Costs:** €0 (zero egress model)

### Sovereignty Metrics

- **Data Residency:** 100% in chosen EU jurisdiction
- **CLOUD Act Exposure:** 0% (no US provider access)
- **Audit Trail:** Complete sovereignty documentation
- **Reversibility:** 100% data portability

---

## Conclusion

**Primary Recommendation:**

For organizations prioritizing digital sovereignty with balanced needs:

1. **Enterprise/Regulated:** **OVHcloud** (SecNumCloud, scale, sovereignty leader)
2. **SME/Startups:** **UpCloud** (performance, zero egress, excellent support)
3. **AI/ML Focus:** **Scaleway** (European AI leadership, GPU infrastructure)
4. **German Market:** **IONOS** (German sovereignty, SECA API, SME focus)
5. **Maximum Privacy:** **Exoscale** (Swiss law, highest privacy standards)
6. **UK-Specific:** **Krystal** (UK sovereignty, sustainability, support)
7. **Maximum Control:** **Coolify** + any European provider (ultimate flexibility)

**For Most Organizations:** Start with **UpCloud** for production workloads (performance, support, cost) + **Coolify** for self-hosted applications (flexibility, control) + **OVHcloud** or **Exoscale** for high-security workloads (compliance, certification).

**Key Insight:** Digital sovereignty is not just about compliance—it's a competitive advantage. European providers now offer performance, features, and pricing competitive with US hyperscalers while guaranteeing data sovereignty, eliminating vendor lock-in, and supporting European digital independence.

---

## Further Reading

### Official Resources

- **Gartner IT Symposium 2025:** Digital Sovereignty Predictions
- **European Commission:** Digital Markets Act, AI Act, Data Act
- **ANSSI (France):** SecNumCloud Qualification
- **CISPE:** Cloud Infrastructure Services Providers in Europe

### Provider Documentation

- Coolify: https://coolify.io/docs
- Krystal: https://krystal.io/docs
- Scaleway: https://www.scaleway.com/en/docs/
- OVHcloud: https://help.ovhcloud.com/
- UpCloud: https://upcloud.com/docs/
- Exoscale: https://community.exoscale.com/
- IONOS: https://www.ionos.de/hilfe/

### Industry Reports

- **IDC:** European Public Cloud IaaS 2024 Vendor Assessment
- **Forrester:** Digital Sovereignty Summit 2025 Report
- **Nextcloud:** Digital Sovereignty Index 2024

---

## Appendix: Quick Comparison Table

| Feature     | Krystal    | Coolify     | Scaleway   | OVHcloud   | UpCloud    | Exoscale | IONOS      |
| ----------- | ---------- | ----------- | ---------- | ---------- | ---------- | -------- | ---------- |
| **Region**  | UK         | Any         | FR         | FR         | FI         | CH       | DE         |
| **Egress**  | Std        | Free        | Std        | Std        | Free       | Std      | Std        |
| **AI/GPU**  | ❌         | N/A         | ⭐⭐⭐     | ⭐⭐       | ⭐         | ⭐⭐     | ⭐⭐       |
| **SecNum**  | ❌         | N/A         | 🔄         | ✅         | ❌         | ❌       | ❌         |
| **Support** | ⭐⭐⭐⭐⭐ | Community   | ⭐⭐⭐⭐   | ⭐⭐⭐⭐   | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐   |
| **Price**   | €€         | Server Only | €€         | €€         | €€         | €€€      | €€         |
| **Scale**   | SME        | DIY         | Enterprise | Enterprise | SME-Ent    | SME-Ent  | Enterprise |
| **Green**   | ⭐⭐⭐⭐⭐ | N/A         | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐   | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |

**Legend:**

- ⭐ = Basic/Limited
- ⭐⭐⭐ = Good
- ⭐⭐⭐⭐⭐ = Excellent/Best-in-class
- € = Budget, €€ = Competitive, €€€ = Premium
- Std = Standard egress fees apply

---

**Document Version:** 1.0  
**Last Updated:** 2025-11-20  
**Next Review:** 2026-02-20  
**Approvers:** [Infrastructure Team, Security Team, Compliance Officer]

---

## Decision

**Status:** [PROPOSED / ACCEPTED / REJECTED / SUPERSEDED]  
**Date Decided:** [To be completed]  
**Decided By:** [To be completed]  
**Implementation Owner:** [To be completed]  
**Budget Approved:** [To be completed]

---

_This ADR provides a comprehensive foundation for European cloud provider selection with a focus on digital sovereignty. Organizations should customize recommendations based on their specific regulatory requirements, technical needs, and strategic objectives._
