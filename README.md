# DevOps Knowledge Base & Tech Blog

Welcome to my personal Technical Blog and DevOps Knowledge Base. This repository is built as a **Hugo** site using the "Leaf Bundle" architecture to ensure every post is completely modular and encapsulated with its own assets. 

Beyond just being a static site, this codebase is supercharged by **Antigravity**—a highly autonomous AI Agent that acts as my dedicated technical reviewer, editor, and Socratic tutor.

## 🎯 Purpose
1. **Capture Learnings**: To force myself to write down, synthesize, and explain complex technical concepts (like Kubernetes, AWS, Terraform) in my own words.
2. **Showcase Skills**: To act as a living, breathing portfolio of my technical journey and capabilities.
3. **Knowledge Sharing**: To distribute insights and best practices with the broader DevOps and engineering community.

## 📂 Repository Structure

The repository relies heavily on maintaining a clean directory separation between "messy learning" and "published content".

```text
.
├── drafts/                     # (Ignored in Git) Raw, unformatted notes and screenshots taken during active learning.
├── content/    
│   └── posts/                  # The actual Hugo technical blog posts.
│       ├── YYYY-MM-DD-slug/    # Leaf Bundle format: Each post gets its own directory.
│       │   ├── index.md        # The Markdown content with YAML Front Matter.
│       │   └── image.png       # Images grouped natively with the post.
└── .agents/                    # The "AI Brain" built specifically for Antigravity.
    ├── skills/                 # AI behavioral instructions (e.g., Socratic verification).
    └── workflows/              # Slash commands to process drafts into bundles.
```

## 🤖 Antigravity Workflow (Slash Commands)

To minimize toil work (scaffolding folders, adding YAML Front Matter, fixing relative image paths, etc.), this project employs specific Antigravity Workflows natively defined in the `.agents/` folder.

### 📝 1. Active Learning (`/capture-note`)
While learning a new concept, I chat interactively with Antigravity. When I synthesize a new insight, I invoke:
> `/capture-note [my takeaway]`

- Antigravity acts as a Senior Tech Lead and **verifies the technical correctness** of my statement.
- If it's correct, Antigravity formats the syntax and appends it to a raw note in the `drafts/` folder. It never rewrites my personal voice.

### 📦 2. Productionizing (`/bundle-post`)
When a draft is ready to become a polished article, I invoke:
> `/bundle-post [filename]`

- Antigravity automatically extracts the draft, generates a SEO-friendly slug (`YYYY-MM-DD-slug/`), creates a Leaf Bundle in `content/posts/`, generates YAML Front Matter, links all local images, and cleans up the draft folder.

### 🧠 3. Knowledge Verification (`/test-me`)
When I want to practice, I invoke:
> `/test-me [topic]`

- Antigravity immediately generates a scenario-based troubleshooting question or hands-on CLI lab related to the topic. It refuses to give me the direct answer, forcing me to troubleshoot and solve it myself.

### 🚀 4. Publishing (`/publish`)
> `/publish`

- Antigravity sets `draft: false` on an active bundle, commits it with semantic messages, and pushes upstream to trigger my CI/CD pipelines.
