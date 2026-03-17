# Fraud Success Manager Assistant Challenge

## 1. Introduction

This exercise is an opportunity for you to demonstrate how you approach building practical, high-impact applications using Generative AI. We're excited to see how you think, design, and build.

The goal is not just to arrive at a "correct" answer, but to see how you tackle an open-ended business problem. Your rationale, design choices, and the clarity of your implementation are as important as the final result.

We estimate this challenge should take approximately 4-5 hours to complete.

## 2. The Scenario: The Fraud Success Manager (FSM)

At [Checkout.com](https://www.checkout.com), a Fraud Success Manager (FSM) plays a critical role in protecting our merchants and their customers. An FSM's primary responsibility is to analyse vast amounts of transaction data to identify emerging fraud patterns.

Their core workflow involves:

- **Exploring data** to form hypotheses about potential fraud signals.
- **Validating these hypotheses** against historical data to find anomalous patterns.
- **Translating these patterns** into **fraud rules** that can be deployed into our production systems to block fraudulent payments.

This is a highly iterative and knowledge-intensive process that requires a blend of deep data analysis and domain expertise.

## 3. The Challenge: Build an FSM Assistant

Your mission is to design and build a prototype of a GenAI-powered application that assists a Fraud Success Manager (FSM) in their core workflow of analyzing transaction data to discover patterns and propose new fraud rules.

**Provided Assets:** You will be provided with the following:

- A **SQLite database** (`data.db`) containing transaction data.
- A **schema definition file** (`schema.sql`) that details the table structures, columns, and their relationships. The tables include:
  - `cards`: Credit and debit card details.
  - `fraud_labels`: Binary classification labels for transactions.
  - `mcc_codes`: Merchant Category Codes and descriptions.
  - `transactions`: Transaction records.
  - `users`: Customer information.

**The Challenge:** We want you to think like an engineer in our AI Centre of Excellence. You have been tasked with designing a system that can accelerate the FSM workflow. How can you leverage Generative AI to do it?

To guide your thinking, consider the following questions:

- How can your application empower an FSM to explore the data and uncover suspicious patterns using natural language?
- How does your solution help the FSM transition from a general pattern (an "insight") to a concrete, deployable "rule"? For this task, a "rule" should be defined as a valid SQL `WHERE` clause that can be used to filter the `transactions` table.
  - Example: `amount > 1000 AND card_id IN (SELECT id FROM cards WHERE card_type = 'debit')`.

## 4. What We're Looking For

We will be evaluating your submission based on the following criteria:

- **Problem Decomposition and Product Sense:** How well do you understand the FSM's challenge? How creative, practical, and effective is your proposed solution?
- **Justification of Approach:** Your `README.md` file should clearly articulate your design choices. Why did you choose your specific architecture and interaction model? How does it solve the core problem?
- **Awareness of GenAI Limitations:** Your solution should demonstrate a practical understanding of the risks associated with LLMs (e.g., hallucination) and include design choices that mitigate these dangers.
- **Technical Execution:** Your prototype should be a high-quality, reproducible, and well-documented piece of software.
- **Evaluation Mindset:** How would you design an evaluation framework to prove to a stakeholder (like the Head of Fraud) that your tool is genuinely effective and safe to use? We are interested in your thoughts on both offline and online metrics. As part of this, we would like to see **an initial attempt at an evaluation suite**.

## 5. Guidance on Your Approach

To help guide your submission, please keep the following points in mind:

- **Managing Scope & MVP Guidance:** We are aware that this is a broad and open-ended task. To help focus your efforts within the 4-5 hour timeframe, we suggest prioritizing an MVP with the following core feature: a system that can reliably translate an FSM's natural language questions into accurate SQL queries for data exploration. If you cannot implement other parts of your envisioned system due to time constraints, please outline them in your `README.md`.
- **Focus on Core Functionality:** Your application can have any interface you like, either a simple terminal-based application or one with a frontend. We would appreciate any attempts to provide a solution that would most closely resemble the UX that a user might make use of - but we encourage you to focus primarily on the system's features and your evaluation thereof.

## 6. Logistics & Deliverables

**Final Outputs:**

- GitHub project containing your solution. Please upload your submission to a private Git repository and provide your interviewer with access to it.
- A comprehensive `README.md` file that includes:
  - Setup and installation instructions.
  - A detailed explanation of your solution, its architecture, and the design choices you made.
  - Clear directions on how to reproduce the project. Choice of tooling is left entirely up to you e.g. uv, poetry, pip, Docker, etc.
