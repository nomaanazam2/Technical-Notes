# System Design & Distributed Systems Expert Roadmap

## 📘 Part 1: Fundamentals of System Design

### Chapter 1: Basics of System Design

- What is System Design?
- Types of System Design: High-Level vs Low-Level
- Functional vs Non-Functional Requirements
- Common Interview Questions

### Chapter 2: Scalability Principles

- Vertical vs Horizontal Scaling
- CAP Theorem (Consistency, Availability, Partition Tolerance)
- Latency vs Throughput
- Load Balancing and Redundancy

### Chapter 3: Building Blocks of a Scalable System

- Client, Server, and APIs
- Application Layer, Service Layer, Data Layer
- Monolithic vs Microservices Architecture

---

## 📘 Part 2: Core Components & Concepts

### Chapter 4: Load Balancers

- L4 vs L7 Load Balancing
- Round-robin, Least connections, IP hash
- HAProxy, NGINX, AWS ELB

### Chapter 5: Caching Systems

- Cache Invalidation strategies (Write-through, Write-around)
- CDN (Content Delivery Networks)
- Redis, Memcached

### Chapter 6: Databases

- SQL vs NoSQL
- Relational (PostgreSQL, MySQL) vs Document (MongoDB)
- Indexing, Sharding, Replication
- Query Optimization and Denormalization

### Chapter 7: Message Queues & Pub/Sub

- Event-driven Architecture
- Kafka, RabbitMQ, Amazon SQS
- Asynchronous Processing
- Dead-letter queues

### Chapter 8: API Design & Communication

- REST vs GraphQL
- Rate Limiting, Throttling
- gRPC and Protocol Buffers
- Idempotency & Retry strategies

---

## 📘 Part 3: Advanced Design Patterns

### Chapter 9: Microservices Architecture

- Service Registry & Discovery
- Communication: Sync vs Async
- API Gateway pattern
- Data Management in Microservices (SAGA, CQRS)

### Chapter 10: Database Scaling

- Vertical vs Horizontal Partitioning
- Data Sharding Strategies
- Replication Lag Handling
- Multi-master setups

### Chapter 11: Distributed Systems Basics

- What is a Distributed System?
- Challenges: Clock Skew, Consensus, Failures
- Eventual Consistency
- Consistent Hashing

### Chapter 12: Consensus Algorithms

- Leader Election
- Paxos, Raft
- ZooKeeper internals
- Quorum and Heartbeat mechanisms

### Chapter 13: File Storage & Large Data Systems

- Blob Storage (S3, GCS)
- Distributed File Systems (HDFS, GFS)
- Log Structured Merge Trees
- Data Lakes & Warehouses (Snowflake, BigQuery)

---

## 📘 Part 4: Performance, Reliability, and Monitoring

### Chapter 14: Performance Engineering

- CDN + Caching layers
- Load Testing with Locust, k6, JMeter
- Profiling tools (Perf, Flame graphs)

### Chapter 15: Fault Tolerance & High Availability

- Retry Logic & Circuit Breakers
- Graceful Degradation
- Redundancy, Failover, and Backup strategies

### Chapter 16: Observability & Monitoring

- Logging, Tracing, Metrics
- Prometheus, Grafana
- ELK Stack, Jaeger, OpenTelemetry

---

## 📘 Part 5: Security, DevOps, and Real-World Systems

### Chapter 17: Security Fundamentals

- Authentication vs Authorization
- OAuth2, OpenID Connect, JWT
- SSL/TLS, HTTPS, HSTS
- Rate Limiting, API Keys, IP Whitelisting

### Chapter 18: CI/CD and Infrastructure

- Docker, Kubernetes (K8s)
- GitOps, Helm Charts
- GitHub Actions, Jenkins, ArgoCD
- Canary, Blue-Green Deployments

### Chapter 19: Cloud Architecture

- AWS, GCP, Azure Building Blocks
- S3, Lambda, EC2, VPC, RDS, SQS, CloudWatch
- Cloud-Native Patterns

### Chapter 20: Designing Real Systems (Case Studies)

- Design YouTube / Netflix
- Design WhatsApp / Slack
- Design Uber / Ola
- Design Twitter Feed / Instagram
- Design Scalable Notification System

---

## 📘 Part 6: Practice & Interview Prep

### Chapter 21: System Design Interviews

- Clarifying requirements
- Drawing architecture diagrams
- Estimations and bottleneck identification
- Trade-off decisions

### Chapter 22: Mock Designs & Review

- Sample low-level designs (class diagrams, DB schema)
- Practice whiteboarding
- Review by peers or mentors
