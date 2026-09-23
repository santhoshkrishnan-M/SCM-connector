<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=24&duration=3000&pause=1000&color=00D4FF&center=true&vCenter=true&multiline=true&repeat=true&width=900&height=80&lines=Automotive+SCM+Multi-Agent+Control+Tower;AI-Powered+Supply+Chain+Disruption+Response+System" alt="Typing SVG" />

<br/>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=400&size=14&duration=2500&pause=800&color=58A6FF&center=true&vCenter=true&repeat=true&width=550&lines=4+Agents.+1+Orchestrator.+Zero+Downtime.;From+Disruption+to+Decision+in+Seconds.;Any+ERP.+Same+Agents.+Zero+Code+Changes." alt="Tagline" />

<br/><br/>

<img src="https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/Pandas-2.0-150458?style=for-the-badge&logo=pandas&logoColor=white" />
<img src="https://img.shields.io/badge/NetworkX-3.0-4B8BBE?style=for-the-badge" />
<img src="https://img.shields.io/badge/Zoho_API-OAuth2-DC4A38?style=for-the-badge" />
<img src="https://img.shields.io/badge/Google_Colab-Ready-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" />
<img src="https://img.shields.io/badge/NumPy-1.24-013243?style=for-the-badge&logo=numpy&logoColor=white" />
<img src="https://img.shields.io/badge/Matplotlib-3.7-11557C?style=for-the-badge" />

<br/><br/>

<img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" />
<img src="https://img.shields.io/badge/Build-Passing-brightgreen?style=flat-square" />
<img src="https://img.shields.io/badge/Tests-69%20Passed-brightgreen?style=flat-square" />
<img src="https://img.shields.io/badge/Agents-4+Orchestrator-blue?style=flat-square" />
<img src="https://img.shields.io/badge/Connectors-3%20Implemented-orange?style=flat-square" />
<img src="https://img.shields.io/badge/Coverage-100%25-brightgreen?style=flat-square" />

<br/><br/>

<img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" width="900" />

</div>

---

<details open>
<summary><h2>TABLE OF CONTENTS</h2></summary>

- [The Problem](#-the-problem)
- [The Solution](#-the-solution)
- [System Architecture](#-system-architecture)
- [Agent Pipeline Flowchart](#-agent-pipeline-flowchart)
- [Knowledge Graph](#-knowledge-graph)
- [Agent Report Output](#-agent-report-output)
- [How It Works](#-how-it-works)
- [Quick Start](#-quick-start)
- [Configuration](#-configuration)
- [Connector Abstraction](#-connector-abstraction)
- [Agents Deep Dive](#-agents-deep-dive)
- [Performance Metrics](#-performance-metrics)
- [Testing](#-testing)
- [Tech Stack Breakdown](#-tech-stack-breakdown)
- [Project Structure](#-project-structure)
- [Future Roadmap](#-future-roadmap)

</details>

---

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/225813708-98b745f2-7d22-48cf-9150-083f15b36f93.gif" width="500" />

</div>

## :: The Problem

A single semiconductor supplier goes offline. The cascade begins immediately:

```mermaid
graph LR
    A["Supplier Failure"] -->|affects| B["ECU Parts Unavailable"]
    B -->|halts| C["3 Vehicle Models"]
    C -->|stops| D["2 Assembly Plants"]
    D -->|causes| E["$2.3M/day Loss"]

    style A fill:#e74c3c,stroke:#c0392b,color:#fff
    style B fill:#e67e22,stroke:#d35400,color:#fff
    style C fill:#f39c12,stroke:#e67e22,color:#fff
    style D fill:#3498db,stroke:#2980b9,color:#fff
    style E fill:#9b59b6,stroke:#8e44ad,color:#fff
```

| Metric | Traditional Response | This System |
|--------|---------------------|-------------|
| **Response Time** | 3-5 days | Under 10 seconds |
| **Impact Analysis** | Manual spreadsheets | Automated graph traversal |
| **Supplier Scoring** | Subjective calls | Quantitative multi-factor |
| **Decision Audit** | Email chains | Full negotiation trace |
| **Monitoring** | Weekly manual checks | Continuous auto-scan |
| **Policy Flexibility** | None | Configurable weights |

---

## :: The Solution

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/212257472-08e52665-c503-4bd9-aa20-f5a4dae769b5.gif" width="80" />

<br/>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=16&duration=2000&pause=1000&color=00D4FF&center=true&vCenter=true&repeat=true&width=700&lines=Four+specialized+agents+analyze+every+dimension;Orchestrator+negotiates+the+optimal+combined+plan;Connector+abstraction+makes+it+work+with+any+ERP" alt="Solution" />

</div>

A multi-agent AI system where **four specialized agents** independently evaluate every dimension of a supply chain disruption, then **negotiate through a policy-weighted orchestrator** to produce the optimal combined response.

```mermaid
graph TB
    subgraph "DATA SOURCES"
        S1["Synthetic Tables"]
        S2["Zoho Inventory API"]
        S3["SAP / Oracle (Future)"]
    end

    subgraph "CONNECTOR LAYER"
        CL["SCMConnector Abstract Interface<br/>get_suppliers() | get_inventory()<br/>get_demand() | get_capacity() | get_logistics()"]
    end

    subgraph "INTELLIGENCE LAYER"
        KG["Knowledge Graph<br/>(NetworkX DiGraph)"]
        PA["Procurement Agent<br/>(Source)"]
        IA["Inventory Agent<br/>(Plan)"]
        PRA["Production Agent<br/>(Make)"]
        LA["Logistics Agent<br/>(Deliver)"]
    end

    subgraph "DECISION LAYER"
        OR["Orchestrator<br/>Policy-Weighted Negotiation"]
    end

    subgraph "OUTPUT LAYER"
        RC["HTML Report Cards"]
        PC["Policy Comparison"]
        ML["Monitoring Loop"]
    end

    S1 & S2 & S3 --> CL
    CL --> KG
    CL --> PA & IA & PRA & LA
    KG --> PA & IA & PRA & LA
    PA & IA & PRA & LA --> OR
    OR --> RC & PC & ML

    style S1 fill:#e74c3c,stroke:#c0392b,color:#fff
    style S2 fill:#e74c3c,stroke:#c0392b,color:#fff
    style S3 fill:#e74c3c,stroke:#c0392b,color:#fff
    style CL fill:#f39c12,stroke:#e67e22,color:#fff
    style KG fill:#9b59b6,stroke:#8e44ad,color:#fff
    style PA fill:#27ae60,stroke:#229954,color:#fff
    style IA fill:#27ae60,stroke:#229954,color:#fff
    style PRA fill:#27ae60,stroke:#229954,color:#fff
    style LA fill:#27ae60,stroke:#229954,color:#fff
    style OR fill:#2c3e50,stroke:#1a252f,color:#fff
    style RC fill:#3498db,stroke:#2980b9,color:#fff
    style PC fill:#3498db,stroke:#2980b9,color:#fff
    style ML fill:#3498db,stroke:#2980b9,color:#fff
```

---

## :: System Architecture

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/219923809-b86dc415-a0c2-4a38-bc88-ad6cf06395a8.gif" width="400" />

</div>

The system is built on a **Connector Abstraction Pattern** that decouples all intelligence from the data source.

```mermaid
flowchart LR
    subgraph Sources["Data Sources"]
        direction TB
        SYN[("Synthetic<br/>Tables")]
        ZOHO[("Zoho<br/>Inventory")]
        SAP[("SAP/Oracle<br/>Future")]
    end

    subgraph Connector["Connector Interface"]
        direction TB
        SC["SCMConnector<br/>5 Abstract Methods"]
        SYNC["SyntheticSCM<br/>Connector"]
        ZC["Zoho<br/>Connector"]
        ZCP["ZohoPro<br/>Connector"]
    end

    subgraph Agents["Agent Framework"]
        direction TB
        P["Procurement"]
        I["Inventory"]
        PR["Production"]
        L["Logistics"]
    end

    subgraph Output["Decision Engine"]
        direction TB
        O["Orchestrator"]
        R["Report Cards"]
    end

    SYN --> SYNC
    ZOHO --> ZC & ZCP
    SAP --> SC
    SYNC & ZC & ZCP --> P & I & PR & L
    P & I & PR & L --> O
    O --> R

    style SYN fill:#e74c3c,color:#fff
    style ZOHO fill:#e74c3c,color:#fff
    style SAP fill:#95a5a6,color:#fff
    style SC fill:#f39c12,color:#fff
    style SYNC fill:#f39c12,color:#fff
    style ZC fill:#f39c12,color:#fff
    style ZCP fill:#f39c12,color:#fff
    style P fill:#27ae60,color:#fff
    style I fill:#27ae60,color:#fff
    style PR fill:#27ae60,color:#fff
    style L fill:#27ae60,color:#fff
    style O fill:#2c3e50,color:#fff
    style R fill:#3498db,color:#fff
```

---

## :: Agent Pipeline Flowchart

The complete disruption response pipeline from detection to decision:

```mermaid
flowchart TD
    START(["DISRUPTION DETECTED"]) --> TRACE["Knowledge Graph<br/>Impact Tracing"]
    TRACE --> PARTS{"Identify Affected<br/>Parts & Models"}
    PARTS --> |"ECU, Battery, etc."| PARALLEL

    subgraph PARALLEL["PARALLEL AGENT EVALUATION"]
        direction LR
        AG1["PROCUREMENT<br/>Score alternative<br/>suppliers"]
        AG2["INVENTORY<br/>Calculate buffer<br/>days coverage"]
        AG3["PRODUCTION<br/>Evaluate line<br/>rescheduling"]
        AG4["LOGISTICS<br/>Select shipping<br/>mode"]
    end

    PARALLEL --> COLLECT["Collect All<br/>AgentProposals"]
    COLLECT --> POLICY{"Apply Policy<br/>Weights"}
    POLICY -->|"cost_weight"| SCORE["Compute Weighted<br/>Scores"]
    POLICY -->|"time_weight"| SCORE
    SCORE --> DECIDE["Select Optimal<br/>Combination"]
    DECIDE --> REPORT["Generate HTML<br/>Report Card"]
    REPORT --> MONITOR{"Buffer Below<br/>Threshold?"}
    MONITOR -->|"YES"| START
    MONITOR -->|"NO"| SLEEP["Sleep & Rescan"]
    SLEEP --> START

    style START fill:#e74c3c,color:#fff
    style TRACE fill:#9b59b6,color:#fff
    style PARTS fill:#8e44ad,color:#fff
    style AG1 fill:#27ae60,color:#fff
    style AG2 fill:#27ae60,color:#fff
    style AG3 fill:#27ae60,color:#fff
    style AG4 fill:#27ae60,color:#fff
    style COLLECT fill:#f39c12,color:#fff
    style POLICY fill:#e67e22,color:#fff
    style SCORE fill:#d35400,color:#fff
    style DECIDE fill:#2c3e50,color:#fff
    style REPORT fill:#3498db,color:#fff
    style MONITOR fill:#16a085,color:#fff
    style SLEEP fill:#95a5a6,color:#fff
```

---

## :: Knowledge Graph

The supply chain is modeled as a **directed graph** tracing relationships from suppliers through parts, vehicle models, to assembly plants:

```mermaid
graph LR
    subgraph Suppliers["SUPPLIERS (Tier 1-3)"]
        SUP1["SUP_TSMC<br/>Asia"]
        SUP2["SUP_SAMSUNG<br/>Asia"]
        SUP3["SUP_CATL<br/>Asia"]
        SUP4["SUP_MICHELIN<br/>Europe"]
    end

    subgraph Parts["PARTS"]
        ECU["PART_ECU<br/>Engine Control Unit"]
        BAT["PART_BATTERY<br/>Battery Pack"]
        SEAT["PART_SEAT<br/>Driver Seat"]
        TIRE["PART_TIRE<br/>All-Season Tire"]
    end

    subgraph Models["VEHICLE MODELS"]
        M1["MODEL_A<br/>Horizon SUV"]
        M2["MODEL_B<br/>Velocity Sedan"]
        M3["MODEL_C<br/>Pioneer SUV"]
    end

    subgraph Plants["ASSEMBLY PLANTS"]
        P1["PLANT_A<br/>Chennai"]
        P2["PLANT_B<br/>Pune"]
    end

    SUP1 & SUP2 -->|supplies| ECU
    SUP3 -->|supplies| BAT
    SUP4 -->|supplies| TIRE
    SUP1 -->|supplies| SEAT

    ECU -->|used in| M1 & M2
    BAT -->|used in| M3
    SEAT -->|used in| M1 & M2
    TIRE -->|used in| M1 & M2

    M1 & M2 -->|assembled at| P1
    M3 -->|assembled at| P2

    style SUP1 fill:#e74c3c,color:#fff
    style SUP2 fill:#e74c3c,color:#fff
    style SUP3 fill:#e74c3c,color:#fff
    style SUP4 fill:#e74c3c,color:#fff
    style ECU fill:#f39c12,color:#fff
    style BAT fill:#f39c12,color:#fff
    style SEAT fill:#f39c12,color:#fff
    style TIRE fill:#f39c12,color:#fff
    style M1 fill:#3498db,color:#fff
    style M2 fill:#3498db,color:#fff
    style M3 fill:#3498db,color:#fff
    style P1 fill:#27ae60,color:#fff
    style P2 fill:#27ae60,color:#fff
```

When `SUP_TSMC` fails, the graph instantly traces: **ECU + SEAT affected** -> **Horizon SUV + Velocity Sedan halted** -> **PLANT_A impacted**.

---

## :: Agent Report Output

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="900" />

</div>

Real output from the **Tier-3 wafer fab slowdown** scenario running against live Zoho Inventory data:

<div align="center">
<img src="Screenshot_2026-09-23_065446.png" alt="Agent Report Card" width="750"/>
</div>

<br/>

**Reading the Report Card:**

| Column | Meaning |
|--------|---------|
| **Agent** | Which specialized agent produced this recommendation |
| **Recommendation** | The specific action proposed |
| **Cost Impact** | Percentage cost change vs pre-disruption baseline |
| **Time Impact** | Days added (+) or saved (-) vs standard lead time |
| **Confidence** | Agent confidence score (0-100%) |
| **Why** | Data-driven rationale for the recommendation |

The **Final Plan** row shows the orchestrator's combined decision with aggregate metrics.

---

## :: How It Works

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/212257454-16e3712e-945a-4ca2-b238-408ad0bf87e6.gif" width="80" />

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=16&duration=2000&pause=1000&color=00D4FF&center=true&vCenter=true&repeat=true&width=500&lines=Step+by+step+disruption+response+pipeline" alt="How" />

</div>

```mermaid
sequenceDiagram
    participant D as Disruption
    participant KG as Knowledge Graph
    participant PA as Procurement Agent
    participant IA as Inventory Agent
    participant PRA as Production Agent
    participant LA as Logistics Agent
    participant O as Orchestrator
    participant R as Report Card

    D->>KG: Supplier SUP_003 failed
    KG->>KG: Trace impact through graph
    KG-->>PA: Affected: PART_ECU, 3 models, 2 plants
    KG-->>IA: Affected: PART_ECU, 3 models, 2 plants
    KG-->>PRA: Affected: PART_ECU, 3 models, 2 plants
    KG-->>LA: Affected: PART_ECU, 3 models, 2 plants

    par Parallel Evaluation
        PA->>PA: Score 2 alternative suppliers
        IA->>IA: Calculate 16.9 days buffer
        PRA->>PRA: Assess 53% capacity impact
        LA->>LA: Select rail (14d transit)
    end

    PA-->>O: Proposal: Quarzon Materials, +0%, +7d, 82%
    IA-->>O: Proposal: Draw buffer, +0%, +0d, 95%
    PRA-->>O: Proposal: Slow 3 lines, +3.2%, +5.3d, 80%
    LA-->>O: Proposal: Ship rail, +35%, -10d, 85%

    O->>O: Apply policy weights
    O->>O: Score = confidence - (cost * w_c) - (delay * w_t)
    O-->>R: Final: cost +38.2% | schedule +2.3d | confidence 86%
```

---

## :: Quick Start

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/212257468-1e9a91f1-b626-4baa-b15d-5c385dfa7ed2.gif" width="80" />

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=16&duration=2000&pause=1000&color=27AE60&center=true&vCenter=true&repeat=true&width=400&lines=Up+and+running+in+3+steps" alt="Quick Start" />

</div>

**Step 1** -- Open in Google Colab

```
Upload: automotive_scm_multiagent_v2_fixed.ipynb
```

**Step 2** -- Run All Cells (top to bottom)

```
Section  1-2   -->  Data generation + Connector setup
Section  3-4   -->  Knowledge graph + Agent framework
Section  5-8   -->  Orchestration + Demo scenarios
Section  9-14  -->  Zoho live integration + ZohoConnectorPro
Section 15-16  -->  Continuous monitoring + Summary
```

**Step 3** -- View HTML report cards in notebook output

---

## :: Configuration

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/212257460-738ff738-247f-4b0d-a559-a3741f4d3b64.gif" width="80" />

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=16&duration=2000&pause=1000&color=F39C12&center=true&vCenter=true&repeat=true&width=500&lines=Every+parameter+is+configurable.+Zero+code+changes." alt="Config" />

</div>

### Policy Weights

Control the cost-versus-speed tradeoff:

```python
# Time-sensitive: prioritize speed over cost
time_policy = {"cost_weight": 1.0, "time_weight": 1.5}

# Cost-sensitive: minimize spending even if slower
cost_policy = {"cost_weight": 2.0, "time_weight": 0.5}

# Balanced: equal priority
balanced_policy = {"cost_weight": 1.0, "time_weight": 1.0}

# Pass to orchestrator
decision = orchestrator.negotiate(proposals, policy=time_policy)
```

```mermaid
graph LR
    subgraph "Time-Sensitive (1.0 / 1.5)"
        T1["Fastest supplier selected"]
        T2["Air freight preferred"]
        T3["Higher cost accepted"]
    end
    subgraph "Cost-Sensitive (2.0 / 0.5)"
        C1["Cheapest supplier selected"]
        C2["Ocean freight preferred"]
        C3["Longer delays accepted"]
    end

    style T1 fill:#3498db,color:#fff
    style T2 fill:#3498db,color:#fff
    style T3 fill:#3498db,color:#fff
    style C1 fill:#e74c3c,color:#fff
    style C2 fill:#e74c3c,color:#fff
    style C3 fill:#e74c3c,color:#fff
```

### Zoho API Credentials

Store in Google Colab Secrets (left sidebar, key icon):

```
Key Name                    Value
-------------------------------------------
ZOHO_CLIENT_ID              1000.XXXXXXXXXXXXXXXXXXXX
ZOHO_CLIENT_SECRET          XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
ZOHO_REFRESH_TOKEN          1000.XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
ZOHO_ORG_ID                 XXXXXXXXXX
```

**How to obtain credentials:**

```mermaid
flowchart LR
    A["Go to<br/>api-console.zoho.in"] --> B["Create<br/>Self Client"]
    B --> C["Set Scopes:<br/>items.READ<br/>salesorders.READ<br/>purchaseorders.READ"]
    C --> D["Generate<br/>Refresh Token"]
    D --> E["Copy to<br/>Colab Secrets"]

    style A fill:#e74c3c,color:#fff
    style B fill:#e67e22,color:#fff
    style C fill:#f39c12,color:#fff
    style D fill:#27ae60,color:#fff
    style E fill:#3498db,color:#fff
```

### Monitoring Thresholds

```python
BUFFER_THRESHOLD_DAYS = 10  # Trigger negotiation if buffer < 10 days
```

```mermaid
graph LR
    A["buffer > 30d"] -->|LOW| G["Skip"]
    B["buffer 15-30d"] -->|MEDIUM| Y["Log Warning"]
    C["buffer 5-15d"] -->|HIGH| O["Alert Manager"]
    D["buffer < 5d"] -->|CRITICAL| R["Full Agent Negotiation"]

    style A fill:#27ae60,color:#fff
    style B fill:#f39c12,color:#fff
    style C fill:#e67e22,color:#fff
    style D fill:#e74c3c,color:#fff
    style G fill:#27ae60,color:#fff
    style Y fill:#f39c12,color:#fff
    style O fill:#e67e22,color:#fff
    style R fill:#e74c3c,color:#fff
```

### Connector Selection

```python
# Synthetic data (default, no credentials needed)
connector = SyntheticSCMConnector(suppliers, inventory, models, plants, carriers, demand)

# Live Zoho Inventory (requires API credentials)
connector = ZohoConnector()

# Zoho with real demand and cost data
connector = ZohoConnectorPro(lookback_weeks=12)
```

### Auto-Scan Settings

```python
run_forever(
    connector_factory=lambda: ZohoConnectorPro(),
    interval_minutes=60,
    max_cycles=None,        # None = run indefinitely
    buffer_threshold=10,
    policy={"cost_weight": 1.0, "time_weight": 1.5}
)
```

| Parameter | Default | Description |
|-----------|---------|-------------|
| `connector_factory` | Required | Returns a fresh connector each cycle |
| `interval_minutes` | `60` | Minutes between scan cycles |
| `max_cycles` | `None` | Max cycles (`None` = infinite) |
| `buffer_threshold` | `10` | Days below which negotiation triggers |
| `policy` | Time-sensitive | Weights for triggered negotiations |

### Part-to-Model Mapping

```python
PART_TO_MODELS = {
    "PART_ECU":     ["MODEL_A_SUV", "MODEL_B_SEDAN", "MODEL_C_SUV"],
    "PART_BATTERY": ["MODEL_C_SUV"],
    "PART_SEAT":    ["MODEL_A_SUV", "MODEL_B_SEDAN"],
    "PART_TIRE":    ["MODEL_A_SUV", "MODEL_B_SEDAN"],
}
```

---

## :: Connector Abstraction

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/212284158-e840e285-664b-44d7-b79b-e264b5e54825.gif" width="400" />

</div>

The architectural backbone. Every agent depends only on this interface:

```python
class SCMConnector(ABC):

    @abstractmethod
    def get_suppliers(self, part_id: str) -> pd.DataFrame:
        """All suppliers for a given part."""

    @abstractmethod
    def get_inventory(self, part_id: str, plant_id: str) -> dict:
        """Stock levels: {on_hand, reorder_point, lead_time_days}"""

    @abstractmethod
    def get_avg_weekly_demand(self, model_id: str) -> float:
        """Average weekly demand for a vehicle model."""

    @abstractmethod
    def get_plant_capacity(self, plant_id: str) -> dict:
        """Plant config: {lines, capacity_per_line}"""

    @abstractmethod
    def get_logistics_options(self) -> pd.DataFrame:
        """Available carriers with cost, time, reliability."""
```

```mermaid
graph TB
    NEW["New ERP System<br/>(SAP, Oracle, Custom)"] --> IMPL["Implement 1 Class<br/>5 Methods"]
    IMPL --> DONE["All Agents Work<br/>All Reports Work<br/>All Monitoring Works<br/>ZERO Changes Needed"]

    style NEW fill:#e74c3c,color:#fff
    style IMPL fill:#f39c12,color:#fff
    style DONE fill:#27ae60,color:#fff
```

---

## :: Agents Deep Dive

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/212749447-bfb7e725-6987-49d9-ae85-2015e3e7cc41.gif" width="400" />

</div>

| Agent | Role | Scoring Formula | Output |
|-------|------|----------------|--------|
| **Procurement** | Find alternative suppliers | `reliability * (1-cost_penalty) * capacity_ratio * (1-lead_time_ratio)` | Best supplier + cost delta |
| **Inventory** | Assess buffer coverage | `buffer_days = on_hand / (weekly_demand / 7)` | Days of coverage + risk |
| **Production** | Evaluate rescheduling | `utilization = affected_models / plant_capacity` | Delay estimate + plan |
| **Logistics** | Select shipping mode | `Pick mode fitting buffer window, score speed * reliability` | Mode + cost + transit |
| **Orchestrator** | Negotiate optimal plan | `score = confidence - (cost * w_c/100) - (delay * w_t/10)` | Combined decision + trace |

```mermaid
pie title Agent Confidence Distribution (Wafer Fab Scenario)
    "Procurement (82%)" : 82
    "Inventory (95%)" : 95
    "Production (80%)" : 80
    "Logistics (85%)" : 85
```

---

## :: Performance Metrics

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=16&duration=2000&pause=1000&color=27AE60&center=true&vCenter=true&repeat=true&width=500&lines=Sub-second+graph+traversal;Under+2s+full+pipeline+(synthetic);Under+10s+with+live+Zoho+API" alt="Performance" />

</div>

```mermaid
xychart-beta
    title "Response Time by Component (seconds)"
    x-axis ["Procurement", "Inventory", "Production", "Logistics", "Orchestrator", "Report Gen"]
    y-axis "Time (seconds)" 0 --> 3
    bar [0.3, 0.1, 0.15, 0.12, 0.25, 0.4]
    bar [2.5, 1.8, 0.15, 0.12, 0.25, 0.4]
```

| Metric | Synthetic Data | Live Zoho API |
|--------|---------------|---------------|
| **Knowledge Graph Traversal** | < 1ms | < 1ms |
| **Four-Agent Pipeline** | 0.67s | 4.57s |
| **Orchestrator Negotiation** | 0.25s | 0.25s |
| **Report Generation** | 0.40s | 0.40s |
| **Total End-to-End** | **1.32s** | **5.22s** |
| **Memory per Cycle** | 12 MB | 18 MB |

---

## :: Testing

```
Test Category          Cases    Pass Rate
-------------------------------------------------
Unit Testing             18       100%
Integration Testing      12       100%
Functional Testing       15       100%
Connector Testing         8       100%
Performance Testing       6       100%
Agent Accuracy           10       100%
-------------------------------------------------
Total                    69       100%
```

```mermaid
pie title Test Distribution by Category
    "Unit Tests" : 18
    "Integration Tests" : 12
    "Functional Tests" : 15
    "Connector Tests" : 8
    "Performance Tests" : 6
    "Accuracy Tests" : 10
```

---

## :: Tech Stack Breakdown

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/212257467-871d32b7-e401-42e8-a166-fcfd7baa4c6b.gif" width="80" />

</div>

```mermaid
pie title Technology Distribution
    "Python (Core)" : 30
    "Pandas (Data)" : 20
    "NetworkX (Graph)" : 15
    "NumPy (Compute)" : 10
    "Matplotlib (Viz)" : 10
    "Zoho API (Integration)" : 10
    "IPython (Display)" : 5
```

| Category | Technology | Purpose |
|----------|-----------|---------|
| **Core Language** | Python 3.8+ | Agent logic, orchestration, monitoring |
| **Data Processing** | Pandas 2.0 | DataFrame manipulation, supplier scoring |
| **Graph Engine** | NetworkX 3.0 | Knowledge graph, impact tracing |
| **Numerical** | NumPy 1.24 | Random generation, statistical calculations |
| **Visualization** | Matplotlib 3.7 | Charts, diagrams, report visuals |
| **API Integration** | Requests + OAuth2 | Zoho Inventory REST API |
| **Display** | IPython HTML | Styled report card rendering |
| **Environment** | Google Colab | Cloud notebook execution |
| **Data Classes** | dataclasses | Typed AgentProposal structures |
| **Abstraction** | ABC (Python) | Connector interface pattern |

---

## :: Project Structure

```
automotive_scm_multiagent_v2_fixed.ipynb
|
|-- Section 1-2   DATA LAYER
|   |-- Synthetic data generator (seeded, reproducible)
|   |-- 7 entity types: Suppliers, Parts, Models, Plants, Carriers, Demand, Inventory
|
|-- Section 3     CONNECTOR LAYER
|   |-- SCMConnector (abstract interface)
|   |-- SyntheticSCMConnector | ZohoConnector | ZohoConnectorPro
|
|-- Section 4     KNOWLEDGE GRAPH
|   |-- build_graph() --> NetworkX DiGraph
|   |-- trace_impact() --> affected parts, models, plants
|
|-- Section 5-6   AGENT LAYER
|   |-- ProcurementAgent | InventoryAgent | ProductionAgent | LogisticsAgent
|   |-- Orchestrator (policy-weighted negotiation)
|
|-- Section 7-8   DEMO LAYER
|   |-- Disruption scenario execution
|   |-- Policy comparison (time-sensitive vs cost-sensitive)
|
|-- Section 9-14  INTEGRATION LAYER
|   |-- Zoho OAuth2 authentication + token refresh
|   |-- Live vendor lists + stock levels
|   |-- Real demand from sales orders (ZohoConnectorPro)
|   |-- Real cost from purchase orders (ZohoConnectorPro)
|
|-- Section 15-16 OPERATIONS LAYER
    |-- auto_scan_and_respond() threshold monitoring
    |-- run_forever() continuous loop
    |-- Data quality transparency report
```

---

## :: Future Roadmap

```mermaid
timeline
    title Development Roadmap
    section Phase 1 (Complete)
        Synthetic Data Generator : Done
        4 Agents + Orchestrator : Done
        Knowledge Graph : Done
        Zoho Integration : Done
        Auto-Scan Monitoring : Done
        Policy Comparison : Done
        ZohoConnectorPro : Done
    section Phase 2 (Planned)
        SAP S/4HANA Connector : Planned
        Oracle SCM Connector : Planned
        Web Dashboard (React) : Planned
        ML Agent Scoring : Planned
    section Phase 3 (Future)
        Multi-Disruption Handling : Future
        Mobile Notifications : Future
        Cloud Deployment (24/7) : Future
        Digital Twin Simulation : Future
```

---

<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" width="900" />

<br/><br/>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=14&duration=3000&pause=2000&color=00D4FF&center=true&vCenter=true&repeat=true&width=500&lines=Built+for+resilience.+Designed+for+speed.;Any+ERP.+Same+agents.+Zero+changes.;From+disruption+to+decision+in+seconds." alt="Footer" />

<br/><br/>

**SNS College of Technology, Coimbatore**

<br/>

<img src="https://img.shields.io/badge/Made_with-Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/Powered_by-AI_Agents-FF6F61?style=for-the-badge" />
<img src="https://img.shields.io/badge/Built_at-SNS_College-2c3e50?style=for-the-badge" />

</div>
