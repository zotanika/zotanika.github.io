# Potential Customers & Tapping Strategy

Based on the Z Venture Capital portfolio and the `enVector` product capabilities, we have identified the following potential customers. Each entry includes their website, the rationale for why they need secure vector search, and a specific strategy to approach them.

## 1. AI Agent & Data Companies
**Persona Strategy:** Pitch "Zero-Trust Memory." Enable them to sell to privacy-conscious enterprise/government clients by promising that even the platform provider cannot see the user's data.

### [WRTN TECHNOLOGIES INC.](https://wrtn.io/) (#AI, #Korea)
- **Business:** Generative AI platform / Assistant.
- **Why enVector:** User prompts and generated content are highly sensitive. `enVector` ensures user history remains private even from WRTN's own backend.
- **Tapping Strategy:** Target the CTO. Demonstrate `enVector` as a way to unlock enterprise contracts that are currently blocked by data privacy concerns. Show them how to replace their current vector store with our encrypted MCP server.

### [ZEALS Co., Ltd.](https://zeals.co.jp/) (#AI, #Commerce, #Japan)
- **Business:** Chat Commerce Application (Chatbots).
- **Why enVector:** Conversational data contains personal preferences and purchase intent which is PII.
- **Tapping Strategy:** Pitch "Liability Reduction." If their logs are breached, it's just ciphertext. Position `enVector` as a safety net for their massive volume of consumer interactions.

### [Turing Inc.](https://tur.ing/) (#AI, #Japan)
- **Business:** Fully autonomous driving AI.
- **Why enVector:** Perception data and driving logs are proprietary and contain sensitive location/video data.
- **Tapping Strategy:** Approach the R&D team. Propose `enVector` for their internal data lakes to search through driving scenarios (e.g., "find similar left turns") without exposing raw data to the entire engineering org.

### [Helpfeel Inc.](https://helpfeel.com/) (#AI, #SaaS, #Japan)
- **Business:** FAQ and Enterprise Search SaaS.
- **Why enVector:** "Secure search" is a massive differentiator for their enterprise clients (banks, insurance) who use Helpfeel for internal docs.
- **Tapping Strategy:** Suggest a "Premium Secure Tier" for their SaaS, powered by `enVector`.

### [Pictoria Inc.](https://www.pictoria.co.jp/) (#AI, #Japan)
- **Business:** AI VTuber technology.
- **Why enVector:** Character "memory" and interactions could be stored securely, preserving the "soul" of the AI character privately.
- **Tapping Strategy:** Focus on IP protection. The unique behavioral vectors of their VTubers are trade secrets.

### [DATAMAKER CORP.](https://www.datamaker.io/) (#AI, #Korea)
- **Business:** Data labeling and processing.
- **Why enVector:** They handle 3rd party datasets. Secure handling is their core business requirement.
- **Tapping Strategy:** "Audit-proof your pipeline." Use `enVector` to guarantee to clients that their raw data is never indexed in plaintext.

---

## 2. Fintech & Crypto Companies
**Persona Strategy:** Pitch "Compliance-as-Code." End-to-end encryption satisfies Data Sovereignty and financial regulations (GDPR, PCI-DSS) while still allowing advanced similarity search for fraud detection or analytics.

### [LayerX Inc.](https://layerx.co.jp/) (#Fintech, #SaaS, #Japan)
- **Business:** Digitizing corporate activities, expense management (Bakuraku).
- **Why enVector:** Corporate transaction data requires the highest security standards.
- **Tapping Strategy:** Target the CISO/Engineering VPs. Pitch "Encrypted Audit Log Search" or similar internal tools that require zero-knowledge properties.

### [SmartBank, Inc.](https://smartbank.co.jp/) (#Fintech, #Japan)
- **Business:** Personal finance (B/43).
- **Why enVector:** Storing transaction embeddings for similarity search (e.g., "find similar expenses") requires strict privacy.
- **Tapping Strategy:** "Fraud detection without PII exposure." Show how embeddings can identify spending patterns without creating a honey-pot of raw transaction data.

### [miive, Inc.](https://miive.jp/) (#Fintech, #Japan)
- **Business:** Corporate card and benefits.
- **Why enVector:** Employee spending data is sensitive corporate intel.
- **Tapping Strategy:** Similar to LayerX—focus on the security of the underlying data infrastructure.

### [Habit factory](https://www.habitfactory.co/) (#Fintech, #Korea)
- **Business:** Insurance and financial analysis (Signal Planner).
- **Why enVector:** Medical and financial data combined. Extremely high sensitivity.
- **Tapping Strategy:** Highlight the "Double Lock": protecting both health and wealth data simultaneously.

### [CHEQUER Inc.](https://www.querypie.com/) (#Cybersecurity, #Data, #SaaS)
- **Business:** Data governance and security (QueryPie).
- **Why enVector:** They are a perfect "Primary Customer." They understand the tech. They could integrate `enVector` to offer "Encrypted Audit Log Search" to their own customers.
- **Tapping Strategy:** **Partnership Pitch.** Don't just sell it as a tool, sell it as a component for *their* product. "Add Encrypted Vector Search to QueryPie."

### [Kyuzan Inc.](https://kyuzan.com/) (#Crypto, #Japan)
- **Business:** Blockchain gaming and NFT platform.
- **Why enVector:** Off-chain user metadata and behavioral profiles benefit from encryption.
- **Tapping Strategy:** "Web3 Privacy for Web2 Data." Appeal to their crypto-native ethos of user ownership and privacy.

---

## 3. Healthcare Companies
**Persona Strategy:** Pitch "HIPAA-Ready Vector Database." Store patient vectors without ever exposing PHI. Avoid anonymization that degrades model performance by using encryption instead.

### [Munice Inc.](https://munice.com/index.html) (#Healthcare, #Korea)
- **Business:** Sleep and mental health data (Miracle Night).
- **Why enVector:** Sleep patterns are biometric fingerprints.
- **Tapping Strategy:** Pitch "Ethical AI." Build a brand around privacy-preserving sleep analysis.

### [Aillis, Inc.](https://aillis.jp/) (#Healthcare, #Japan)
- **Business:** Medical AI (Influenza diagnosis, etc.).
- **Why enVector:** Diagnostic data and patient records used in vector search (e.g., symptom matching) must be encrypted.
- **Tapping Strategy:** Target the Compliance Officer. "Reduce your HIPAA/GDPR liability to near zero for this dataset."

### [Genon, Inc](https://genon.co.jp/about) / [Welmo Inc.](https://welmo.co.jp/)
- **Business:** Genetic testing / Elderly care.
- **Why enVector:** Genetic data is the ultimate PII.
- **Tapping Strategy:** "Sovereign Genetic Data." Ensure that genetic markers are searchable but never viewable.

---

## 4. SaaS & Enterprise Tools
**Persona Strategy:** Differentiate via "Security-First" features.

### [Visional, Inc.](https://www.visional.inc/ja/index.html) (#HR, #SaaS)
- **Business:** HR Tech (BizReach, HRMOS).
- **Why enVector:** Resume and candidate data is PII.
- **Tapping Strategy:** "Private Semantic Search" for candidate matching. Allow recruiters to find "similar candidates" without exposing the entire database to every query.
