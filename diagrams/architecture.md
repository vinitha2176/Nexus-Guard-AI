```meermaid
flowchart TD
A[Alert Received] --> B[Orchestrator]
B --> C1[Auth Log Analyzer]
B --> C2[App Log Analyzer]
B --> C3[Deployment Analyzer]
C1 --> D[Correlation Engine]
C2 --> D
C3 --> D
D --> E[Risk Scorer]
E --> F[Risk Level]
F -->|Low| G[Log & Close]
F -->|Medium| H[Analyst Review]
F -->|High| I[Human Approval -> Lockdown]
I --> J[Incident Memory Log]
```