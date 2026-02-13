# Architecture Diagram
                          ┌──────────────────────────────┐
                          │     User in Discord Server    │
                          │    │
                          └───────────────┬──────────────┘
                                          │
                                          ▼
                     ┌────────────────────────────────────────┐
                     │    QA-Agent-Bot (Discord Bot)       │
                     │  Command Parser + Intent Detection      │
                     └───────────────┬────────────────────────┘
                                     │
                                     ▼
                     ┌────────────────────────────────────────┐
                     │      Fraud Test Case Generator          │
                     │  • Velocity anomalies                   │
                     │  • Geolocation mismatch                 │
                     │  • Device fingerprint mismatch          │
                     │  • Mule account pattern                 │
                     │  • Behavioral anomaly                   │
                     │  • ATO indicators                       │
                     └───────────────┬────────────────────────┘
                                     │
                                     ▼
                     ┌────────────────────────────────────────┐
                     │   Session Test Case Store (In‑Memory)   │
                     │  Stores generated test cases per user   │
                     └───────────────┬────────────────────────┘
                                     │
                                     ▼
                     ┌────────────────────────────────────────┐
                     │        Fraud Test Executor              │
                     │  • Simulated PASS/FAIL outcomes         │
                     │  • Weighted randomness (fraud edge)     │
                     │  • Logs execution results               │
                     └───────────────┬────────────────────────┘
                                     │
                                     ▼
                     ┌────────────────────────────────────────┐
                     │   Session Execution Results Store       │
                     │  Stores PASS/FAIL outcomes per user     │
                     └───────────────┬────────────────────────┘
                                     │
                                     ▼
                     ┌────────────────────────────────────────┐
                     │       Fraud QA Report Builder           │
                     │  • Total tests                          │
                     │  • Pass/Fail summary                    │
                     │  • Detailed fraud scenario analysis     │
                     │  • Expected vs. actual behavior         │
                     └───────────────┬────────────────────────┘
                                     │
                                     ▼
                          ┌──────────────────────────────┐
                          │   Response Back to Discord    │
                          │  (Report, Scores, Insights)   │
                          └──────────────────────────────┘
