# Assignment 2 8916

## Executive Summary

This report provides a comprehensive comparison of **AWS**, **Microsoft Azure** and **Google Cloud Platform** with a focus on their cloud services supporting remote data access and real time applications. The analysis covers key areas like **RESTful API services**, **GraphQL support**, **WebSocket capabilities**, **data streaming**, and **stream analytics**, drawing from official documentation, market analyses and comparative studies as of 2025.

Aws emerges as the market leader with approximately **30 percent** of global cloud market share offering the broadest and most mature set of services for real time and data intensive workloads. Its strengths lie in scalability, extensive integrations and cost effectiveness for high volume operations.

Azure, holding about **20 to 23 percent** of the market share, excels in enterprise integration, particularly for organizations using Microsoft ecosystems with strong hybrid cloud support and user friendly tools for real time messaging.

GCP with **12–13 percent** market share stands out in data analytics and AI/ML, providing efficient, cost optimized solutions for streaming and processing large datasets though it sometimes lags in native support for certain API paradigms.

AWS provides native fully managed services across all categories making it ideal for diverse real time applications; Azure offers seamless integration for .NET developers and robust analytics; GCP emphasises open source compatibility and efficiency but relies more on third party tools for GraphQL and WebSockets. Pricing varies by usage with AWS and GCP often more predictable for scaling while Azure tailored model suits enterprise needs.

---

## Introduction

### Purpose and Scope

The purpose of this comparison is to evaluate the three platforms in the context of cloud services that enable remote data handling and real time applications. The scope is limited to these providers offering **RESTFUL APIs**, **GraphQL**, **WebSockets**, **data streaming**, **stream analytics** and much more.

---

## Overview of the Three Providers

### AWS
Launched in 2006 AWS is the dominant cloud provider with a vast ecosystem of over 200 services and leads in market share, due to its reliability, global reach and innovation in serverless tech. Its strengths include scalability and pay as you go model which is suited for startups and enterprises.

### Azure
Microsoft cloud platform was introduced in 2010 and holds 20–23 percent of the market share and integrates with Windows seamlessly through the products already in the ecosystems. It emphasizes hybrid cloud solutions, AI, developer tools, with strong presence in enterprise sectors like finance and healthcare.

### GCP
Google’s offering since 2008, GCP commands 12–13 percent of the market share and leverages Google’s expertise in data and AI. It focuses on open source tools, sustainability and cost efficiency appealing to data scientists and organizations prioritizing analytics and machine learning.

---

## Service Comparison

### RESTFUL API Services

This section compares the API gateway and management services for building, deployment and managing RESTFUL APIs including for traffic management, security and analytics along with pricing models.


| Feature | AWS (API Gateway) | Azure (API Management) | GCP (API Gateway / Apigee) |
|---------|-------------------|------------------------|---------------------------|
| Core Services | Fully managed service for REST, HTTP, and WebSocket APIs; supports serverless integrations with Lambda. | Comprehensive API management with developer portals, policies, and analytics. | API Gateway for serverless APIs; Apigee for advanced management, analytics, and monetization. |
| Management Tools | Caching, throttling, usage plans, monitoring via CloudWatch; SDKs for multiple languages. | Subscription keys, OAuth, rate limiting, transformation policies; integrates with Azure Monitor. | Traffic routing, quota enforcement, developer portals (Apigee); integrates with Cloud Monitoring. |
| Scalability Features | Auto-scales to millions of requests; edge-optimized endpoints for low latency. | Scales via tiers; premium supports multi-region deployment. | Serverless scaling; Apigee handles enterprise-scale with hybrid options. |
| Pricing Model | Pay-per-use: $3.50 per million API calls + $0.09/GB data transfer; caching extra. Free tier available. | Tiered:<br>Consumption (~$0.191/10,000 calls), Developer (free for testing), Standard (~$700/month), Premium (~$4,000/month). | API Gateway: $3 per million calls.<br>Apigee: Subscription-based starting at ~$2,795/unit/month; usage-based options. |

### GraphQL Services

GraphQL enables efficient and flexible data querying for remote applications. This compares native support and integration options.

| Feature | AWS (AppSync) | Azure | GCP |
|---------|---------------|-------|-----|
| Native Support | Fully native with AppSync: serverless GraphQL APIs, real-time subscriptions via WebSockets. | No dedicated native service; limited GraphQL in Cosmos DB for specific data models. | No native GraphQL service. |
| Key Features | Data sources (DynamoDB, Lambda, RDS); caching, offline support; integrates with Amplify. | Use Azure Functions or App Service for custom GraphQL; real-time via SignalR. | Run GraphQL servers on Compute Engine, Cloud Run, or GKE. |
| Third-Party Integration | Built-in resolvers; supports Apollo, Hasura via integrations. | Strong with Apollo Server, Hasura (on Azure VMs or Kubernetes); Cosmos DB API for GraphQL queries. | Compatible with Apollo, Hasura on GKE; Firebase for real-time if needed. |
| Scalability & Pricing | Auto-scales; $4 per million queries + $0.08 per million real-time updates. | Depends on underlying service (e.g., Functions: $0.20/million executions). | Pay for compute resources; e.g., Cloud Run: $0.000024/GB-second. |

### Data Streaming Services

These platforms handle ingestion and processing of real time data streams from sources like sensors or logs.

| Feature | AWS (Kinesis Data Streams) | Azure (Event Hubs) | GCP (Pub/Sub) |
|---------|---------------------------|-------------------|---------------|
| Stream Processing | Shard-based streaming; supports SQL/Flink processing. | Partitioned event streaming; integrates with Stream Analytics. | Topic-based pub/sub; at-least-once delivery. |
| Data Ingestion | High throughput (1MB/sec/shard); durable storage up to 365 days. | Up to 1MB/sec/partition; capture to storage; geo-replication. | Global, low-latency ingestion; data retention up to 7 days. |
| Scalability Features | Auto-sharding; on-demand mode. | Auto-inflate; up to 20 throughput units. | Auto-scales to petabytes; push/pull subscriptions. |
| Pricing Model | $0.011/shard-hour + $0.015 per million PUTs. | $0.028/throughput unit-hour + $0.015/million events. | $0.40/million messages + data volume fees. |

### Stream Analytics

Platforms for real time processing and analysis of streaming data often using SQL or code based queries.

| Feature | AWS (Kinesis Data Analytics) | Azure (Stream Analytics) | GCP (Dataflow) |
|---------|------------------------------|--------------------------|----------------|
| Core Platforms | SQL or Apache Flink for stream processing; anomaly detection. | SQL-based queries; windowing, ML integration. | Apache Beam SDK; unified batch/stream processing. |
| Key Capabilities | Processes from Kinesis/Firehose; outputs to S3, Lambda. | Integrates with Event Hubs, IoT Hub; outputs to Power BI, Cosmos DB. | Autoscaling runners; integrates with Pub/Sub, BigQuery. |
| Scalability Features | Elastic scaling with KPUs; serverless Flink. | Streaming units scale on-demand; geo-distributed. | Horizontal autoscaling; no server management. |
| Pricing Model | $0.11/KPU-hour + running application fees. | $0.11/streaming unit-hour + output fees. | $0.0576/vCPU-hour + shuffle/storage fees. |

## Use Case Analysis

### Scenario 1: Real Time IoT Monitoring Smart Manufacturing

In smart manufacturing, companies like Siemens and General Electric deploy IoT sensors to monitor machinery in real time, detecting anomalies to prevent downtimes. Data from thousands of sensors streams continuously requiring low latency ingestion, processing and analytics for predictive maintenance (ProjectPro, 2025).

**Recommended CSP: Azure.** The IoT Hub integrates seamlessly with Event Hubs and Stream Analytics for real time data ingestion and SQL based querying enabling quick anomaly detection with built in ML. Performance is strong for hybrid set ups common in manufacturing. Ease of integration shines for Microsoft centric enterprises with tools like Power BI available for visualization. Cost is competitive with tiered pricing potentially lower for moderate scales compared to AWS's shard-based model. GCP could work but lacks native IoT depth; AWS is viable but Azure's ecosystem edges it for Windows/IoT integrations (Intelgain, 2025).

### Scenario 2: Real Time Analytics for Live Streaming Media

Media companies like Netflix or Disney+ use real time analytics to personalize content recommendations and monitor viewer engagement during live events, processing streaming data for immediate insights (AWS, 2025).

**Recommended CSP: AWS.** Kinesis suite handles high throughput data streaming with durable storage integrating with Data Analytics for Flink based processing. Performance excels in global scalability supporting millions of viewers with low latency. Ease of integration is high via serverless Lambda and broad ecosystems. Cost is pay per use and efficient for bursty live events versus Azure's fixed tiers or GCP message based fees. GCP Pub/Sub and Dataflow are strong for AI driven recommendations but less mature for media specific tools. Azure suits but AWS dominates in the entertainment streaming (Dev, 2025).

---

## Conclusion

In summary, the three each offer robust services for remote data and real time applications, with AWS leading in breadth and maturity, Azure in enterprise integration and GCP in AI analytics efficiency. Key findings highlight AWS native support across categories, Azure user friendly real time tools and GCP cost optimized streaming. For use cases, Azure suits IoT heavy scenarios like manufacturing, while AWS excels in media streaming. Overall recommendations include: select based on ecosystem alignment, a Microsoft shop should lean Azure, data/AI focused opt GCP and general scalability favor AWS. Future evaluations should monitor evolving AI integrations and pricing.

## Refernces
Real-World AWS Use Cases: How Top Industries Are Powering Innovation. https://dev.to/cloud_man/real-world-aws-use-cases-how-top-industries-are-powering-innovation-with-the-cloud-5bgg

30+ Real-Time Azure Project Ideas for Beginners to Practice [2025]. https://www.projectpro.io/article/microsoft-azure-projects-ideas-for-beginners-for-learning/507

6 Ways Azure AI Transforms Enterprise Workflows (2025). https://www.intelegain.com/6-practical-ways-azure-ai-can-revolutionize-your-enterprise-workflows/

Uses Of AWS In 2025. https://builder.aws.com/content/2skYDVpQfoeCGV08dMTM9P2iKaL/uses-of-aws-in-2025

## AI USE
i used ai to make the table 
ai was used to do markdown format

no word content was copied from any AI, the words and sentences are my own as Trevor Kutto 
