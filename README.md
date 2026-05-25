# Monitoring

In SRE/DevOps, metrics are tightly tied to system reliability, performance, and user experience. They’re usually categorized around SLIs, SLOs, and SLAs, but there are several types you should know for interviews:

📊 Core Types of Metrics in SRE/DevOps
1. Golden Signals (Google SRE model)
These are the four most critical metrics to monitor:

Latency → Response time of requests (e.g., API call duration).

Traffic → Demand on the system (e.g., requests per second).

Errors → Failed requests (e.g., HTTP 5xx rates).

Saturation → Resource usage (CPU, memory, disk, network).

👉 These are the foundation of observability.

2. SLI / SLO / SLA Metrics
SLI (Service Level Indicator) → Actual measured value (e.g., 99.95% uptime, 200ms latency).

SLO (Service Level Objective) → Target threshold (e.g., 99.9% availability).

SLA (Service Level Agreement) → Contractual commitment with penalties if breached.

👉 SLIs are the raw data, SLOs are the goals, SLAs are the promises.

3. Error Budget Metrics
Error Budget Consumption → How much unreliability is acceptable before breaching SLO.

Example: If SLO is 99.9% uptime, error budget = 0.1% downtime allowed.

👉 Balances reliability vs. velocity (deployments, changes).

4. Infrastructure & Resource Metrics
CPU / Memory / Disk / Network utilization.

Pod health in Kubernetes (ready/unready states).

Container restart counts.

Node saturation.

👉 These help with capacity planning and troubleshooting.

5. Application Metrics
Request throughput (RPS/QPS).

Error rates (exceptions, failed transactions).

Queue length / backlog.

Cache hit/miss ratio.

👉 Directly tied to user experience and system efficiency.

6. Business & User-Centric Metrics
Conversion rate (successful transactions).

Abandonment rate (users dropping off).

Feature adoption.

👉 These connect system reliability to business outcomes.

| Metric Type | Examples | Purpose |
| --- | --- | --- |
| Golden Signals | Latency, Traffic, Errors, Saturation | Core system health |
| SLI/SLO/SLA | Availability %, latency targets | Reliability commitments |
| Error Budgets | Downtime allowance, breach tracking | Balance reliability vs. velocity |
| Infra Metrics | CPU, memory, pod restarts | Resource & infra health |
| App Metrics | RPS, error rates, cache hits | Application performance |
| Business Metrics | Conversion, churn, adoption | User & business impact |


💡 Interview Tip
When asked about metrics, always anchor your answer in Golden Signals + SLIs/SLOs/Error Budgets. Then expand into infra/app/business metrics depending on the scenario. For example:

“If latency spikes, I’d check saturation (CPU/memory), error rates, and traffic volume. If it breaches the SLO, I’d calculate error budget consumption and decide whether to halt deployments.”
