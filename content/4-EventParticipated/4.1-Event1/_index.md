---
title: "Event 1"
date: 2026-05-09
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

# Harvest Report: "FCAJ Community Day - 09/05/2026"

### Event Objectives

- Share practical techniques for building sustainable study habits by leveraging how the brain actually works.
- Introduce advanced Prompt Engineering practices and explain how optimized prompts significantly improve the output quality of Large Language Models (LLMs).
- Discuss the role of junior developers in the AI era and emphasize the critical importance of strong foundational knowledge.
- Present the BMAD Method — a structured, AI-driven software development framework that replaces unorganized "vibe coding."

### Speakers

- **Huynh Hoang Long** - FCAJ Member
- **Nguyen Tuan Thinh** - DevOps/Cloud Engineer (FCAJ Representative Speaker)
- **Nguyen Duy Khang** - Solutions Architect at Cloud Kinetics
- **Thao Nguyen** - BMAD Method Expert

### Event Highlights

#### Hacking Your Brain to Learn Like a Game Addict (Huynh Hoang Long)

Huynh Hoang Long opened with a relatable question: why can we scroll TikTok for hours effortlessly, yet struggle to study for just 10 minutes?

- **Root cause analysis:** The brain prioritizes low-energy activities with fast rewards and curiosity triggers — exactly what social media and online games have mastered.
- **The Dopamine Mechanism:** Dopamine is not released when you receive a reward, but when you *expect* a reward is coming. This is why TikTok algorithms and slot machine mechanics keep users hooked so effectively.
- **"Mystery Reward Box" technique:** Write random small rewards on separate pieces of paper, put them in a box, and draw one every 10 minutes of studying. The curiosity of not knowing the next reward triggers a dopamine loop that sustains motivation.
- **Leveraging Loss Aversion:** Build a daily learning streak calendar similar to Duolingo's streak system or game daily check-ins. Once a streak gets long enough, the fear of breaking it becomes a powerful motivator.
- **Task Decomposition:** Break large study goals into tiny daily chunks — one AWS service per day instead of cramming everything in one session. Like a beginning runner who breaks a 5km run into short segments.
- **The 2-Minute Rule:** If something can be resolved in 2 minutes, do it immediately. Never let it pile up.
- **XP System:** Design a personal XP (experience point) reward system where completing topics earns points that unlock real-world treats (a Starbucks drink, an activity, etc.).
- **Share knowledge instead of scrolling:** Replace mindless scrolling with posting new things you learned — this also builds the habit of becoming a future speaker at events like FCAJ Community Day.

#### Automated Prompt Engineering & Proptimizer on AWS (Nguyen Tuan Thinh)

Nguyen Tuan Thinh presented entirely in English, explaining the art of communicating effectively with AI models.

- **The "Generic Prompt" problem:** Vague prompts produce low-quality outputs, waste tokens, increase API costs, and push models into hallucination mode.
- **7 Key Components of a Great Prompt:**
  - **Role:** Define the persona the AI should adopt (e.g., "You are a senior career coach").
  - **Instruction:** The specific action to perform.
  - **Context:** Relevant background information.
  - **Input Data:** The raw text or data to process.
  - **Output Format:** JSON, Markdown, bullet list, etc.
  - **Examples:** Few-shot prompting to guide style and accuracy.
  - **Constraints:** Length limits, language scope, and rules.
- **Advanced Prompting Techniques:**
  - **Chain of Thought (CoT):** Guide the AI to reason step-by-step for complex tasks.
  - **Self-Consistency:** Run multiple reasoning paths and select the majority consensus answer.
  - **Tree of Thought (ToT):** AI uses BFS/DFS to explore multiple reasoning branches to find the optimal solution.
- **Token Economics:** Vietnamese costs roughly double the tokens compared to English; API pricing is split between input and output tokens — understanding this is essential for cost management.
- **Proptimizer Solution Architecture on AWS:**
  - **Frontend & CDN:** Next.js hosted on Amazon S3, globally distributed via Amazon CloudFront with Origin Access Control (OAC).
  - **Authentication:** Amazon Cognito manages sign-up, sign-in, password reset, and JWT token issuance — zero custom auth infrastructure needed.
  - **API & Backend:** Amazon API Gateway routes traffic → AWS Lambda (serverless) handles business logic on-demand.
  - **AI Core:** Amazon Bedrock provides secure, serverless access to Foundation Models (Claude, GPT) — no server provisioning required.
  - **Storage:** Amazon DynamoDB (NoSQL) stores prompt history and user configs; Amazon S3 stores static assets.
  - **Monitoring:** Amazon CloudWatch aggregates Lambda logs and API Gateway metrics for debugging and performance analysis.
  - **Product Feature:** Proptimizer is a browser extension — highlight any text on any webpage, click the icon, and receive an AI-optimized prompt ready to paste into ChatGPT or Gemini.

#### Foundation Knowledge & the Role of AI for Freshers (Nguyen Duy Khang)

Khang — Solutions Architect at Cloud Kinetics with 3 years of industry experience — shared a candid perspective from the hiring side:

- **Foundation over breadth:** In a rapidly changing industry, foundational knowledge is the only thing with lasting value. Hiring managers don't need you to know all 200+ AWS services; they need you to truly master 5 core services and demonstrate a solid **thought process**.
- **AI amplify:** AI doesn't replace developers — it amplifies their existing ability. If you're strong, AI makes you 10x stronger. If you're weak, AI makes your weaknesses more visible, faster.
- **You can outsource your thinking, but not your understanding:** When an employer changes one small detail in an assignment, candidates who only copied AI output without truly understanding it will immediately fail. Those who understood the fundamentals adapt easily.
- **No absolute right or wrong in cloud architecture:** What matters is your reasoning — a well-argued rationale for choosing one solution over another is what passes interviews, not memorized answers.

#### BMAD Method — Structured AI-Driven Software Development (Thao Nguyen)

BMAD (Breakthrough Method for Agile AI-Driven Development) is an open-source framework designed to bring discipline and structure to AI-assisted software development, replacing chaotic "vibe coding":

- **Agentic Roles:** Assign specialized AI agents to act as Product Manager, Architect, Developer, QA, and Scrum Master — each responsible for a defined SDLC stage.
- **Two Core Phases:**
  - **Phase 1 - Agentic Planning:** Produce complete PRDs (Product Requirements Documents), system architecture blueprints, and user stories *before writing any code*.
  - **Phase 2 - Context-Engineered Development:** Use the Phase 1 artifacts as grounding context to guide development agents in producing accurate, maintainable, and consistent code.
- **Practical Benefits:**
  - Reduces AI hallucination because agents cross-validate each other's outputs.
  - Produces well-documented codebases that are easy to audit and scale.
  - Scales from solo side projects to enterprise-level systems.
  - Installed via CLI (`npx bmad-method install`), compatible with Cursor, Claude Code, and other AI IDEs.

### Key Takeaways

#### Study Habits & Personal Development
- Understood the dopamine mechanism as the foundation for designing a personalized and sustainable self-study system.
- Planning to apply the "mystery reward box" and daily streak calendar immediately to my AWS self-study roadmap.

#### Prompt Engineering & AI Cost Control
- Mastered the 7-component prompt framework and advanced techniques (CoT, ToT) to extract the highest quality output from LLMs.
- Learned to calculate token costs when building AI-powered apps on AWS Bedrock to prevent unexpected cloud bills.

#### Cloud Architecture Thinking
- Gained a clear understanding of each component in a full Serverless AWS architecture (S3, CloudFront, Cognito, API Gateway, Lambda, Bedrock, DynamoDB, CloudWatch) and the rationale behind each service selection.

#### Professional AI Collaboration
- Solidified the understanding that AI amplifies capability rather than replacing thinking. Strong foundations are the only durable competitive advantage.
- Started exploring the BMAD Method to apply to personal projects in a more structured, spec-driven way.

### Work Application

- **Improve AI Interaction Quality:** Apply the 7-component prompt framework and Chain-of-Thought technique to daily tasks including writing documentation, code reviews, and test case generation for the AutoRx project.
- **Build Sustainable Study Habits:** Implement a streak-based learning check-in system with mystery reward boxes to maintain consistent daily AWS learning progress.
- **Explore BMAD Method:** Experiment with applying BMAD's Phase 1 planning to structure the internship project with clear PRD and architecture documentation before implementation begins.
- **Cloud Cost Governance:** Actively monitor Bedrock token usage and API Gateway logs to keep AWS Lab spending within acceptable limits.

### Event Experience

This was my first FCAJ Community Day and the experience exceeded expectations:

#### Unique Blend of Soft Skills and Technical Content
- It was rare and refreshing to open a tech community event with a talk on **learning psychology** rather than purely technical content. Huynh Hoang Long's session resonated deeply with anyone struggling with inconsistent motivation.

#### Real-World AWS in Action
- The live **Proptimizer** demo by Nguyen Tuan Thinh was the highlight — seeing a production browser extension built on a complete Serverless AWS architecture clarified exactly what the internship program's final project should look like.

#### Unfiltered Perspective from the Hiring Side
- Khang's candid breakdown of how he evaluates candidates and assignments changed the way I think about using AI — and reinforced my commitment to truly *understanding* concepts rather than simply *copying outputs*.

#### Event Gallery
![Group Photo](/images/AWSevent1.jpg)
![Slide Photo](/images/event1_presentation.jpg)
> Overall, FCAJ Community Day 09/05 was a high-quality event that equipped me with both technical tools (Prompt Engineering, BMAD, Serverless AWS) and the right mindset (learning habits, foundational knowledge, AI amplification) to grow sustainably in my IT career.
