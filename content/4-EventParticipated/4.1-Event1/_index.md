---
title: "Event 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Summary Report: “FCAJ Community Day”

### Event Information

- **Event name:** FCAJ Community Day
- **Date:** June 27, 2026
- **Role:** Attendee

### Event Objectives

- Share practical cloud-computing experience and perspectives from enterprise environments.
- Introduce AI Agent solutions for cloud operations, Vietnamese voice processing, and human-resources workflows.
- Present standard security-architecture methods for integrating AI into internal enterprise systems.
- Create opportunities for the community, students, and Cloud and AI professionals to connect and exchange ideas.

### Speakers

- **Steve Tran** — Founder, Cloud Thinker
- **Hieu Nghi** — Renova Cloud
- **Kiet** — Student Builder Group
- **Trung** — CEO, Re AI
- **Bao and Nguyen** — Cloud Engineers, Cloud Kinetics
- **Truong** — AI Solution, Noventiq
- **Minh Anh** — Solution Sales, Noventiq
- **Toan Nguyen** — AWS Security Builder

### Key Highlights

#### Applying AI Agents to Cloud Operations

- Increasingly complex microservice systems make manual operations time-consuming, expensive, and difficult to scale.
- AI Agents can help DevOps engineers investigate incidents, inspect source code, optimize FinOps costs, and automate security assessments and penetration testing.
- AI acts as an analytical and recommendation assistant, helping technical teams work faster and more systematically.

#### Building Voice AI specialized for Vietnamese

- Traditional Speech-to-Speech models remain limited for low-resource languages such as Vietnamese.
- The architecture is divided into three stages: **STT (Speech-to-Text) → LLM (Large Language Model) → TTS (Text-to-Speech)**, enabling better content control and reducing hallucinations.
- Tool Calling, context and gender recognition, and interruption detection help the system produce more natural responses.

#### Optimizing incident response with AWS DevOps Agent

- AWS DevOps Agent helps address **Fragmented Telemetry**, where logs and traces are scattered across multiple sources.
- Its automated workflow has four stages: **Classify information → Investigate the root cause → Recommend remediation → Improve the system**.
- The **human-in-the-loop** model remains essential: AI makes recommendations, while people review and decide whether to act.

#### Digitizing human-resources workflows with Amazon Q

- Manual CV screening is susceptible to subjective judgment and may overlook suitable candidates.
- Amazon Q can understand job descriptions, extract information from CVs—including PDFs and scanned images—and then compare and score candidates more objectively.
- The solution reduces repetitive work for HR teams and gives them more time for in-depth evaluation.

#### Establishing a secure architecture for Amazon Q

- Public endpoints can increase the risk of DDoS attacks, eavesdropping, or data leakage in transit.
- A secure connection flow uses a **VPC Connection, Private Subnet, and Application Load Balancer (ALB)** to protect internal data.
- Access permissions and private connectivity must be designed from the beginning when enterprises integrate AI into production environments.

### What I Learned

#### Design Mindset

- **Human-in-the-loop:** AI supports and amplifies human capability rather than fully replacing skilled engineers.
- **Business-first approach:** AI tools and technology workflows must begin with real business problems and needs.
- AI adoption requires clear review mechanisms, authorization, and decision-making responsibility.

#### Technical Architecture

- I learned how to separate STT, LLM, and TTS modules to recognize and respond to Vietnamese speech.
- I understood how VPCs, Private Subnets, and ALBs can create a closed network environment for AI systems and MCP servers.
- I gained a clearer understanding of the role of logs, metrics, traces, and observability in AI-assisted incident investigation.

#### AI Adoption Strategy

- AI is well suited to repetitive tasks such as reading CVs, summarizing error logs, and assisting with root-cause analysis.
- Automation gives employees more time for strategic work and decision-making.
- Effective AI adoption requires sufficiently mature infrastructure, especially in observability and operational data.

### Applying It to My Work

- **Experiment with AWS DevOps Agent:** Integrate it into the project to help reduce MTTR (Mean Time To Recovery) during incidents.
- **Integrate GenAI into business workflows:** Use Amazon Q Developer or AI Agents to help non-technical departments such as HR and Administration analyze data.
- **Improve security:** Review API connections to third-party AI services and prioritize private connections to strengthen information security.
- **Maintain human-in-the-loop controls:** Require human review before actions that affect the production environment.

### Event Experience

Attending **FCAJ Community Day** was a practical and in-depth experience. It helped me stay current with AI Agent trends on AWS and better understand how enterprises apply these technologies.

#### Learning from experienced practitioners

- Talks by founders, CEOs, cloud engineers, and security builders provided diverse perspectives ranging from startups to large enterprises.
- The sessions did more than introduce technology; they analyzed real operational, human-resources, and security challenges.

#### Visual technical experience

- Live demonstrations—including a responsive Voice Bot, AI-assisted system troubleshooting, and AI-based CV analysis—made the workflows easy to understand.
- Practical examples showed how AI Agents can combine analytical capabilities with Tool Calling to support real tasks.

#### Networking and Q&A

- The event offered direct discussions with speakers about regional accents, Data Transfer costs, and practical deployment challenges.
- Questions and feedback helped clarify the gap between a technical demo and a production system.

#### Lessons Learned

- AI is evolving from standalone chatbots into Agent ecosystems that can analyze information and invoke tools to perform tasks.
- Data Security and Observability are two essential foundations for integrating AI into enterprise operations.
- New technology must include Role-Based Access Control, review mechanisms, and clearly defined action limits.
- AI delivers the greatest value when it helps people make faster, more accurate, data-informed decisions.

> Overall, FCAJ Community Day expanded my knowledge of Cloud, AI Agents, Voice AI, DevOps automation, and security architecture on AWS while giving me clearer direction for applying these technologies to real projects.
