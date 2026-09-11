# PlantUML Architecture Assets

A collection of clean, modern, and production-ready **PlantUML architecture diagrams** covering modern cloud, distributed systems, security, and AI infrastructure patterns.

---

## 📂 Included Diagrams

| File | Domain | Architecture Pattern & Key Components |
| :--- | :--- | :--- |
| **[`event-driven-cqrs-microservices.puml`](./event-driven-cqrs-microservices.puml)** | Microservices & Distributed Systems | **Event-Driven CQRS & Transactional Outbox**<br>• Write path with ACID Transactional Outbox + Debezium CDC<br>• Kafka/Redpanda event streaming backbone with Schema Registry<br>• Read path with Elasticsearch, Redis, and Read Replica projections |
| **[`zero-trust-kubernetes-mesh.puml`](./zero-trust-kubernetes-mesh.puml)** | Cloud Security, DevOps & SRE | **Zero-Trust Multi-Tier Service Mesh on K8s**<br>• Edge WAF/DDoS protection & Istio Ingress Gateway with OIDC<br>• Strict mTLS & SPIFFE/SPIRE workload identities per pod<br>• HashiCorp Vault dynamic secrets, ArgoCD GitOps, OPA Gatekeeper |
| **[`llm-rag-agentic-pipeline.puml`](./llm-rag-agentic-pipeline.puml)** | Generative AI & Cloud Data | **Enterprise LLM RAG & Agentic Tool Execution**<br>• Guardrails (Prompt injection, PII masking, Hallucination checks)<br>• Semantic Caching (Redis/LangCache) & Hybrid Retrieval (Vector + BM25)<br>• Re-ranking, ReAct Agentic tool orchestration, and LLMOps tracing |

---

## 🛠️ How to Render and Use

### 1. In Visual Studio Code / Antigravity IDE
- Install the **PlantUML** extension (`jebbs.plantuml`).
- Open any `.puml` file and press `Alt + D` (or `Option + D` on macOS) to preview live.
- Right-click and choose **Export Current Diagram** to export to PNG, SVG, or PDF.

### 2. In Diagrams.net / Draw.io
- Open [draw.io](https://app.diagrams.net/).
- Navigate to: **Arrange > Insert > Advanced > PlantUML...**
- Paste the contents of any `.puml` file to generate an editable vector diagram.

### 3. Using PlantUML CLI / Docker
```bash
# Render to SVG using PlantUML JAR
plantuml -tsvg event-driven-cqrs-microservices.puml

# Or using Docker
docker run --rm -v $(pwd):/data plantuml/plantuml -tsvg *.puml
```

### 4. Online Live Preview
- Paste code into [PlantText](https://www.planttext.com/) or the official [PlantUML Web Server](https://www.plantuml.com/plantuml/uml/).
