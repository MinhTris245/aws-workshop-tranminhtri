---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# Summary Report: “Career Orientation and AI Applications on AWS”

### Event Information

- **Date:** May 23
- **Role:** Attendee
- **Main topics:** Career orientation, Prompt Engineering, Multi-Agent systems, Amazon CloudFront, and enterprise AI security

### Event Objectives

- Provide career direction and development strategies for IT engineers in the rapidly evolving AI landscape.
- Share Prompt Engineering best practices and methods for supplying context to work effectively with AI.
- Explain how to apply enterprise Multi-Agent architectures to complex problems while meeting security requirements.
- Present Amazon CloudFront's new pricing model and advanced security capabilities.

### Speakers

- **Nguyen Gia Hung** — Solutions Architect, AWS Vietnam; founder of SC
- **Tinh Truong** — Platform Engineer, Gotam X
- **Hai Anh** — Pacific Vietnam
- **Nguyen Tuan Thinh** — DevOps Engineer
- **Uyen and Thao** — Hackathon team, UTM Morpo project
- **Vy Lam** — Specialist in implementing AI systems for VBBank

### Key Highlights

#### Career orientation in the AI era

- The Jevons paradox suggests that when AI lowers the cost of creating software, demand for software may grow sharply and create more jobs.
- Work such as fixing AI-generated defects, maintaining systems, AI DevOps, and Platform Engineering will become increasingly important.
- To compete, engineers need academic foundations, strong technical knowledge, business understanding, and real products—not only demos.

#### Optimizing context for AI

- Avoid an “Internet Buller” mindset that overloads AI with too many unrelated plugins, rules, and data.
- Constant context changes can distract the model and produce inaccurate answers.
- Context should be narrow but deep, with a clearly defined **Goal, Role, and Format** based on the real business domain.
- An AI mindset and the ability to apply AI appropriately are important labor-market skills.

#### Reducing LLM variability

- An LLM is a **Probabilistic Engine**, so results can vary between runs even when `temperature = 0`.
- Differences may arise from GPU floating-point calculations and provider inference-optimization techniques.
- Mitigations include running the model multiple times to identify consensus, self-hosting the model, using JSON Mode, and testing continuously.
- Downstream systems must detect and handle malformed or unstable AI output.

#### Optimizing cost and security with Amazon CloudFront

- Flat Rate Pricing provides Free, Pro, Business, and Premium plans with AWS WAF integration to reduce the risk of bill spikes caused by DDoS attacks or abnormal traffic.
- VPC Origin hides the origin server from the public internet and permits only internal CloudFront connections.
- CloudFront also supports mTLS, geographic restrictions, and DDoS protection at the Edge.

#### Lessons from a 36-hour Hackathon

- Morpo is an AI-assisted editor that creates HTML/CSS interfaces from screenshots or hand-drawn designs.
- Users can edit the interface directly instead of asking AI to regenerate everything, thereby saving tokens.
- Important lessons included focusing on one real problem, avoiding feature creep, dividing work clearly, and maintaining personal health during the competition.

#### Building an Enterprise Multi-Agent System

- The case study focused on credit assessment for startups without collateral, relying mainly on intellectual property.
- Multi-Agent systems are suitable when context is very large and the problem requires specialized roles such as finance, market research, and risk management.
- Dividing responsibilities prevents the context window from growing excessively and reduces knowledge drift.
- Enterprises need input/output guardrails, Prompt Injection defenses, Output Filtering, API-key rotation, and an Audit Trail.
- Knowledge Transfer should select the information real experts use instead of feeding entire long documents to AI.

### What I Learned

#### Design Mindset

- **Business-first:** Start by asking who will use the system, what they will use, and why, following the Working Backwards method.
- A system must not only function but also be secure, reliable, and supported by an Audit Trail that establishes accountability.
- Every AI-adoption decision should connect to user needs and concrete business value.

#### Technical Architecture

- I understood MCP attack vectors and the importance of isolating each Agent's access permissions.
- I learned the Infrastructure as Code mindset and Terraform's role in infrastructure management and automation.
- Multi-Agent orchestration should follow a divide-and-conquer approach in which every Agent has a clear Role and Goal.
- Downstream systems must proactively validate and handle unstable LLM output.

#### Development Strategy

- Engineers should not become so dependent on AI that they neglect core backend skills such as password hashing and JWT Authentication.
- An enterprise AI Engineer must first be a Software Engineer capable of integrating AI securely.
- Before implementation, a solution's ROI should be calculated with real data to persuade stakeholders.

### Applying It to My Work

- **Improve LLM usage:** Standardize prompts, remove redundant rules, and provide relevant context for more stable output.
- **Strengthen project security:** Use CloudFront to filter unwanted requests and VPC Origin to protect the origin server.
- **Design Multi-Agent workflows:** Separate the process into research, review, and synthesis Agents instead of assigning every task to one chatbot.
- **Practice Infrastructure as Code:** Learn Terraform to manage infrastructure instead of relying on manual AWS Console operations.
- **Add testing:** Design downstream validation for JSON and other AI-generated output.

### Event Experience

The event provided valuable direction and gave me a more practical view of both the potential and limitations of AI in enterprise environments.

#### Learning from experienced practitioners

- The sessions covered topics ranging from IT career strategy to a bank's internal credit-assessment process.
- They focused on how engineers can adapt, develop capabilities, and create real value in the AI era.

#### Lessons in security mindset

- Warnings against copying ChatGPT-generated code directly into production showed that AI output must always be reviewed and tested.
- Cases where applications were rejected for deployment because of data-leakage risks emphasized security's critical role in enterprises.

#### Lessons from the Hackathon

- The teams' time management and removal of superficial features to focus on the core experience provided useful lessons for personal projects.
- A product that solves one real problem well is more valuable than one with too many unfinished features.

#### Lessons Learned

- AI's growth does not eliminate the role of software engineers, but it requires stronger system-design, process-management, and business-domain capabilities.
- Backend, Security, and Infrastructure as Code knowledge provide the foundation for secure GenAI deployment.
- Enterprise systems must be secure, reliable, and aligned with user needs—not merely operational.

> Overall, the event helped me develop a more practical perspective on careers, Prompt Engineering, Multi-Agent systems, Amazon CloudFront, security, and enterprise-scale AI deployment.
