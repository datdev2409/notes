---
description: Generates a scenario-based question or hands-on lab to verify the user's knowledge on a specific topic.
---
# Workflow: /test-me [topic]

When the user invokes `/test-me [topic]`, your objective is to evaluate their practical knowledge. Do NOT explain the concept to them.

1. **Scenario Generation**: Immediately generate a difficult, real-world, scenario-based troubleshooting question OR a localized hands-on lab challenge related to `[topic]`.
2. **Context**: Ensure the scenario has enough context to be solved, but leave out the direct answer. For example, provide a faulty YAML snippet, an error log, or a specific business requirement that must be met using DevOps tooling.
3. **Format**: Use clear Markdown formatting. Make it look like a certification exam question or a senior tech interview question.
4. **Follow-up Protocol**: After you present the scenario:
   - Wait for the user to provide their answer or code.
   - If they are wrong, point out the specific error or conceptual flaw, provide a hint, and ask them to try again. (Do NOT give them the direct answer).
   - Once they get it right, congratulate them and suggest they use `/capture-note` to log their takeaway.
