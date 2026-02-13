# Architecture Diagram

                   +-----------------------------+
                   |   Discord User              |
                   +--------------+--------------+
                                  |
                                  v
                   +-----------------------------+
                   |   Discord Bot (Python)      |
                   |  - Command Handler          |
                   |  - Evaluation Logic         |
                   +--------------+--------------+
                                  |
                                  v
                   +-----------------------------+
                   |   Agentic QA Functions      |
                   |  - Test Case Generator      |
                   |  - Hallucination Checker    |
                   |  - Compliance Evaluator     |
                   |  - QA Report Builder        |
                   +--------------+--------------+
                                  |
                                  v
                   +-----------------------------+
                   |   Discord Server Channel    |
                   +-----------------------------+
