# Customer Value Integration: enVector
This document illustrates how `enVector` integrates with the specific business architectures of key potential customers to deliver "Monetizable Privacy" and "Regulatory Compliance."

## 1. WRTN Technologies (GenAI Agent Platform)
**Value Prop:** **"Zero-Knowledge Memory" for Enterprise Agents.**
WRTN can offer a "Private Mode" where even they (the platform provider) cannot access the user's Retrieval-Augmented Generation (RAG) history.

```mermaid
sequenceDiagram
    participant U as Enterprise User
    participant W as WRTN Agent (SaaS)
    participant E as enVector (Encrypted Memory)
    participant L as LLM (Stateless)

    Note over U, W: "Private Mode" Enabled
    U->>U: Generate Query Embedding (E_q) <br/> Encrypt with User Key
    U->>W: Send Encrypted Query (E_q)
    
    Note over W: WRTN cannot read E_q
    W->>E: Forward Encrypted Query (E_q)
    
    Note over E: Homomorphic/Encrypted Search
    E->>E: Search encrypted index
    E-->>W: Return Encrypted Results (E_mem)
    
    W-->>U: Return Encrypted Results (E_mem)
    U->>U: Decrypt E_mem (Context)
    
    U->>L: Send Prompt + Decrypted Context
    L-->>U: Final Answer
    
    Note over U, E: Value: WRTN hosts the Agent, but User owns the Memory.
```

---

## 2. Turing Inc. (Autonomous Driving)
**Value Prop:** **Secure Data Exchange for Partners.**
Turing has vast driving datasets. Tier 1 suppliers or researchers want to search this data (e.g., "scenes with pedestrians at night") without Turing exposing the entire raw dataset or the partners exposing their proprietary search queries.

```mermaid
flowchart LR
    subgraph "Turing Data Lake"
        Raw[Raw Driving Video] -->|Feature Extraction| CNN[Vision Model]
        CNN -->|Encrypt Vectors| EV[enVector Index]
    end

    subgraph "Partner (Tier 1 Supplier)"
        Eng[Engineer] -->|Text Query| Enc[Encrypt Search Query]
    end

    Enc -- "Encrypted Query (e.g., 'Rainy Night')" --> EV
    EV -- "Encrypted Indices (Timecodes)" --> Enc
    
    Enc -->|Decrypt| Res[Result List]
    Res -->|Request Specific Clips| Raw
    
    style EV fill:#f9f,stroke:#333
    
    Note["Value: <br/>1. Turing protects dataset structure<br/>2. Partner protects search intent<br/>3. Minimal data egress"]
```

---

## 3. LayerX (Bakuraku - Fintech)
**Value Prop:** **Compliance-Ready Financial Search.**
Bakuraku handles sensitive invoices. `enVector` enables features like "Find similar past invoices" for fraud detection while keeping the data encrypted, satisfying strict financial regulations (GDPR/PCI-DSS compliant architecture).

```mermaid
graph TD
    User[Corporate User] -->|Upload Invoice| App[Bakuraku App]
    
    subgraph "Bakuraku Cloud (LayerX)"
        App -->|OCR Process| PII[PII Extraction]
        PII -->|Tokenize/Encrypt| DB[(Standard DB - Encrypted)]
        
        PII -->|Generate Embedding| Vec[Vector Embedding]
        Vec -->|Encrypt| EV[(enVector - Secure Search)]
    end
    
    User -->|Search: 'Suspicious Duplicate?'| App
    App -->|Encrypted Vector Search| EV
    EV -->|Encrypted Candidates| App
    App -->|Decrypt & Match| Alert[Fraud Alert]
    
    style EV fill:#f9f,stroke:#333
    
    classDef secure fill:#e1f5fe,stroke:#01579b,stroke-width:2px;
    class App,DB,EV secure
```

---

## 4. CHEQUER (QueryPie - Security)
**Value Prop:** **Tamper-Proof Audit Logs for AI (MCP PAM).**
QueryPie acts as a gateway for AI agents. By storing the *audit logs* (who prompted what) in `enVector`, they ensure that the logs themselves are searchable by security teams but protected from tampering or leakage, even if the logging server is compromised.

```mermaid
sequenceDiagram
    participant Admin as Security Admin
    participant QP as QueryPie (MCP PAM)
    participant EV as enVector (Log Storage)
    participant AI as Internal AI Models

    Note over QP, AI: Monitor & Log Interactions
    QP->>QP: Capture Prompt/Response
    QP->>QP: Create Vector Embedding of Log
    QP->>EV: Store Encrypted Log Vector

    Note over Admin: Incident Investigation
    Admin->>QP: "Show all SQL injection attempts"
    QP->>QP: Vectorize Query
    QP->>EV: Search Encrypted Logs
    EV-->>QP: Return Encrypted Matches
    QP->>Admin: Decrypt & Display Risk Report
    
    Note over EV: Value: "Sealed" Evidence Locker
```

---

## 5. ZEALS (Chat Commerce)
**Value Prop:** **Zero-Knowledge RAG for Personalized Ads.**
ZEALS uses RAG to power "Auto Chat." `enVector` ensures that the user's profile and conversation history (stored in vector memory) are encrypted, protecting consumer privacy while enabling highly personalized ad targeting.

```mermaid
sequenceDiagram
    participant U as Consumer (LINE/Instagram)
    participant Z as ZEALS Auto Chat
    participant EV as enVector (User Profile Memory)
    participant LLM as Generator

    U->>Z: "I'm looking for skin care for dry skin."
    Z->>Z: Extract Intent & Encrypt
    Z->>EV: Search Encrypted User History
    EV-->>Z: Return Encrypted Preferences (e.g., "Budget: High")
    
    Z->>Z: Decrypt Context (in secure enclave/ephemeral)
    Z->>LLM: Generate Product Recommendation
    LLM-->>Z: "Try this premium moisturizer."
    Z-->>U: Send Recommendation
    
    Note over EV: Data at rest is encrypted. <br/>ZEALS reduces PII liability.
```

---

## 6. SmartBank (B/43 - Fintech)
**Value Prop:** **Secure eKYC & Transaction Analysis.**
SmartBank focuses on "Household Finance." Analyzing spending habits creates a very detailed private profile. `enVector` allows them to build "Similar User" features or "Recurring Payment Detection" without exposing raw financial history to the analysis engine.

```mermaid
flowchart TD
    subgraph "SmartBank (AWS)"
        App[Mobile App B/43] -->|Transaction Feed| Srv[Backend Server]
        Srv -->|Write| DB[(Main DB - Encrypted)]
        
        Srv -->|Vectorize Transaction| Vec[Emb]
        Vec -->|Encrypt| EV[(enVector)]
    end
    
    subgraph "Analyst / Fraud Engine"
        Eng[Engine] -->|Encrypted Query| EV
        EV -->|Encrypted Matches| Eng
        Eng -->|Decrypt Local| Result[Fraud Score / Insight]
    end
    
    style EV fill:#f9f,stroke:#333
```

---

## 7. Visional (BizReach - HR Tech)
**Value Prop:** **Privacy-Preserving Resume Matching (SPLADE).**
Visional uses "Sparse Vector Search" (SPLADE) for matching. `enVector` can support encrypted sparse vectors, allowing them to match candidates to job descriptions without the matching engine "seeing" the candidate's name or current employer, preventing bias and leakage.

```mermaid
graph LR
    Candidate -->|Resume| Biz[BizReach]
    Recruiter -->|Job Description| Biz
    
    subgraph "Search Infrastructure"
        Biz -->|Generate Sparse Vector| SPLADE[SPLADE Model]
        SPLADE -->|Encrypt| EV[(enVector - Encrypted Sparse Index)]
    end
    
    Recruiter -->|Search| EV
    EV -->|Encrypted Candidate IDs| Recruiter
    
    Note["Value: <br/>Bias-Free Matching (Blind Search)<br/>PII Protection for Candidates"]
```

---

## 8. Helpfeel (Enterprise Search SaaS)
**Value Prop:** **"Secure Search" as a Premium Feature.**
Helpfeel's core value is "Findability." For clients like banks or insurance firms, internal knowledge bases contain sensitive operational info. `enVector` allows Helpfeel to offer a "Zero-Trust FAQ" where the index is encrypted.

```mermaid
sequenceDiagram
    participant U as End User (Employee)
    participant H as Helpfeel (Intent Prediction)
    participant EV as enVector (Encrypted FAQ Index)
    participant R as Resolver (RAG/Answer)

    U->>H: "How do I process a Level 4 claim?"
    H->>H: Predict Intent & Vectorize
    H->>EV: Search Encrypted Knowledge Base
    
    Note over EV: Helpfeel sees only vectors, <br/>not the secret claims docs.
    EV-->>H: Return Encrypted Document IDs
    
    H->>R: Retrieve Content (if auth matches)
    R-->>U: "Here is the Level 4 process..."
    
    Note over U, H: Value: Helpfeel can sell to <br/>defense/gov sectors.
```
