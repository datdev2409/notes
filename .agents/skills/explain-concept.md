---
description: Instructs the agent on how to research and explain technical concepts using an interactive, drip-feed approach in English.
---
# Skill: Explain Technical Concepts

Whenever the user asks you to explain a new technical concept, tool, or process (e.g., "Explain Kubernetes Service to me", "What is AWS IAM?"), you MUST follow this protocol:

1. **Mandatory Web Search**: You **MUST** first execute the `search_web` tool with relevant keywords to find the most current, up-to-date information, official documentation, and best practices. Do NOT rely entirely on your pre-trained knowledge base, especially for rapidly evolving infrastructure tools.
2. **Information Drip-Feed (Micro-Learning)**: Do NOT dump an overwhelming wall of text. Overloading the user with too much information at once reduces retention. Instead, explain just enough to spark understanding.
3. **Structured Mini-Explanation**:
   - **TL;DR**: A bolded, one-sentence punchline summary.
   - **The Problem It Solves (Why?)**: What specific pain point does this tool/concept exist to solve?
   - **Core Concept (What/How?)**: A very brief, intuitive explanation. Use a real-world, non-technical analogy if possible.
4. **Interactive Deep Dive (Choose Your Own Adventure)**: Stop explaining here! Instead, present the user with 3-4 specific options to explore further based on their interest. For example:
   * *"1. Dive deeper into the architecture and internal components."*
   * *"2. Show a real-world, hands-on example (Code snippet YAML/Terraform/Bash)."*
   * *"3. Compare this tool against alternative X (e.g., modern vs traditional setup)."*
   * *"4. Review security best practices for production usage."*
5. **Citations & Call to Action**: 
   - Briefly cite the official URLs you used.
   - Remind the user: *"Let me know which option you want to explore next, or use `/capture-note [your takeaway]` to lock in this fundamental concept before we proceed!"*
