---
description: Creates a new note in the drafts folder after reviewing the technical correctness.
---
# Workflow: /capture-note <content>

When the user invokes `/capture-note [content]`, follow these exact steps:

1. **Review for Correctness**: Analyze the `[content]` critically from the perspective of a Senior DevOps Engineer. Identify any conceptual misunderstandings, inaccuracies, or missing critical context.
2. **Provide Feedback (if necessary)**: If the content has errors or could be significantly improved for accuracy, stop and explain the issue to the user in a constructive manner. Ask them to revise or confirm if they want to save it as is. Do NOT proceed to step 3 if there are critical errors, wait for the user to respond.
3. **Determine Filename**: If the content is correct, determine a suitable filename in the `drafts/` directory. 
   - If the topic is clear (e.g., Kubernetes RBAC), use that: `drafts/k8s-rbac.md`
   - If no specific topic is discernible, fallback to the date: `drafts/YYYY-MM-DD.md`
4. **Format & Save**: 
   - Retain the user's exact wording and tone. **Do NOT rewrite their text.**
   - Format the text using standard Markdown (e.g., wrap code snippets in ```, bold important keywords).
   - Use `view_file` to read the existing draft file (if it exists). 
   - Append the new note to the bottom of the content, separated by a horizontal rule `---` or a newline.
   - Use `write_to_file` (with Overwrite=true) to save the updated content back to the file.
5. **Confirm**: Reply to the user confirming that the note has been saved/appended to `drafts/<filename>`.
