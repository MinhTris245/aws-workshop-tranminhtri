---
title: "Event 3"
date: 2026-07-25
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Summary Report: “Agentic AI Buildweek 2026”

### Event Information

- **Date:** Saturday, July 25, 2026 (continuing after a 24-hour Hackathon)
- **Location:** Ho Chi Minh City
- **Organizers:** AWS, JI Investment Fund, and the FCAJ Community (AWS Study Group)
- **Role:** Attendee

### Event Objectives

- Provide a hands-on Hackathon environment where participants build and present Agentic AI products on AWS.
- Connect students, engineers, and the technology community through demos, expert feedback, and practical knowledge sharing.
- Promote product development based on real problems, user value, and deployment feasibility.

### Speakers

#### Mr. Nguyễn Gia Hưng – Head of Solution Architect, AWS Vietnam

- Joined as a special guest and judge, directly scoring teams and asking in-depth questions about their cloud architectures.
- Presented certificates and took commemorative photographs with the winning teams.

#### Mr. Joseph Marazota – Head of Technology, AWS ASEAN

- **Opening and inspiration:** Reflected on 20 years in technology—from quarterly software releases to today's AI Agents that can deploy software every minute.
- **Innovation mindset:** Encouraged young developers not to be constrained by ideas inherited from 20 years ago, but to challenge traditional perspectives with a new mental model.
- **Technology at Amazon:** Shared that Amazon operates more than one million robots in its fulfillment centers. Robots and software are only raw machinery; data, Agents, and people acting as Human-in-the-loop create value and continuous improvement.
- **Message:** Encouraged Vietnam's younger generation to become lifelong learners, master technology, and help build the technological future of Vietnam and the region.

### Key Highlights

The program centered on product pitches, live demonstrations, and questions from the judging panel for five teams:

#### One Team – First Prize, AWS Track

- **Product:** A multi-channel KFC ordering chatbot integrated with Zalo and WhatsApp.
- **Solution:** AWS Bedrock Agent Core retains context and transaction history. Tiny Fish automatically collects the KFC menu, while a final verification step prevents incorrect orders caused by hallucinations. Optimized infrastructure cost is approximately USD 0.006 per order.

#### Signal Scout – Second Prize

- **Product:** A Multi-Agent Competitive Intelligence system.
- **Solution:** Collects strategic signals and fragmented competitor financial reports through Tiny Fish and Apify. An Agent Supervisor coordinates Sub-Agents, Langfuse scores data quality, and deterministic code helps prevent Prompt Injection while reducing token costs.

#### PLAN

- **Product:** An AI-native assistant designed specifically for Solution Architects.
- **Solution:** Analyzes natural-language requirements or enterprise policy files, generates Draw.io architecture diagrams, exports cost spreadsheets, and produces Terraform or CloudFormation code for AWS deployment.

#### 3K – Project Shepherd

- **Product:** A real-time AI system for monitoring and coordinating crowd density through cameras.
- **Solution:** Amazon Kinesis Video Streams sends live video to ECS Fargate running YOLOv8/v11 Small with ByteTrack. Users define zones for counting people, while an Amazon Bedrock AI Agent estimates waiting times and recommends staffing adjustments.

#### Six Pillars

- **Product:** An Anti-Money Laundering system for banks and exchanges that reduces false positives.
- **Solution:** A three-tier architecture uses Kinesis and XGBoost for fast filtering; KYC, Money Flow, and Sanction Agents with OpenSearch RAG and Guardrails for analysis; and a Human-in-the-loop Case Management interface. KMS, IAM, Security Hub, and AWS X-Ray strengthen security and observability.

### What I Learned

#### Design And AI Product Mindset

- **Solve the real pain point:** Products should address actual user problems instead of merely showcasing technical complexity.
- **Control the 24-hour scope:** Prioritize a working MVP and avoid expanding the scope beyond what can be demonstrated.
- **Reliability and Human-in-the-loop:** AI requires output review and confirmation, with people retaining decision-making responsibility in critical workflows.

#### Technical And Cloud Architecture

- Understand Supervisor–Sub-Agent Multi-Agent architectures and Agent-to-Agent communication.
- Combine AI with deterministic scripts to validate data, reduce hallucinations, and prevent Prompt Injection.
- Estimate and optimize LLM and Amazon Bedrock costs for real-world environments.

#### Soft Skills And Teamwork

- Improve communication, listen to teammates, and resolve conflict under the pressure of a 24-hour sprint.
- Practice pitching, live demonstrations, and defending system architectures before AWS experts and judges.

### Applying It to My Work

- Apply Supervisor–Sub-Agent patterns and Agent-to-Agent communication when designing AI workflows with specialized responsibilities.
- Combine AI with deterministic code, verification steps, and Human-in-the-loop controls to validate data, reduce hallucinations, and protect critical decisions.
- Focus on real pain points, control MVP scope, and estimate Amazon Bedrock costs from the design stage.

### Event Experience

Following five live pitches and demonstrations helped me understand how an Agentic AI idea becomes a product with a practical architecture, cost model, and user value. The AWS experts' questions also provided useful experience in evaluating feasibility, reliability, and security.

#### Lessons Learned

Agentic AI Buildweek 2026 provided a broad view of current AI Agent development trends and strong inspiration through practical insights from AWS ASEAN leaders Mr. Joseph Marazota and Mr. Nguyễn Gia Hưng. It reinforced user-centered product thinking, the importance of scope control, and teamwork as a core value.
