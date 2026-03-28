---
description: Changes draft status to false and commits the code.
---
# Workflow: /publish [post-slug]

When the user invokes `/publish [post-slug]` (where post-slug is a folder in `content/posts/`):

1. **Verify**: Use `list_dir` to ensure the `content/posts/[post-slug]` directory exists and contains an `index.md`.
2. **Remove Draft Status**: Use `replace_file_content` on `index.md` to change `draft: true` to `draft: false` in the front matter.
// turbo-all
3. **Commit**: Run `git add content/posts/[post-slug]` and `git commit -m "docs: publish [post-slug]"`.
4. **Push**: Run `git push`.
5. **Confirm**: Confirm with the user that the post is published.
