# AIOps Design for Gen AI Projects at Novo Nordisk 

## 1. Introduction & Purpose (Non-Technical)

* **What is AIOps?** A framework for bringing automation, consistency, and visibility to AI applications
* **Why does Novo Nordisk  Nordisk need it?** To standardize development approaches across projects like QCP and CMC
* **Business Value:**
  - Faster development cycles with standardized tools
  - Higher quality AI solutions through consistent evaluation
  - Lower maintenance costs through automation
  - Better visibility into AI application performance

```mermaid
flowchart TD
    subgraph "AIOps Framework"
        direction TB
        Dev[Developer Experience] --> |Build| Flow[Flow Development]
        Flow --> |Test| Eval[Evaluation]
        Eval --> |Deploy| Prod[Production]
        Prod --> |Monitor| Insights[Insights & Analytics]
        Insights --> |Improve| Flow
        
        
        Dev -.-> Core[Core Capabilities]
        Flow -.-> Core
        Eval -.-> Core
        Prod -.-> Core
        Insights -.-> Core
        
        
    end
    
    QCP[Use-Case 1] --> Dev
    CMC[Use-Case 2] --> Dev
    
    classDef primary fill:#4287f5,stroke:#0066cc,color:white
    classDef secondary fill:#f5a742,stroke:#cc8c00,color:white
    classDef project fill:#42f59e,stroke:#00cc88,color:black
    
    class Dev,Flow,Eval,Prod,Insights primary
    class Auto,Stand,Gov,Obs secondary
    class QCP,CMC project
```
```mermaid
    flowchart TD
        subgraph "Core Capabilities"
            direction LR
            Auto[Automation] --- Stand[Standardization]
            Stand --- Gov[Governance]
            Gov --- Obs[Observability]
        end
    classDef primary fill:#4287f5,stroke:#0066cc,color:white
    classDef secondary fill:#f5a742,stroke:#cc8c00,color:white
    classDef project fill:#42f59e,stroke:#00cc88,color:black
    class Auto,Stand,Gov,Obs secondary
```

## 2. Current AIOps Scope (What's In vs. Out)

**In Current Phase:**
* Prompt Flow orchestration (experiment, evaluate, deploy)
* CI/CD pipelines for automated testing and deployment
* Monitoring & alerting for deployed flows
* DataOps for preparing and registering data assets

**Not In Current Phase:**
* Model training and fine-tuning
* Custom RAG implementations beyond template
```mermaid
flowchart TB
  subgraph "Current Phase"
    direction TB
    
    subgraph "In Current Phase - Prompt Flow Orchestration"
      direction TB
      A["<span style='font-size:22px;'>Prompt Flow Orchestration</span>"] --> A1["<span style='font-size:20px;'>Experiment</span>"]
      A --> A2["<span style='font-size:20px;'>Evaluate</span>"]
      A --> A3["<span style='font-size:20px;'>Deploy</span>"]
    end

    subgraph "In Current Phase - CI/CD Pipelines"
      direction TB
      B["<span style='font-size:22px;'>CI/CD Pipelines</span>"] --> B1["<span style='font-size:20px;'>PR Validation</span>"]
      B --> B2["<span style='font-size:20px;'>Full CI Pipeline</span>"]
      B --> B3["<span style='font-size:20px;'>Deployment Automation</span>"]
    end

    subgraph "In Current Phase - Monitoring & Alerting"
      direction TB
      C["<span style='font-size:22px;'>Monitoring & Alerting</span>"] --> C1["<span style='font-size:20px;'>Performance Metrics</span>"]
      C --> C2["<span style='font-size:20px;'>Usage Tracking</span>"]
      C --> C3["<span style='font-size:20px;'>Error Detection</span>"]
    end

    subgraph "In Current Phase - DataOps"
      direction TB
      D["<span style='font-size:22px;'>DataOps</span>"] --> D1["<span style='font-size:20px;'>Data Preparation</span>"]
      D --> D2["<span style='font-size:20px;'>Asset Registration</span>"]
      D --> D3["<span style='font-size:20px;'>Dataset Management</span>"]
    end
  end

  classDef current fill:#ececff,stroke:#9999ff, color:#333
  classDef element fill:#ffffff,stroke:#6666cc, color:#000000
  classDef wrapper fill:#f5f5f5,stroke:#333333,stroke-width:1px,color:#333
  
  class A1,A2,A3,B1,B2,B3,C1,C2,C3,D1,D2,D3 element
  class A,B,C,D current
  class Current_Phase wrapper
```

```mermaid
flowchart LR
  subgraph "Future Phases"
    E[Model Training & Fine-tuning]:::future
    F[Custom RAG Implementations]:::future
    G[Databricks Connectors]:::future
    E --> E1[Fine-tuning Workflows]:::future
    E --> E2[Model Evaluation]:::future
    F --> F1[Advanced RAG Patterns]:::future
    F --> F2[Complex Retrieval]:::future
    G --> G1[Data Integration]:::future
    G --> G2[Lakehouse Connectors]:::future
  end
  
  classDef future fill:#ececff,stroke:#9999ff,stroke-width:2px,color:#333,stroke-dasharray: 5 5
```

## 3. Ongoing Gen AI Projects & How AIOps Fits

**Quality Control Platform (QCP):**
* **Current State:** Development stage with manual data processing
* **Business Purpose:** Streamline quality control report generation
* **How AIOps Helps:**
  - Standardized prompt flows for consistent report generation
  - Automated testing with golden datasets
  - Reliable deployment pipeline via Azure DevOps
  - Performance monitoring and alerting

**Content Management & Compliance (CMC):**
* **Current State:** Implementation phase, RAG-based approach
* **Business Purpose:** Find relevant documents and generate summaries
* **How AIOps Helps:**
  - Ready-to-use RAG flow templates
  - Secure deployment within Novo Nordisk  Nordisk network
  - Integration patterns for Azure AI Search
  - Configurable data pipelines

```mermaid
flowchart TD
    subgraph "AIOps Framework"
        direction TB
        Template["Flow Templates & Patterns"]
        Pipeline["CI/CD Pipeline"]
        Eval["Evaluation Framework"]
        Monitor["Monitoring & Alerts"]
        DataOps["Data Management"]
    end
    
    subgraph "QCP Use Case"
        QCP_Data["Quality Data\n(Bacteria samples, readings)"]
        QCP_Flow["Report Generation\nPrompt Flow"]
        QCP_Deploy["Azure ML\nManaged Endpoints"]
        QCP_UI["Web Interface"]
    end
    
    subgraph "CMC Use Case"
        CMC_Data["Documents\n(Q&A Archive)"]
        CMC_Search["Azure AI Search"]
        CMC_Flow["Document Retrieval\nRAG Flow"]
        CMC_Deploy["Secure Deployment\n(V-net, Novo Nordisk  Nordisk Corp)"]
    end
    
    %% Connections from AIOps to QCP
    Template -->|"Standardized patterns"| QCP_Flow
    Pipeline -->|"Automated deployment"| QCP_Deploy
    Eval -->|"Testing with golden datasets"| QCP_Flow
    Monitor -->|"Performance tracking"| QCP_Deploy
    
    %% Connections from AIOps to CMC
    Template -->|"RAG templates"| CMC_Flow
    Pipeline -->|"Secure deployment"| CMC_Deploy
    DataOps -->|"Integration patterns"| CMC_Search
    Monitor -->|"Usage analytics"| CMC_Deploy
    
    %% QCP internal flow
    QCP_Data -->|"Input"| QCP_Flow
    QCP_Flow -->|"Deploy"| QCP_Deploy
    QCP_Deploy -->|"Serve"| QCP_UI
    
    %% CMC internal flow
    CMC_Data -->|"Index"| CMC_Search
    CMC_Search -->|"Retrieve"| CMC_Flow
    CMC_Flow -->|"Deploy"| CMC_Deploy
    
    classDef aiops fill:#4287f5,stroke:#0066cc,color:white
    classDef qcp fill:#f542a7,stroke:#cc0066,color:white
    classDef cmc fill:#42f59e,stroke:#00cc88,color:black
    
    class Template,Pipeline,Eval,Monitor,DataOps aiops
    class QCP_Data,QCP_Flow,QCP_Deploy,QCP_UI qcp
    class CMC_Data,CMC_Search,CMC_Flow,CMC_Deploy cmc
```

## 4. AIOps High-Level Workflow (Simplified)

1. **Development:** Create and test prompt flows locally
2. **Quality Control:** Automated PR checks for code quality
3. **Deployment Pipeline:** 
   - Test flows against multiple datasets
   - Generate performance reports
   - Deploy to chosen target (Azure ML, Web Apps)
4. **Monitoring:** Track performance metrics and usage patterns

```mermaid
flowchart LR
    subgraph "Development"
        Dev1[Create Flow] --> Dev2[Local Testing]
        Dev2 --> Dev3[Git Push]
    end
    
    subgraph "Quality Control"
        QC1[PR Created] --> QC2[Automated Tests]
        QC2 --> QC3[Code Review]
        QC3 --> QC4[Merge to Main]
    end
    
    subgraph "Deployment Pipeline"
        DP1[Full Dataset Tests] --> DP2[Evaluation]
        DP2 --> DP3[Report Generation]
        DP3 --> DP4[Deployment]
    end
    
    subgraph "Monitoring"
        M1[Performance Tracking] --> M2[Usage Analytics]
        M2 --> M3[Alerting]
        M3 --> M4[Continuous Improvement]
    end
    
    Dev3 ==> QC1
    QC4 ==> DP1
    DP4 ==> M1
    M4 -.-> |Feedback| Dev1
    
    classDef dev fill:#42adf5,stroke:#0066cc,color:white
    classDef qc fill:#f5a742,stroke:#cc8c00,color:white
    classDef dp fill:#f542a7,stroke:#cc0066,color:white
    classDef mon fill:#42f59e,stroke:#00cc88,color:black
    
    class Dev1,Dev2,Dev3 dev
    class QC1,QC2,QC3,QC4 qc
    class DP1,DP2,DP3,DP4 dp
    class M1,M2,M3,M4 mon
```

## 5. Implementation Roadmap & Next Steps

**Immediate Actions (Next 30 Days):**
* Complete AIOps pipeline setup for QCP use case
* Define standard metrics for flow evaluation
* Develop basic monitoring dashboards

**Medium-Term (60-90 Days):**
* Extend AIOps framework to CMC use case
* Implement enhanced security controls
* Create documentation and training materials

**Future Enhancements:**
* Databricks connectors for improved data integration
* Specialized RAG evaluation metrics
* Fine-tuning workflow support

```mermaid
gantt
    title AIOps Implementation Roadmap
    dateFormat  YYYY-MM-DD
    axisFormat %b %d
    
    section QCP Implementation
    Pipeline Configuration     :qcp1, 2025-05-15, 14d
    Evaluation Metrics         :qcp2, after qcp1, 10d
    Monitoring Setup           :qcp3, after qcp2, 7d
    
    section CMC Implementation
    Flow Templates             :cmc1, 2025-06-15, 14d
    Security Controls          :cmc2, after cmc1, 10d
    RAG Integration            :cmc3, after cmc2, 7d
    
    section Documentation & Training
    Developer Guidelines       :doc1, 2025-06-20, 10d
    Admin Documentation        :doc2, after doc1, 7d
    Training Sessions          :doc3, after doc2, 14d
    
    section Future Enhancements
    Databricks Connectors      :fut1, 2025-08-01, 30d
    RAG Evaluation Framework   :fut2, 2025-08-15, 30d
    Fine-tuning Support        :fut3, 2025-09-01, 45d
```

## 6. Discussion & Q&A

* How does this align with your team's current development approach?
* What specific challenges would you like AIOps to address?
* What metrics would be most valuable for your use cases?